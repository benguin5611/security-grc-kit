---
Artefact type: Procedure
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Annual, or when the risk landscape changes materially
Version: 1.0 (template)
---

# Risk assessment method + report template

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

Risk / threat / vulnerability framing with worked examples, an explicit informal-versus-formal split, the required risk-card fields, and a full formal-assessment structure.

## Introduction: risk, threat, and vulnerability

A **risk** is the potential for an adverse outcome arising from a threat exploiting a vulnerability. It's measured by likelihood and impact on the organisation's objectives, operations, or obligations. Examples: financial loss from a data breach; reputational harm following a publicised outage; regulatory penalties for non-compliance.

A **threat** is any circumstance, actor, or event that could exploit a vulnerability and cause harm, whether intentional (a cyberattack) or unintentional (human error, a natural disaster). Examples: ransomware deployed by a criminal; a staff member accidentally emailing sensitive data; flooding that damages a data centre.

A **vulnerability** is a weakness or flaw in processes, systems, or controls that a threat could exploit, whether technical, procedural, or human. Examples: unpatched software with known flaws; misconfigured access permissions; lack of staff training on data handling.

**Worked example (a compliance-breach risk):**

- **Risk**: legal penalties, reputational damage, or loss of customer trust from non-compliance with a data-protection law.
- **Threat**: a third-party tracker on the website collects personal data without consent, breaching that law's requirements.
- **Vulnerability**: the website lacks an effective consent-management mechanism, allowing unauthorised data collection without informed consent.

## Informal vs. formal risk assessments

Both approaches identify and evaluate risk; they differ in structure, depth, and application.

### Informal risk assessment

A flexible, non-structured approach using general knowledge, experience, and qualitative judgement, with no specific tools, metrics, or formal documentation required.

**Key characteristics:**

- Relies on team discussion, brainstorming, or informal interviews.
- Based on experience and consensus rather than quantitative data.
- Doesn't use formal methodologies (risk matrices, models).
- Useful as a preliminary tool to decide whether a formal assessment is warranted.

**Appropriate when:** you need a quick, high-level read during early planning; the decision is low-stakes or short-timeframe; resources or risk expertise are limited; you're operating in a fast-paced, agile environment where informal decision-making is the norm.

**Limitations:** efficient, but can lack rigour, traceability, and accuracy. If the risk looks complex, high-impact, or regulatory in nature, move to a formal assessment.

### Formal risk assessment

A structured, systematic process using established methodologies and tools, typically with multidisciplinary input, documented for accountability and auditability.

**Key characteristics:**

- Uses specific risk-analysis techniques (risk matrices, probabilistic models, decision trees).
- Produces structured, evidence-based outcomes.
- Often involves collaboration between subject-matter experts, security, and management.
- Results are documented and support governance, assurance, and compliance.

**Appropriate when:** the decision carries significant operational, regulatory, or financial impact; a compliance framework requires it; external stakeholders (regulators, auditors, clients) expect documented risk assessment; the outcome informs strategic planning or a high-impact change (a new system, a cloud migration).

**Benefits:** results you can repeat, and defend to an auditor later.

## Required risk-card fields

Every identified risk, formal or informal, should have a risk card in your risk register with, at minimum:

- Threat
- Vulnerability
- Assignee
- Control owner
- Risk category
- CIA risk type (if applicable)
- Type of non-conformity (if applicable)
- Inherent risk score
- Priority (matching the inherent risk score)
- Risk treatment action
- Target due date (a best-effort target, not necessarily a hard deadline)
- Root-cause analysis
- Control(s) to be implemented, and the corresponding corrective action (if applicable)
- Expected residual risk level after treatment

## Conducting an informal risk assessment

1. **Identify relevant risks**: using your defined risk categories, identify potential risks to assets, systems, people, or operations, through team discussion or prior knowledge.
2. **Analyse threat scenarios**: for each risk, consider realistic threats and give a qualitative estimate of likelihood and impact, using contextual knowledge, past incidents, or known weaknesses.
3. **Evaluate risk**: combine likelihood and impact using your organisational risk matrix to prioritise and inform treatment.
4. **Raise the risk**: submit it through your normal process; it should be reviewed by the security/GRC lead, who decides whether it needs formal evaluation and tracking.
5. **Define corrective actions**: where appropriate, define how the risk will be addressed, proportionate to its level: mitigation through new/revised controls, avoidance, transfer, process improvement, tooling, or training.
6. **Monitor and track**: track risk and treatment status through your governance cycle; retire a risk only once the possibility of it being realised is genuinely zero, not just "handled for now."

