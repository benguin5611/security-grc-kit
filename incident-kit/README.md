# incident-kit

A portable, vendor-neutral method for documenting an incident from first detection through to lessons learned: the write-up discipline, independent of any specific ticketing tool's screens.

## Why this exists

Incident write-up quality is one of the more legible signals of operational maturity a small team can produce, and it's also one of the easiest disciplines to do badly under time pressure: rushed, inconsistent, or skipped once the fire is out. This kit is the method: a section-by-section post-incident review (PIR) structure, a severity rubric, a discipline for reconstructing a timeline from primary sources, a customer-communication structure, and a cross-linking checklist. Every tool-specific hook has been stripped out, so it drops into whatever chat tool, ticketing system, and status page a team already uses.

## Before you rely on anything here

**This kit is designed to get a lean team from nothing to a defensible incident write-up practice, fast. It is an early starting point on the way to a finished incident-management program, and it makes no claim to be bulletproof.** See the [repo-level disclaimer](../README.md#before-you-rely-on-anything-here) for the full statement; it applies here too.

## What's here

| File | Covers |
|---|---|
| [pir-guide.md](pir-guide.md) | The section-by-section post-incident review structure, and what belongs in each section |
| [severity-rubric.md](severity-rubric.md) | A three-tier severity calibration (P1/P2/P3) and how to decide the borderline cases |
| [customer-comms-structure.md](customer-comms-structure.md) | The five things every customer-facing incident communication should cover |
| [cross-linking-checklist.md](cross-linking-checklist.md) | The discipline of linking every incident artefact to every other one, so nothing about an incident lives in only one place |

## The source-reading discipline

Before writing a word of the PIR, reconstruct the incident directly from primary sources: the chat history, tickets, and any public status page. Working from memory or a verbal summary of what happened isn't good enough.

- **Read the whole thing, not a summary of it.** Skim-reading a chat thread or ticket history produces a skim-quality PIR. Follow pagination to the end; don't stop at the first page of results.
- **Chase threaded replies separately.** Chat tools that show a channel's main timeline often don't inline thread replies, and the decisions and fixes are usually buried in the threads rather than the top-level messages. Read threads on every message that clearly spawned a discussion.
- **Cross-check the public record against the internal one.** If a public status page or customer-facing status exists, read it too. The gap between "we fixed it internally" and "we told customers it was fixed" is itself often a lessons-learned item.
- **Convert every timestamp to one timezone, deliberately, and say which one.** A timeline that silently mixes UTC, server time, and a reader's local time is unreliable the moment two people compare notes on it.
- **If a source doesn't exist, say so; don't skip the check.** No public status update was posted? Note that explicitly in the Communication section as information about the incident response in its own right.

## Relationship to the ITSM docs-kit

Per the [audience split in the root README](../README.md#relationship-to-the-itsm-kit), the method lives here and the fill-in artefacts live in the companion ITSM docs-kit:

- [pir-guide.md](pir-guide.md) here explains what each PIR section is for and why; the fill-in [post-incident report template](https://github.com/benguin5611/ITSM/blob/main/docs-kit/references/post-incident-report-template.md) it pairs with lives in the ITSM kit.
- The incident-response plan (what to do while the incident is still live) also lives in the [ITSM docs-kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit); this kit takes over once the fire is out and the write-up starts.

## Licensing

CC BY 4.0. See the [repo root licence note](../README.md#licensing).
