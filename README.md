# security-grc-kit

Vendor-neutral documentation for running a security and GRC function: the layer model, front matter, and cross-referencing discipline a real ISMS runs on, written from scratch to be organisation-agnostic and forkable by anyone building a program.

## Why this exists

Most public security documentation is either a vendor's marketing collateral or a single leaked policy with no context. This repo is a coherent *documentation system*, organised the same way a real security function's documentation estate is, so the structure itself is reusable, not just the individual files.

This is original documentation, written for public use. It doesn't describe any specific organisation's actual configuration, and no organisation-specific names, figures, tenants, vendors, or internal identifiers appear anywhere in this repo (in docs, examples, or commit history). See [Licensing](#licensing) below.

## Before you rely on anything here

**This kit is designed to get a lean security/GRC function (a solo practitioner or a small team building a program from scratch) from nothing to something defensible, fast. It is a starting point for building a compliance program, and it is not designed to be bulletproof.**

- Every artefact is deliberately simplified to be usable without a large team or an existing GRC platform behind it. That means some choices are pragmatic defaults for that context, not necessarily the most rigorous option a larger, better-resourced function would choose.
- Some content may diverge, intentionally or otherwise, from what a specific standard, framework, contract, or auditor expects. Each artefact's own caveats section is where that gets called out; it isn't optional reading.
- Don't put anything here in front of an auditor, regulator, customer, or board as a certified or audit-ready control without reviewing and adapting it yourself first.
- Where a specific compliance program, contract, or regulator requires something stricter than what's written here, that requirement wins. This kit is a floor to build from, with room to grow well beyond it.

## The documentation model

Every artefact in this kit (and its companion, the [ITSM documentation kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit)) is organised by altitude and sponsorship rather than topic. This layering *is* the value: it is a general-purpose way to structure operational documentation for any function, and ISO 27001 / an ISMS is just one prominent use case for it.

| Layer | Altitude | Owned by | Answers |
|---|---|---|---|
| **Policies** | Strategic, deliberately generic | Executive-sponsored | Why does this function exist, and what does it commit to? |
| **Plans & Standards** | Tactical | CISO / Information Security Manager | *Plans* say how a policy will be achieved and by when. *Standards* set per-control directives, split into **Requirements** (must/shall) and **Guidelines** (should/may/can). |
| **Processes & Procedures** | Implementation, changes often | Team leads / operators | A *Process* is input → sub-process → output (the workflow). A *Procedure* is the checklist for how a task in that process is actually done. |
| **Registers** | Operational record | Whoever owns the data | The listings that track value, location, sensitivity, criticality, ownership, risk, and decisions. |
| **References** | Supporting material | n/a | Anything that fits no other layer: questionnaires, charters, a Statement of Applicability. |

The **must/should/may verb mapping** in the Standards layer is the detail most generic security documentation gets wrong or skips entirely: a Standard that doesn't distinguish a mandatory control from a recommended one isn't actually auditable. The standards in this kit are templates; make that split explicit when you adapt them to your own program.

Artefacts in these layers (the standards, processes, procedures, and references in `security-docs-kit` and `soc2-kit`) carry consistent front matter stating artefact type, owner role, version, and review cadence, so a reader can tell at a glance what altitude they're reading at and how current it is.

## What's here

Five kits, each usable on its own:

- [`security-docs-kit`](security-docs-kit/): the security/GRC operator's runbook (threat hunting, risk assessment, corrective actions, access audits, third-party risk, researcher-facing security).
- [`iso27001-controls-kit`](iso27001-controls-kit/): implementation guidance and evidence prompts for all 93 ISO/IEC 27001:2022 Annex A controls, plus a Statement of Applicability generator.
- [`soc2-kit`](soc2-kit/): a SOC 2 to ISO 27001:2022 crosswalk, plus system description and management assertion templates.
- [`incident-kit`](incident-kit/): a portable incident-documentation method (PIR guide, severity rubric, source-reading discipline, customer-comms structure).
- [`agent-guardrails`](agent-guardrails/): a permission baseline and per-rule rationale for AI coding agents (Claude Code, Amp).

## Relationship to the ITSM kit

This repo and [benguin5611/ITSM](https://github.com/benguin5611/ITSM)'s `docs-kit/` are two audience-scoped halves of one documentation system, split by **audience** rather than topic:

- **ITSM kit** → a solo IT operator / department of one. Ships the operational checklist/template.
- **This repo** → a security/GRC practitioner. Ships the method/model/analysis behind it.

Where both touch the same topic (access management, risk, vendor due diligence, incident response), the register or template lives in the ITSM kit and the procedure or method lives here; each README cross-references the other rather than forking the same content twice.

## Licensing

- **Documentation** (this kit's Markdown and templates): © 2026 Ben Jackson ([benguin5611](https://github.com/benguin5611)), licensed under [CC BY 4.0](LICENSE): attribution required, commercial and derivative use allowed. MIT is written for software; CC BY 4.0 is the better fit for prose and templates.
- **Bundled code** (the `iso27001-controls-kit` Statement of Applicability generator): [MIT](iso27001-controls-kit/soa-generator/LICENSE), in its own subfolder, scoped separately from the documentation licence.

## Contributing

See [CONTRIBUTING.md](.github/CONTRIBUTING.md). Security issues: see [SECURITY.md](.github/SECURITY.md).
