# iso27001-controls-kit

A generic ISO/IEC 27001:2022 implementation kit: per-Annex-A-control implementation guidance and evidence prompts for all 93 controls, plus a Statement of Applicability (SoA) generator that turns a YAML control list into a formatted spreadsheet.

## Why this exists

Most public ISO 27001 content is either a paid consultant's sales page or a bare list of control titles with no implementation depth. This kit is the middle ground: genuinely useful, vendor-neutral guidance for each of the 93 Annex A controls (what it requires in plain language, how a lean team actually implements it, and what an assessor or auditor would expect to see as evidence), plus a small, real tool for the one artefact every ISMS eventually has to produce: the Statement of Applicability.

## Before you rely on anything here

**This kit gives a lean security/GRC function a genuinely useful starting point for an ISO 27001 implementation. It is not a substitute for a qualified lead auditor, and it is not designed to be bulletproof.** See the [repo-level disclaimer](../README.md#before-you-rely-on-anything-here) for the full statement; it applies here too, with two additions specific to this kit:

- **ISO/IEC 27001:2022's official control text is copyrighted by ISO** and is not reproduced here; every "what it requires" line is an independent paraphrase of the control's intent, not the standard's own wording. Buy the standard from ISO or your national standards body if you need the authoritative text for a certification audit.
- **Control numbering, structure, and even control content can change between standard revisions.** This kit reflects the 2022 revision (93 controls across four themes: Organizational, People, Physical, Technological; replacing the 2013 revision's 114 controls across 14 domains). Confirm you're implementing against the current edition before relying on the numbering here.

## What's here

| Artefact | Covers |
|---|---|
| [controls/organizational-controls.md](controls/organizational-controls.md) | A.5, 37 controls: policy, roles, supplier relationships, incident management, business continuity, compliance |
| [controls/people-controls.md](controls/people-controls.md) | A.6, 8 controls: screening, employment terms, awareness training, remote working |
| [controls/physical-controls.md](controls/physical-controls.md) | A.7, 14 controls: perimeters, entry, equipment, media, disposal |
| [controls/technological-controls.md](controls/technological-controls.md) | A.8, 34 controls: endpoints, access, cryptography, operations, networks, secure development |
| [soa-generator/](soa-generator/) | A YAML-in, spreadsheet-out Statement of Applicability generator |

Each control entry follows the same three-part structure: **what it requires** (a plain-language paraphrase), **implementation guidance** (concrete, actionable bullets), and **evidence an assessor would want to see** (the artefact types a real assessment actually asks for).

## The Statement of Applicability

An SoA is the single document every ISO 27001 assessment starts from: for every Annex A control, is it applicable to this organisation, and if not, why not? [soa-generator/](soa-generator/) takes a YAML file listing each control's applicability, justification, implementation status, and owner, and produces a formatted spreadsheet ready to hand to an auditor; see that folder's own README for usage.

## SOC 2 and ISO 27001 together

If you're running both an ISO 27001 ISMS and a SOC 2 report (common if you sell into enterprise customers on both sides of the Atlantic, or into any customer whose procurement team asks for either), most of your evidence overlaps. See the companion [soc2-kit](../soc2-kit/) for a full crosswalk from every SOC 2 Trust Services Criterion to the ISO 27001:2022 controls that typically satisfy it, plus fill-in-the-blank templates for a SOC 2 system description and management assertion, so you're not maintaining two disconnected evidence sets for the same underlying controls.

## How to use this kit

1. Read through all four control files once, end to end, before starting your SoA. Several controls only make sense in light of others (e.g. A.5.9 Inventory of assets underpins A.5.12 Classification, which underpins half of the Technological theme).
2. For each control, decide applicability using your own risk assessment, not by defaulting every row to "yes". A control genuinely inapplicable to your business (e.g. A.8.30 Outsourced development, if you never use one) should be marked not applicable with a clear justification, not forced to fit.
3. Fill in the [SoA generator](soa-generator/)'s YAML file as you go, and generate the spreadsheet whenever you need a current snapshot. Don't hand-maintain a separate spreadsheet that can drift out of sync with your actual implementation notes.
4. Treat "Evidence an assessor would want to see" as a checklist to build toward, not a retrospective description. The strongest evidence pairs a policy citation ("the document that says we do X") with a live artefact proving it happened ("the ticket, log, or screenshot showing X actually occurred, on a specific date, reviewed by a named role").

## Licensing

- **Documentation** (the four control files, this README): [CC BY 4.0](../LICENSE); see the [repo root licence note](../README.md#licensing).
- **The SoA generator code**: MIT; see [soa-generator/LICENSE](soa-generator/LICENSE). Code and documentation are scoped separately, each under the licence appropriate to its content type.
