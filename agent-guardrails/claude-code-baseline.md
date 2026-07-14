---
Artefact type: Baseline (Standards layer)
Owner role: Security/GRC lead, with whoever administers the coding-agent tooling as contributing reviewer
Review cadence: Quarterly, and after any release that changes the tool's permission model
Version: 1.0 (template)
---

# Claude Code baseline

Claude Code governs tool use through a layered settings model with an enforceable managed tier: the closest thing in this comparison to a traditional enterprise policy file.

## Settings precedence

Settings are read from five tiers, highest precedence first: managed settings, command-line flags for the current session, local project settings (not checked into version control), shared project settings (checked in, e.g. for a whole repository), and user settings (the individual's own defaults). One important nuance: permission rules specifically don't simply override each other tier-by-tier; rules from every tier merge into one combined set, and a deny rule at *any* tier beats an allow rule from *any other* tier, including a more specific one from a higher-precedence tier. Design managed-tier rules assuming they'll be layered on top of whatever a project or user already has locally.

## Permission rule syntax

Rules take the shape `Tool` or `Tool(specifier)`. A specifier can match an exact command, use a wildcard (with a space before `*` to enforce a word boundary so a partial-word match doesn't slip through), match a file path, scope a web-fetch rule to a domain, or match a named input parameter directly. Rules are evaluated in a fixed order (deny, then ask, then allow), and the first match in that order wins; a rule's specificity does not change that order. A broad deny rule blocks every call it matches even if a narrower allow rule also matches the same call: a deny rule can't be selectively carved back open with a sibling allow rule.

MCP-provided tools use a distinct namespace, `mcp__<server>__<tool>`. Deny and ask rules can use wildcards anywhere in that pattern, including a bare `mcp__*` to match every MCP tool regardless of server; allow rules are more conservative and only accept a wildcard after a literal, non-wildcarded server name (`mcp__<server>__*`), so a blanket allow across all servers isn't a single-line footgun.

## Managed settings: the enforceable tier

Managed settings live in a dedicated file, delivered by one of three mechanisms: a file dropped at a fixed OS-specific path outside normal user write permissions, an MDM profile push, or a server-managed configuration delivered through an organisation's admin console. A drop-in directory variant also exists, letting multiple managed-settings fragments merge together (arrays concatenate, objects deep-merge) rather than requiring one monolithic file: useful if different policy fragments come from different owners (security, platform, a specific team's exception).

Three settings turn the managed tier from "the default a user could override" into an actual perimeter:

- One setting restricts permission rule definition to the managed tier only: once set, user and project settings can no longer define their own allow/ask/deny rules at all.
- A parallel setting does the same for hooks specifically, so only managed-supplied (or SDK/plugin-force-enabled) hooks run: a user or project can't quietly add a hook that bypasses the intended flow.
- A separate pair of settings disables the tool's own "skip all permission checks" and "auto-approve" modes outright, so a shortcut meant for an individual's own trusted local sessions can't be reached at all in a governed environment.

All three matter more when set at the managed tier than anywhere else; set locally, they're just a preference the same user could unset.

## Worked baseline

A reasonable starting point for a small team, in the audit-then-tighten spirit from the [tool-agnostic spine](README.md#5-roll-out-in-stages-observe-then-tighten):

- **Deny outright:** reading credential stores and private key material by pattern (SSH private keys, cloud credential files, browser/OS keychains) rather than by an exhaustive exact-path list, since the exact-path approach reliably misses a variant; writing to shell startup files or an SSH authorised-keys file via redirection.
- **Ask:** force-pushing git history, skipping commit hooks, reading a `.env`-pattern file, and a short list of high-impact command patterns (recursive delete, infrastructure-destroy commands, database drop/truncate/delete statements, publishing a package, merging or releasing without review). Flag these for confirmation rather than blocking them outright, because there are legitimate reasons to do each of these and a hard deny just gets worked around.
- **Allow freely:** the fast inner-loop commands a team actually runs dozens of times a day (running the test suite, linting, building, reading and listing files in the project). The goal of the ask tier is to catch the rare dangerous action without adding friction to the common safe one.
- Set the managed-only restriction on permission rules and hooks only once the baseline has been through its audit period and the team is confident it reflects real usage. Locking in a baseline before it's validated just means re-editing a file with tighter change control than an unlocked one would have needed.

## Adapt this to your context

- The specific deny/ask/allow split above assumes a typical software team's workflow. A team working primarily in infrastructure-as-code, or one with no package-publish step at all, should re-derive the high-impact command list from its own actual toolchain rather than reusing this one verbatim.
- If your organisation already has an existing endpoint or MDM governance layer, managed settings delivery should plug into that existing distribution mechanism rather than becoming a second, parallel one only the security team knows about.
- Re-verify every setting name and file path here against the tool's current documentation before deploying. See the top-level disclaimer.
