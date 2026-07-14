---
Artefact type: Standard
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Annual
Version: 1.0 (template)
---

# Information asset rating standard

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here), a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The CIA-based asset-rating method the risk assessment and vendor-risk work both depend on, a consistent way to categorise, prioritise, and manage information assets so that security measures, access controls, and investment decisions align with what actually matters.

## Information categories

- **Documents**: any written, printed, electronic, or recorded material: reports, emails, spreadsheets, manuals. Created, revised, and used as part of day-to-day operations; multiple people can access and change them.
- **Records**: a specific type of document holding evidence of an event, transaction, decision, or activity: unique, final, and unchangeable representations of what happened. Typically subject to specific retention and disposal schedules, and may be needed for legal, compliance, audit, or historical purposes.

## Information impact rating (the CIA triad)

- **Confidentiality**: maintaining secrecy and privacy so only authorised parties can access the information.
- **Integrity**: keeping data accurate, consistent, and unaltered through storage, processing, and transmission.
- **Availability**: ensuring authorised users have timely, uninterrupted access when they need it.

### Determining impact

Impact is the potential harm from unauthorised disclosure, modification, destruction, or loss of availability. Rate each of Confidentiality, Integrity, and Availability individually as High (3), Medium (2), or Low (1), then combine:

**I = Confidentiality × Integrity × Availability**

For example: Confidentiality = High (3), Integrity = Low (1), Availability = Medium (2) → 3 × 1 × 2 = 6.

The resulting score maps to one of four overall impact levels (a four-level scale gives more granularity than three):

| Confidentiality | Integrity | Availability | Result | Overall Impact |
| --- | --- | --- | --- | --- |
| 1 | 1 | 1 | 1 | Negligible |
| 1 | 1 | 2 | 2 | Low |
| 1 | 2 | 1 | 2 | Low |
| 2 | 1 | 1 | 2 | Low |
| 1 | 1 | 3 | 3 | Low |
| 1 | 3 | 1 | 3 | Low |
| 3 | 1 | 1 | 3 | Low |
| 1 | 2 | 2 | 4 | Low |
| 2 | 1 | 2 | 4 | Low |
| 2 | 2 | 1 | 4 | Low |
| 1 | 2 | 3 | 6 | Medium |
| 1 | 3 | 2 | 6 | Medium |
| 2 | 1 | 3 | 6 | Medium |
| 2 | 3 | 1 | 6 | Medium |
| 3 | 1 | 2 | 6 | Medium |
| 3 | 2 | 1 | 6 | Medium |
| 2 | 2 | 2 | 8 | Medium |
| 1 | 3 | 3 | 9 | Medium |
| 3 | 1 | 3 | 9 | Medium |
| 3 | 3 | 1 | 9 | Medium |
| 2 | 2 | 3 | 12 | High |
| 2 | 3 | 2 | 12 | High |
| 3 | 2 | 2 | 12 | High |
| 2 | 3 | 3 | 18 | High |
| 3 | 2 | 3 | 18 | High |
| 3 | 3 | 2 | 18 | High |
| 3 | 3 | 3 | 27 | High |

| Level | Description |
| --- | --- |
| **Negligible** | Negligible impact on business operations, external service offerings, or the CIA of information. |
| **Low** | Supports efficient operations but no direct impact on external service offerings or CIA. |
| **Medium** | Supports everyday operations and indirectly impacts external service offerings or CIA. |
| **High** | Supports core operations and directly impacts external service offerings or CIA. |

## Information sensitivity categorisation

Sensitivity measures how important or confidential information is to the organisation, and the consequences if it were compromised, disclosed, altered, or made unavailable. Example classification scheme:

| Classification | Description | Example content |
| --- | --- | --- |
| **Public (1)** | Requires no marking or handling control; normal version control/retention may still apply. | Public product information, general company announcements, published research, job postings |
| **Limited Distribution (2)** | Disclosure likely has an insignificant or minor impact. | Internal procedures, non-restricted internal communications, draft reports for internal review |
| **Confidential (3)** | Disclosure likely has a moderate-to-major impact: reportable data breaches, degraded trust, remediation costs. | Resourcing plans, unpublished financials, personally identifiable information, sensitive supplier agreements |
| **Highly Confidential (4)** | The most restrictive tier; disclosure likely causes severe impact: significant regulatory issues, brand damage, or material financial loss. | Proprietary source code, penetration-test results, trade secrets, strategic plans, credentials and encryption keys |

When rating a **web/software application or plugin**, classify based on the information it processes or has access to, not the availability of the application itself. When rating a **vendor or service provider**, classify based on the sensitivity of the information they'll access or handle on your behalf.