## Conducting a formal risk assessment

### 1. Define the assessment foundation

Document, in the report:

- **Context**: the business, regulatory, and technological context; why the assessment is required (a regulatory obligation, a change in threat landscape, a scheduled reassessment); whether it's an initial or subsequent review.
- **Purpose**: the objective is to identify risks to the confidentiality, integrity, availability, or privacy of the systems and processes in scope, informing risk-acceptance, mitigation, and planning decisions.
- **Scope**: the boundaries are systems, teams, processes, and third-party dependencies in scope; explicit exclusions and why (e.g. environmental threats already covered by a cloud provider's own assurances).
- **System description**: a high-level technical and functional overview of what's in scope: architecture, deployment model, integrations, and why it matters to the business or its customers.
- **Objectives**: what the assessment is meant to achieve: identifying risks to business/security objectives, recognising threats across internal and external dependencies, surfacing control weaknesses, informing treatment plans.

### 2. Define the methodology and tools

Document the structured approach:

- Use your organisation's risk-management methodology; align it with a recognised framework such as ISO 31000 or NIST SP 800-30.
- Select qualitative and/or quantitative techniques proportionate to complexity and available data.
- Reference the tools you'll actually use (workflow tracking, reporting, security-testing platforms).
- Where useful, gather operational insight through structured stakeholder interviews.

### 3. Identify and classify assets

Document the information assets in scope: systems, APIs and data-exchange layers, customer data, internal documentation and intellectual property, and the people/roles critical to operating them. Classify each by its confidentiality, integrity, and availability requirements (see the [Information Asset Rating Standard](../standards/information-asset-rating-standard.md)).

### 4. Identify threats and vulnerabilities

For each asset:

- Identify threat sources (adversarial, accidental, structural).
- Document threat events: social engineering, denial of service, insider mishandling, software vulnerabilities.
- Identify vulnerabilities through technical testing, configuration review, and process walkthroughs.

Link every threat and vulnerability clearly to the assets and business objectives it affects.

### 5. Evaluate risks

For each threat event:

- Rate the likelihood of occurrence, for adversarial and non-adversarial threats separately.
- Rate the likelihood of adverse impact given existing controls, with a structured justification.
- Determine overall likelihood.
- Assess impact using your domain-specific scale.
- Combine likelihood and impact into a risk rating.

Document every scoring decision with reference to actual evidence: logs, audit results, prior incidents, threat intelligence.

### 6. Raise and record risks

For every newly identified risk rated outside your risk appetite, raise a risk card in your register (see "Required risk-card fields" above), meeting your defined acceptance criteria: evidence-based likelihood, impact, treatment notes, and reviewer comments.

### 7. Recommend treatment or acceptance

For non-accepted risks, define corrective actions: technical controls (encryption, segmentation), organisational/process changes, or staff training/third-party support.

If recommending acceptance, justify it with one or more of:

- The cost of mitigation outweighs the expected impact.
- A known change is expected to resolve the issue in the short term.
- The residual risk is within defined thresholds.
- The risk is intentional and strategic (high risk, high reward).

Document and clearly explain every treatment decision.

### 8. Complete and approve the report

Summarise: identification and evaluation outcomes; risk ratings and treatment recommendations; a breakdown by severity and area; assumptions, limitations, and dependencies. Submit for approval by the appropriate senior sponsor(s) after review by whoever coordinates information security day to day.

## Adapt this to your context

- **Size**: a solo practitioner runs the informal assessment as a genuine solo brainstorm; the value is in writing it down and setting a review date, not in simulating a committee.
- **Methodology choice**: ISO 31000 and NIST SP 800-30 are named as examples of recognised risk-management frameworks; use whichever your compliance program or industry actually expects, as they aren't interchangeable in every regulatory context.
- **Compliance program**: if you're pursuing a specific certification, that framework will prescribe minimum content for a formal risk assessment (e.g. ISO 27001's risk treatment plan requirements) beyond what's outlined here; check the current requirements of whichever framework applies.
- **Industry**: some sectors (financial services, healthcare, critical infrastructure) require formal risk assessments at a mandated minimum frequency, or for specific categories of change; check your sector's requirements on top of this method.

**Frameworks referenced** (by family; check current editions): ISO 31000, NIST SP 800-30, ISO/IEC 27001.
