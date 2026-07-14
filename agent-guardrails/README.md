# agent-guardrails

A documented, security-reasoned permission baseline for AI coding agents, covering the two tools most teams actually have to govern today: a CLI-based coding agent with a managed-settings model, and a plugin-based coding agent with a rule-engine model. This kit teaches the tool-agnostic principles first, then a worked baseline for each.

## Why this exists

AI coding agents run real tools against real systems: shells, file systems, git remotes, package registries, production infrastructure. Every team that adopts one inherits a new governance surface, and most teams govern it badly: either "allow everything, we trust the tool" or a pile of ad hoc denials that nobody can reason about as a whole. This kit is a worked example of the alternative: a small set of principles, applied consistently, with a written rationale for every rule, so the baseline is auditable rather than folklore.

## Before you rely on anything here

**This kit gives a lean team a defensible starting baseline for two specific tools. It is a starting point for a governance program: it is not finished, and it is not designed to be bulletproof.** See the [repo-level disclaimer](../README.md#before-you-rely-on-anything-here) for the full statement. It applies here too, with one addition specific to this kit: **agent permission models change fast.** Amp materially changed its default security posture within the last 12 months (see the [Amp baseline](amp-baseline.md)), and nothing stops the other tool doing the same. Treat every specific setting name, file path, and default behaviour below as correct as of when this was written, and re-verify against the tool's current documentation before depending on it; don't assume a permission model is stable just because it worked last quarter.

## The tool-agnostic spine

Everything below applies regardless of which agent you're governing.

### 1. Deny beats allow, and specificity doesn't change that

A well-designed permission system evaluates rules in a fixed order (deny, then ask, then allow), and the first matching rule wins regardless of how specific a competing rule further down the list is. A broad deny rule blocking a whole class of commands still blocks a narrower allow rule that would otherwise have permitted one of them. Design your rules around this: a single broad deny for a dangerous pattern is worth more than a long list of narrow allows you hope don't collide with it.

### 2. The sandbox-versus-permissions distinction: the point almost everyone misses

Denying a tool at the permission layer does not stop the underlying capability if a *different* tool with equivalent reach is still allowed. The clearest example: blocking a dedicated network-fetch tool does nothing to stop `curl` or `wget` if a general-purpose shell tool is still permitted, because network egress from a shell is an OS-level capability that sits outside what the permission layer mediates. Permission rules govern which *tools* the agent invokes; they do not put a network or filesystem boundary around what a permitted tool can then do. If you need an actual boundary (no egress except an allowlist, no filesystem access outside a project directory), that has to come from a sandboxing layer (a container, a VM, an OS-level sandboxing profile) sitting underneath the permission system. Treat "we deny the fetch tool" and "this agent cannot reach the network" as two different claims, and don't let the first one stand in for the second in a threat model.

### 3. Managed settings beat local settings, or they're not really managed

A permission baseline that lives only in a user's local config is a suggestion: the same person who might run a risky command can also edit the file that would have blocked it. A real governance layer needs a settings tier that a normal user session cannot edit: delivered via an admin console, an MDM profile, or a file outside the user's write permissions. Both worked baselines below identify where each tool's enforceable tier lives and how it's delivered.

### 4. Ask for genuinely ambiguous cases; don't make every rule a yes/no gate

Some commands are unambiguously fine (running a test suite) and some are unambiguously dangerous (recursive delete against a production path); those deserve a hard allow or deny. A useful middle tier exists for commands whose risk depends on context a static rule can't see (is this `rm -rf` against a scratch directory or a shared one?). Both tools covered here support routing that middle tier to an interactive confirmation, and one of them supports routing it to the model's own judgement first. Use the ask tier deliberately for genuine ambiguity: overusing it just trains people to click through prompts without reading them, which defeats the point.

### 5. Roll out in stages: observe, then tighten

Deploying a strict baseline on day one, before you know what your actual workflows need, produces either constant interruption (so people disable it) or a baseline quietly full of holes punched to make real work possible. Start in an audit or observation mode where the tool logs what it *would* have blocked without actually blocking it, review that output for a representative period, then tighten the ruleset based on what you learned rather than what you guessed in advance.

## Worked baselines

- [Claude Code baseline](claude-code-baseline.md): settings precedence, permission rule syntax, managed-settings delivery, MCP tool governance
- [Amp baseline](amp-baseline.md): the opt-in rule engine and its external-delegate action, the 2026 default-posture change and why explicit opt-in now matters, routing ambiguous commands to the model's own judgement

## Licensing

CC BY 4.0. See the [repo root licence note](../README.md#licensing).
