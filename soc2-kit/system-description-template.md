---
Artefact type: Reference
Owner role: Information Security Manager, with input from Engineering leadership
Review cadence: Per audit period (typically every 6 to 12 months), plus whenever the system changes materially
Version: 1.0 (template)
---

# SOC 2 system description template

> Part of [soc2-kit](README.md#before-you-rely-on-anything-here). Read that disclaimer before relying on this template.

A SOC 2 report's "description of the system" is the document your auditor and your customers actually read to understand what you run and how you protect it. This template follows the structure a SOC 2 Type II system description conventionally uses, based on the AICPA's description criteria (DC section 200). It's a skeleton to fill in with your own organisation's real detail, not a document to publish with the placeholders left in.

**This is a structural template only.** Every bracketed placeholder below needs your organisation's actual, current information. Do not guess, copy an example from elsewhere, or leave a placeholder in a document you give to an auditor or a customer.

## Examination information

| Field | Your organisation's answer |
|---|---|
| Company name | `[legal entity name]` |
| Trading name (if different) | `[trading name, or "N/A"]` |
| Company registration number | `[your jurisdiction's equivalent, e.g. ABN, EIN, company number]` |
| Registered address | `[registered address]` |
| Scope of services | `[one or two sentences describing what the system does and for whom]` |
| Service auditor | `[the accredited firm performing the examination]` |
| Examination standard | `[e.g. ISAE 3000, AICPA description criteria section 200, AICPA trust services criteria section 100]` |
| Report type | `[SOC 2 Type I or Type II]` |
| Examination period | `[start date] to [end date]` |
| Applicable Trust Services Criteria | `[tick whichever of Security, Availability, Processing Integrity, Confidentiality, Privacy apply]` |

## Types of service provided

Describe each distinct product or service the system provides, in plain language, at a level a customer's risk or procurement team can understand without a technical background. For each one, list the specific capabilities it exposes (what a user or an integrating system can actually do).

## Principal service commitments and system requirements

### Service commitments

State the assurances your organisation makes to customers, business partners, vendors, and subservice providers, covering at minimum:
- Security, availability, and confidentiality commitments (what you promise to protect and how).
- Operational functionality commitments (what the service actually does, as described in contracts and public service documentation).
- Regulatory compliance commitments, if your service is positioned to help customers meet specific obligations (e.g. a data protection regime relevant to your market).

### Operational requirements

State the requirements your organisation has established to meet those commitments, including functional and non-functional system requirements, and how third-party providers are monitored to catch failures that could affect your own service delivery.

### System requirements

If your organisation has adopted a formal information security management system (for example, one built on ISO/IEC 27001), name it here and list the requirement categories it drives (context and alignment, leadership and accountability, risk-based planning, operational implementation, monitoring and evaluation, continuous improvement, asset management, risk management, access management, asset protection, operational security, supplier and third-party management, incident response and recovery, compliance and reporting). If you haven't adopted a formal framework, describe the equivalent structure you do use.

## System components

### Infrastructure

Describe, at a generic level appropriate for a public-facing or customer-facing document, how your infrastructure is organised: whether it's self-hosted, hosted with one or more cloud providers, and how responsibility is split between you and any hosting/infrastructure provider under a shared-responsibility model. Describe your approach to geographic distribution and redundancy in terms of the *pattern* (e.g. "distributed across multiple availability zones for resilience"), not the exact provider, region, or account details, if this document or its audience doesn't need that level of specificity.

**Note on sensitivity**: a full, exact infrastructure description (specific cloud regions, specific managed services, specific account structure) is appropriate *inside* a real SOC 2 report shared under NDA with your auditor and vetted customers. It is not something to publish in a public-facing version of this document, or in any generic template. Decide who the audience is before deciding how much specificity belongs here.

### Software

List the categories of software and tooling that build, support, secure, maintain, and monitor your system: for example, application monitoring, identity and access management, infrastructure monitoring, infrastructure-as-code, version control and deployment, intrusion detection, automated patching, data storage, container orchestration, key management, compute, object storage, load balancing, cloud security posture management, secure networking, and customer support. You don't need to name specific vendor products in a generic or public-facing version of this table; describing the *category* of tool is usually sufficient unless the specific product is itself a customer-facing commitment (e.g. you've contractually committed to a specific certified subprocessor).

### People

Describe your organisational structure by function rather than by name: for example, senior management, delivery/engineering leadership, information security, operations, platform engineering, product, quality assurance, and software engineering. State what each function is responsible for.

### Data

**Data lifecycle**: describe the stages data moves through in your system, creation or acquisition, storage, usage or processing, sharing or distribution, archival, and destruction or deletion. Give a generic example of what happens at each stage, without listing real customer data types if this is a public-facing document.

**Data categories**: describe the broad categories of data your system holds (for example, a distinction between data belonging to your direct contractual counterparties versus data processed on their behalf), and the different access/handling rules that apply to each.

**Types of data collected**: list the categories of data your system processes (for example, transaction data, compliance/verification data, user and access data), without listing the literal fields if this is a public-facing document. A real SOC 2 report given to an auditor would list literal fields.