## Relationship between sensitivity and impact

Related but distinct: sensitivity assesses importance/confidentiality; impact evaluates the consequence if compromised. Highly sensitive information isn't automatically high-impact if exposed: customer contact details might be sensitive but low-impact if disclosed, while unpublished R&D data could be both sensitive and severely impactful if leaked, since it harms competitive position.

## Information criticality rating

Criticality is the product of sensitivity and impact, used to prioritise assets by relative importance:

**C = Sensitivity × Impact**

| Sensitivity ↓ / Impact → | Negligible | Low | Medium | High |
| --- | --- | --- | --- | --- |
| **Highly Confidential** | Medium | High | Critical | Critical |
| **Confidential** | Medium | High | High | Critical |
| **Limited Distribution** | Low | Medium | High | High |
| **Public** | Low | Low | Medium | Medium |

Higher criticality values mean an asset needs more attention, stronger protection, and more resource allocation.

## Service provider risk rating

When assessing a vendor or service provider, combine the Information Security Criticality rating above with two further dimensions (**Jurisdiction** and **Adverse History**) into an **Overall Risk Rating**. An Overall Risk Rating of High or Extreme requires escalation to the security/GRC lead before proceeding with the engagement.

### Jurisdiction rating

Combines data-sovereignty considerations with modern-slavery/supply-chain risk:

| Rating | Criteria |
| --- | --- |
| **Lowest** | Vendor is domiciled, and data is hosted, in your own jurisdiction. |
| **Low** | A jurisdiction with a recognised data-adequacy finding relative to yours, and no cross-border data movement of concern. |
| **Medium** | An OECD jurisdiction outside that adequacy group, or the vendor uses sub-processors in higher-risk locations. |
| **High** | The vendor or a material sub-processor operates somewhere with elevated modern-slavery prevalence, weaker data-protection law, or known state-access regimes. |
| **Extreme** | The vendor or a material sub-processor is in a recognised high-risk jurisdiction with no compensating contractual or technical controls. |

### Adverse history rating

Review the last 36 months, using adverse-media search, regulatory registers, and vendor trust centres as sources:

| Rating | Criteria |
| --- | --- |
| **Lowest** | No adverse findings; an established vendor with a clean record. |
| **Low** | Minor findings only: operational issues with no security or ethical impact. |
| **Medium** | One notable incident handled well with a public post-mortem, or unresolved minor compliance findings. |
| **High** | A material breach, regulatory action, ongoing litigation, a pattern of incidents, or an ownership/control change that raises questions. |
| **Extreme** | Active enforcement action, an unresolved major breach, a sanctioned entity, or credible allegations of modern slavery in the supply chain. |

### Overall risk rating

**Overall Risk Rating = Information Security Criticality × Jurisdiction Rating × Adverse History Rating**

| Dimension | Lowest | Low | Medium | High | Extreme/Critical |
| --- | --- | --- | --- | --- | --- |
| Information Security Criticality | N/A | 1 | 2 | 3 | 4 |
| Jurisdiction Rating | 1 | 2 | 3 | 4 | 5 |
| Adverse History Rating | 1 | 2 | 3 | 4 | 5 |

| Score | Overall Risk Rating |
| --- | --- |
| 1-4 | Lowest |
| 5-12 | Low |
| 13-27 | Medium |
| 28-60 | High |
| 61-100 | Extreme |

## Adapt this to your context

- **The multiplicative impact score is a known weakening**: multiplying the three CIA ratings lets one high rating wash out, so an asset rated High on confidentiality but Low on integrity and availability (a credentials store, say) comes out Low overall. NIST-style categorisation takes the highest of the three ratings instead; use that high-water mark if any of your assets concentrate their value in a single dimension.
- **Classification labels**: "Public / Limited Distribution / Confidential / Highly Confidential" is one reasonable scheme; some compliance programs mandate their own labels or a different number of tiers. Use whichever your framework or contracts require if it differs from this.
- **The jurisdiction/adverse-history bands** are a starting scoring model rather than a regulatory requirement; if your compliance program or a specific customer contract prescribes its own third-party risk methodology, that one governs, so adapt the bands here to match rather than running two incompatible models.
- **Size**: a solo practitioner can run this scoring alone for most vendors; reserve the "escalate to the security/GRC lead" step in the High/Extreme band for genuinely material engagements, since escalating everything defeats the point of having a threshold.

**Frameworks referenced**: NIST FIPS 199 (the source of the low/moderate/high impact-level concept this model builds on), as applied by NIST SP 800-60 (which maps information types to those impact levels); ISO/IEC 27001 Annex A's asset-management and supplier-relationship objectives.
