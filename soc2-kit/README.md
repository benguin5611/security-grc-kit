# soc2-kit

A SOC 2 to ISO 27001:2022 crosswalk, plus fill-in-the-blank templates for a SOC 2 system description and management assertion.

## Why this exists

Most organisations running an ISO 27001 ISMS and pursuing a SOC 2 report end up building two disconnected evidence sets for what's substantially the same underlying set of controls. This kit exists to stop that duplication: a full mapping from every SOC 2 Trust Services Criterion to the ISO 27001:2022 Annex A controls that typically satisfy it, plus templates for the two documents every SOC 2 Type II report needs beyond the controls matrix itself, the system description and the management assertion.

## Before you rely on anything here

**This kit gives a lean security/GRC function a genuinely useful starting point for aligning a SOC 2 report with an existing ISO 27001 ISMS. It is not a substitute for your service auditor's guidance, and it is not designed to be bulletproof.** See the [repo-level disclaimer](../README.md#before-you-rely-on-anything-here) for the full statement; it applies here too, with one addition specific to this kit:

- **The templates here are structural skeletons.** The [examples](examples/) fill them in for a fictional company so you can see a completed version, but a real SOC 2 system description and management assertion describe your organisation's actual, current infrastructure, personnel, and commitments in detail, under the assumption that the document is shared with your auditor and vetted customers, not published publicly. Never publish a filled-in version of these templates that discloses more about your real environment than you intend to make public.
- **The AICPA's Trust Services Criteria and description criteria text is copyrighted by the AICPA.** The crosswalk paraphrases what each criterion asks for; it doesn't reproduce the official wording. If you need the authoritative criterion text for a real engagement, get it from the AICPA or your auditor.

## What's here

| Artefact | Covers |
|---|---|
| [soc2-iso27001-crosswalk.md](soc2-iso27001-crosswalk.md) | Every SOC 2 common criterion (CC1 to CC9) and additional criterion (Availability, Confidentiality, Processing Integrity, Privacy), mapped at the point-of-focus level to the ISO 27001:2022 controls and clauses that satisfy it, with the reasoning for each mapping |
| [system-description-template.md](system-description-template.md) | A fill-in-the-blank template for a SOC 2 system description, following the AICPA description criteria structure |
| [management-assertion-template.md](management-assertion-template.md) | A fill-in-the-blank template for the management assertion that opens a SOC 2 report |
| [examples/](examples/) | Both templates filled in end to end for a single fictional company, so you can see a completed version before writing your own |

## Relationship to iso27001-controls-kit

This kit's crosswalk is built to sit alongside [iso27001-controls-kit](../iso27001-controls-kit/): read that kit's per-control implementation guidance to build out your actual ISO 27001 controls, then use this kit's crosswalk to see which of those same controls also satisfy your SOC 2 obligations, rather than building a second, parallel control set from scratch.

## Licensing

CC BY 4.0, see the [repo root licence note](../README.md#licensing).
