---
Artefact type: Standard
Owner role: Security/GRC lead, with Engineering and QA as contributing reviewers
Review cadence: Per material software/infrastructure change
Version: 1.0 (template)
---

# Software security review standard

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here), a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

A security review gate for software, applications, or infrastructure changes, integrating security considerations from architecture through to deployment, and confirming legal/regulatory requirements are met.

## Engineering: written

### Description of what's under review

- Clearly describe the software, application, or infrastructure and its purpose.
- List authentication methods used (OAuth, LDAP, MFA, etc.).
- Describe communication protocols (HTTPS, RESTful APIs, SSH, etc.).
- Identify third-party dependencies (databases, cloud storage, identity providers, etc.).

### Security architecture

- **Web application security**: assess against the current OWASP Top 10 categories; document mitigation for each.
- **Cloud infrastructure security** (if applicable): identify potential issues: insecure configuration, injection flaws, improper authentication, CI/CD pipeline weaknesses, insecure secrets storage, network policy gaps, asset-management gaps, missing resource limits, and logging/monitoring gaps. Document mitigations for each.

### Code quality and logging

- Confirm the design follows secure development standards, minimises complexity, and stays maintainable.
- Confirm appropriate supporting documentation exists (README, inline comments).
- Confirm errors are captured securely and informatively, without leaking sensitive data.
- Confirm application telemetry (logs, metrics, traces) is configured to reach your observability stack.

## Engineering + security: interview

### Threat assessment

- **Threat modelling**: use a structured model (e.g. STRIDE) to identify, quantify, and address security risks.
- **Threat analysis**: assess each workflow, component, resource, or application for potential threats; document affected areas, threat types, vulnerabilities, mitigations, and actions.

## QA: written

### Security testing, maintenance, and controls

- **Testing strategy**: define the resources, schedule, test-environment setup, and data needed; cover unit, integration, system, performance, and security testing at minimum.
- **Defect management**: log defects with severity ratings, clear descriptions, and reproduction steps; prioritise by severity and timeline impact.

## Security: written

### Legal and regulatory compliance

- **PII handling**: determine whether the item stores, transmits, or processes personally identifiable information.
- **Compliance review**: confirm secure configuration/design principles are followed, and identify applicable legislation or compliance programs (e.g. a relevant data-protection law, ISO 27001).
- **Repository details**: confirm whether it's a new or existing repository; list any new or modified open-source dependencies and their licences.
- **Security tooling**: confirm relevant security tools are enabled (static analysis, dependency scanning, branch protection, secret scanning).
- **ISMS documentation**: determine whether this change requires updates to ISMS documentation (licensing, continuity plans, incident response plans).

## Adapt this to your context

- **Solo/small team**: the "three roles" structure (Engineering, QA, Security) is often one person wearing three hats. Work through all four sections anyway, in order; the value is in the checklist rather than in having three different people sign off.
- **Threat modelling framework**: STRIDE is named as an example; use whichever structured threat-modelling approach you're already comfortable with; the important part is that it's structured and repeatable rather than the specific acronym.
- **Depth should scale with risk**: a small internal tool doesn't need the same depth of review as a change touching customer data or production infrastructure; use the [Information Asset Rating Standard](information-asset-rating-standard.md) to judge how much rigour a given review actually needs.

**Frameworks referenced** (by family; check current editions): OWASP Top 10, STRIDE threat modelling.
