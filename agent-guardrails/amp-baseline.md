---
Artefact type: Baseline (Standards layer)
Owner role: Security/GRC lead, with whoever administers the coding-agent tooling as contributing reviewer
Review cadence: Quarterly, and after any release that changes the tool's permission model
Version: 1.0 (template)
---

# Amp baseline

Amp's governance model is worth documenting for a reason beyond "here's how to configure it": the tool changed its own default posture significantly in 2026, and that change is itself the most useful lesson in this kit.

## The default changed: know which one you're running

Amp originally shipped with a rule-based permission engine similar in spirit to other coding agents': every tool call checked against an ordered list of rules before running. As of a mid-2026 release, the vendor changed the *default* behaviour so that Amp does not ask for approval before running tools at all, on the stated reasoning that as agents increasingly write and chain their own throwaway scripts, a rule engine trying to statically pattern-match "is this command safe" against an open-ended space of generated shell commands was becoming unreliable as a safety boundary anyway.

The old rule-based engine still exists and is fully supported: it activates automatically the moment the tool detects that a workspace or user has defined its own permission rules, or explicitly turned off the "allow everything" setting. In other words: **as of this change, running Amp's rule-based gate is now something you opt into rather than something you get by default.** Before adopting Amp anywhere governance matters, the first and most important configuration decision is confirming which mode you're actually running: check for an explicit permissions configuration and an explicit statement that blanket auto-allow is turned off, rather than assuming a gate exists.

This is a useful case study in its own right: a vendor can change your effective security posture with a product update, silently, if your governance depends on a default rather than an explicit, checked-for configuration. Treat "what does this tool do out of the box today" as a question to re-verify periodically rather than a fact to memorise once.

## The permission rule model (when opted in)

Once the legacy gate is active, every tool call is checked against an ordered list of rules until one matches; the matching rule's action applies. Available actions: allow it outright, ask for interactive confirmation, reject it, or hand the decision to an external helper program. Rules match on named parameters of the call (a command string, a file path, a target) using glob patterns, regular expressions, an array of alternatives, or an exact literal, which is a more flexible matching surface than a single command-string pattern alone.

The external-delegate action is a distinctive feature: instead of the tool's own built-in logic making the allow/ask/reject call, a rule can hand the decision to an external program (the call's details passed in, a decision code passed back), which is how a policy engine external to the coding agent itself (something a security team already runs) can become the actual source of truth for what an agent is allowed to do, rather than duplicating that logic inside the agent's own config.

## Configuration locations

Rules live in a settings file read from three tiers: a system-wide managed-settings file at a fixed OS path (analogous to the managed tier in other tools: this is the enforceable one, locked against user edits in a normal session), a workspace-level settings file that lives in the project and is merged with the user's own global settings, and the user's own global settings file. An organisation running Amp at any scale should also be aware of a separate, web-console-based admin layer (configured centrally rather than via any local file) that can enforce an approved-server allowlist for external tool integrations and set per-person or per-team usage limits; that layer is a distinct governance surface from the local rule engine and is worth knowing about even though it isn't a permission-rule mechanism in the same sense.

## A useful pattern: asking the model, not just a regex

Beyond the standard allow/ask/reject/delegate actions, Amp's plugin surface lets a rule call back into the model itself to make a judgement call on an ambiguous case: describe the command in question and a specific yes/no question about its risk, and use the model's own answer (plus its confidence) to decide whether to escalate to a human. This is a meaningfully different tool from pure pattern-matching: a static rule can't easily tell the difference between a destructive command run against a scratch environment versus a shared one, but a model asked the right specific question, with the right framing to bias toward caution on genuine uncertainty, often can. Reserve this pattern for the ambiguous middle tier (commands that are neither obviously safe nor obviously dangerous) rather than using it as a substitute for a clear deny rule on things that are unambiguously dangerous regardless of context.

## Worked baseline (for the opted-in, rule-based mode)

- **Reject outright:** force-pushing to a protected branch (checked dynamically against the actual repository's protection settings where the tooling allows it, with a small static fallback list of common branch names for when it can't); writes to shell startup files or an SSH authorised-keys file via shell redirection.
- **Ask:** force-pushing to a non-protected branch; skipping commit hooks; editing a shell startup file directly (as opposed to via redirection, which is rejected outright above); a drive-by install pattern (piping a network download straight into a shell or script interpreter). Flag it and require the script be fetched and read in a separate step first.
- **Route to the model, then ask if warranted:** a broader family of high-impact command patterns (recursive delete, infrastructure destroy commands, database drop/truncate/delete statements, package publishing, merging or releasing without review, bulk cloud-resource deletion). Ask the model whether the specific invocation would cause irreversible change to production infrastructure, production data, package registries, or shared cloud resources, treating local-only equivalents (a dev cluster, a scratch directory, ephemeral test data) as out of scope, and only escalate to a human confirmation when the answer is yes or uncertain.
- **Block reads of credential material by pattern** (private key files, cloud credential stores, OS keychains, the tool's own stored credentials) rather than an exhaustive exact-path list: pattern-matching catches variants an exact-path list will always eventually miss.
- **Require confirmation before reading `.env`-pattern files**: they often hold secrets, and a blanket allow here is one of the more common accidental-disclosure paths for an agent with broad file read access.

## Adapt this to your context

- If you're deploying Amp today, confirm which mode is actually active before assuming any of the rule-based guidance above even applies. See "the default changed" above. A baseline written for the rule engine does nothing if the workspace never opted into it.
- The delegate-to-an-external-program pattern is worth adopting specifically if your organisation already runs a policy engine (for infrastructure access, for example): reusing that existing source of truth beats maintaining a second, parallel rules file that can drift out of sync with it.
- Re-verify every setting name and file path here against the tool's current documentation before deploying. See the top-level disclaimer. This tool's configuration surface has moved multiple times within a single year; treat anything here as a snapshot rather than a permanent reference.
