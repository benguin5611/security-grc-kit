# security-docs-kit

The operating documents a lean security or GRC function runs on: vendor-neutral, organised by the same layer model as the rest of this repo.

## Before you rely on anything here

**This kit is designed to get a lean security/GRC function (a solo practitioner or a small team) from nothing to something defensible, fast. It is a starting point rather than a finished compliance program, and it is not designed to be bulletproof.** See the [repo-level disclaimer](../README.md#before-you-rely-on-anything-here) for the full statement; it applies to every artefact below. Each artefact also carries its own "Adapt this to your context" section; that's not optional reading.

## What's here

| Artefact | Layer |
|---|---|
| [Corrective Action Management](processes/corrective-action-process.md) | Process |
| [Third-Party Security Risk Model](processes/third-party-security-risk-model.md) | Process |
| [Threat Hunting Procedure](procedures/threat-hunting-procedure.md) | Procedure |
| [Security Event Response Procedure](procedures/security-event-response-procedure.md) | Procedure |
| [Risk Assessment Method](procedures/risk-assessment-method.md) | Procedure |
| [Privileged & User Access Audit](procedures/privileged-and-user-access-audit-procedure.md) | Procedure |
| [Physical / Domain-Hosting / BYOD Audits](procedures/physical-domain-hosting-byod-audits-procedure.md) | Procedure |
| [Information Security Competence Framework](standards/information-security-competence-framework.md) | Framework |
| [ISMS Change & Monitoring](standards/isms-change-and-monitoring.md) | Standard |
| [Software Security Review Standard](standards/software-security-review-standard.md) | Standard |
| [Information Asset Rating Standard](standards/information-asset-rating-standard.md) | Standard |
| [Security Awareness & Phishing Simulation](standards/security-awareness-and-phishing-simulation.md) | Standard |
| [Researcher-Facing Security](references/researcher-facing-security/) | Reference |

Processes are the cross-functional workflows (input → sub-process → output); procedures are the operational checklists for how a task is actually done, matching the split in the companion ITSM docs-kit.

## Relationship to the ITSM kit

Several of these draw on, or feed, a register that lives in the companion [ITSM docs-kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit), per the audience split documented in the root README:

- **Risk register** and **corrective actions register** are ITSM-kit templates; the [Risk Assessment Method](procedures/risk-assessment-method.md) and [Corrective Action Management](processes/corrective-action-process.md) here are the methods that populate them.
- The [Third-Party Security Risk Model](processes/third-party-security-risk-model.md) here is the security-grade scoring behind the operational Software Onboarding & Vendor Due Diligence check in the [ITSM docs-kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit).

## Licensing

CC BY 4.0; see the [repo root licence note](../README.md#licensing).