**Supported file types**: list the file formats your system accepts and produces, by product/interface if relevant.

**Personal data and protections**: describe your baseline protections (encryption, access control, monitoring) at the level of principle, not implementation specifics.

**Third-party access and data considerations**: describe how third parties that may access data operate under contractual data-protection obligations, and how you assure yourself of their ongoing compliance (for example, reviewing their own SOC reports or independent audits).

**Boundary definitions**: define the technical boundary of your system precisely. Where does your responsibility start and end for each interface (for example, a web application, an API, a file-transfer mechanism)? What's explicitly excluded (for example, the user's own browser or device, or a client's own on-premises systems)?

### Procedures

Summarise the procedures that make up your internal control environment, organised by the same categories used in your controls matrix (control environment, information and communication, risk assessment, monitoring activities, control activities, logical and physical access controls, change management, system operations, risk mitigation). State how often these are reviewed and what triggers a review outside the normal cadence.

## Applicable Trust Services Criteria and related controls

State which of the five Trust Services Criteria categories apply to your system (Security is always included; Availability, Processing Integrity, Confidentiality, and Privacy apply based on your actual service). Reference your controls matrix (see the companion [SOC 2 to ISO 27001 crosswalk](soc2-iso27001-crosswalk.md)) for the detailed control-to-criterion mapping, rather than repeating it in full here.

## Changes to the system

Describe any changes to the system made during the examination period that are significant enough to affect a reader's risk assessment. If there were none, state that explicitly rather than leaving the section blank.

## System incidents

Describe any security incidents during the examination period that met your own materiality threshold for disclosure, along with their resolution. If there were none, state that explicitly.

## Complementary user entity controls

List the controls your customers (user entities) are expected to implement on their own side for your service's controls to work as designed. This is not a formality: your auditor's opinion is conditioned on these existing. Common categories include:
1. Access management (strong authentication, periodic access reviews, prompt deprovisioning on the customer's side).
2. Data encryption in transit and at rest for anything the customer controls.
3. Input validation on data the customer submits to you.
4. Privacy and confidentiality handling on the customer's side for any personal or sensitive data they choose to submit.
5. Incident management and notification obligations on the customer's side.
6. Anti-malware protections on customer-controlled endpoints that interact with your system.
7. The customer's own compliance with applicable data protection law.
8. Data retention and termination instructions from the customer when an agreement ends.
9. The customer's own monitoring and reporting of suspicious activity on their side of the integration.

State clearly that this list is indicative and that it's each user entity's own auditor's responsibility to assess whether their implementation is adequate.

## Subservice organisations

For each subservice organisation your system depends on (a hosting provider, an identity provider, a source-control platform, an observability platform, an alerting/incident-management tool, a customer-support platform, a secure-networking provider, etc.), describe:
- What service they provide and how it fits into your system.
- Whether you use the **carve-out method** (your description covers your own monitoring of the subservice organisation, and excludes their internal controls from your report's scope, which is the common approach) or the **inclusive method** (their controls are described and tested as part of your own report).
- The relevant internal controls (from your own controls matrix) that address your responsibility for that dependency.
- The Complementary Subservice Organisation Controls (CSOCs) you're relying on them to operate effectively, and where a reader can obtain that subservice organisation's own assurance report (their SOC 2, ISO 27001 certificate, or equivalent) if a valid business need is established.

**Note on sensitivity**: naming your actual subservice organisations, and describing their specific role in detail, is standard and expected inside a real SOC 2 report shared under NDA with your auditor and vetted customers. A public-facing or generic template version of this document should describe categories of dependency ("a cloud infrastructure provider", "an identity provider", "a source control platform") rather than naming the specific vendors, unless disclosing a specific vendor relationship is itself something you've chosen to make public (for example, as a trust/security page commitment).

## Criteria not relevant to the system

If your organisation is a data processor rather than a data controller (you process personal information only as instructed by your customers, and don't interact directly with the data subjects whose information you hold), several Privacy criteria are typically not applicable. For each excluded criterion, state:
- **Control**: the criterion being excluded.
- **Reason for exclusion**: why it doesn't apply to your role (e.g. "the organisation does not directly collect personal information from data subjects; this responsibility sits with our customers as data controllers").
- **Disclosure**: what you do instead (e.g. contractual obligations that place the relevant responsibility on the customer).

## Adapt this to your context

- The exact section list and depth above reflects a SaaS platform's SOC 2 Type II system description. A different business model (e.g. a managed infrastructure provider, a data controller rather than processor) will need different emphasis, particularly in the data and privacy sections.
- If you're preparing your first SOC 2 report, work with your service auditor early on the description criteria; they'll have a current, precise view of what the description needs to satisfy for your specific circumstances, which this generic template can't fully anticipate.
- Keep a clear internal distinction between the version of this document that goes to your auditor (full detail, under NDA) and any public-facing summary you publish (a trust page, a security overview): the latter should describe categories and commitments, not your literal infrastructure and vendor list.

**Frameworks referenced**: AICPA description criteria (DC section 200), AICPA Trust Services Criteria (TSP section 100)
