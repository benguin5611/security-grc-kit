---
Artefact type: Process
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Per engagement; the model itself reviewed annually
Version: 1.0 (template)
---

# Third-party / service-provider security risk model

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The quantitative model, in its proper home: CIA criticality × jurisdiction rating × adverse-history rating → a scored overall risk rating with banded thresholds and an escalation trigger. This is the security-grade version of the operational vendor check (Software Onboarding & Vendor Due Diligence) in the companion [ITSM docs-kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit); that kit runs the check, and the scoring model behind it lives here.

## Process

1. **Request received**: a vendor onboarding request is raised, including purpose, business justification, whether it's a new or replacement solution, estimated cost, vendor details, data sensitivity, and access requirements.
2. **Preliminary suitability check**: review for business relevance, duplication with existing tools, and vendor viability; a quick financial sanity check; check for obvious security or compliance red flags.
3. **Risk classification**: rate the vendor's Confidentiality, Integrity, and Availability impact, and assign a sensitivity rating, per the [Information Asset Rating Standard](../standards/information-asset-rating-standard.md#service-provider-risk-rating).
4. **Score jurisdiction and adverse history**, and calculate the Overall Risk Rating using the same standard's scoring tables.
5. **Escalate if High or Extreme**: an Overall Risk Rating of High or Extreme requires sign-off from the security/GRC lead before proceeding.
6. **Security and compliance assessment**:
   - For all vendors: review available documentation on encryption, access control, authentication (SSO/MFA), data handling, privacy policy, and retention.
   - For vendors rated Critical on Information Security Criticality: request an ISO 27001 certification and/or a SOC 2 Type II attestation report, or a completed supplier evaluation questionnaire; assess the security documentation you get back for gaps and compensating controls.
7. **Approval and documentation**:
   - If approved: attach completed questionnaires/certifications to the request; file supporting documentation somewhere durable; add the vendor to your asset register (Tier 1 supplier tab if applicable); grant and record any user access; implement any required allowlisting; close the request once the register is updated.
   - If rejected: document the rationale, provide feedback to the requester, and close the request.

## Adapt this to your context

- **This process defers its scoring model entirely to the Information Asset Rating Standard**: read that artefact's own "Adapt this to your context" section too; the jurisdiction/adverse-history bands and thresholds aren't a regulatory requirement, and a specific compliance program or customer contract may prescribe its own third-party risk methodology instead.
- **Government vs non-government suppliers**: private-sector vendors commonly evidence themselves with SOC 2 or an ISO 27001 Statement of Applicability; a government supplier, or a vendor selling into government, may instead hold a government-specific assessment (e.g. Australia's IRAP, the US's FedRAMP) that isn't a drop-in substitute for the private-sector evidence types above.
- **Size**: a solo practitioner runs this whole flow alone for most vendors; the escalation step exists precisely so that the High/Extreme cases still get a deliberate second look, even if that "second look" is your own return visit with fresh eyes and a night's sleep between the scoring and the decision.

**Frameworks referenced** (by family; check current editions): ISO/IEC 27001 (Statement of Applicability), SOC 2 (Trust Services Criteria).
