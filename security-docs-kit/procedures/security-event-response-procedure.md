---
Artefact type: Procedure
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Annual
Version: 1.0 (template)
---

# Security event response procedure

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

Triage and log the event → initial analysis and categorisation → collect data and indicators of compromise → decide escalation → remediate → document. Decoupled from any one ticketing tool.

## 1. Identify and log the security event

Triage potential security events: unauthorised access, suspicious activity, IDS/IPS alerts, malware outbreaks, phishing attempts, or data-breach indicators. Log the event in your ticketing system, documenting source, impact, and any preliminary observations.

## 2. Initial analysis and categorisation

Review the event to determine its nature and scope:

- Confirm whether it's a security *event* or escalates to a security *incident*.
- Categorise it by type, urgency, and potential impact.
- If it escalates, hand off to your incident response plan and notify the security/GRC lead.

## 3. Data collection and evaluation

Gather relevant data points:

- URLs, IP addresses, file hashes, email headers, or other indicators of compromise.
- Logs and alerts from monitoring tools.

Analyse using whatever tooling you have available: threat-intelligence lookup services, email-header analysis tools, and your internal monitoring/logging systems (SIEM or IDS).

## 4. Determine escalation and response requirements

Assess severity and decide whether to escalate, based on:

- Scope of impact (isolated system vs. widespread).
- Whether business-critical systems or data are affected.
- Legal or regulatory implications.

If escalating, inform relevant stakeholders and initiate a coordinated response.

## 5. Remediation

Implement appropriate mitigation:

- Contain and isolate affected systems.
- Block malicious content (URLs, files, emails) using whatever platforms you have available.
- Patch vulnerabilities or implement compensating controls.
- Notify affected users or teams if necessary.

## 6. Document actions and lessons learned

| Category | What to capture |
| --- | --- |
| **Event details** | When first detected (date, time, who/what identified it); a clear description of what was observed; which systems, accounts, or data were potentially affected; an initial severity assessment and why. |
| **Initial analysis** | Whether the event was confirmed as a legitimate event or incident; how it was classified (phishing, malware, policy violation, etc.); impact categorisation and urgency. |
| **Data collection and evaluation** | Which logs were reviewed (SIEM, firewall, endpoint protection, cloud services); indicators of compromise identified; any external tools or lookup services used to verify findings. |
| **Escalation and communication** | Who was informed (IT, security, legal, executive) and when; any regulatory or legal obligations triggered (breach notification, evidence preservation) and any advice sought. |
| **Remediation** | Actions taken to contain the threat (access revoked, domains blocked, endpoints isolated); follow-up steps to resolve vulnerabilities; who was notified and what they were told. |

## Adapt this to your context

- **Size**: a solo practitioner is often the person doing every step above. Log it anyway: the record is what turns "I remember dealing with something like this" into an actual pattern you can spot across events.
- **Tooling**: the "data collection and evaluation" step assumes some monitoring/logging exists. If it doesn't yet, the honest answer for a given event may be "we have no way to confirm scope"; that's a real finding, and a candidate for a corrective action.
- **Escalation to incident response**: this procedure covers the *event*, triage through to a decision on whether it's actually an incident. Once it's confirmed as an incident, hand off to your incident response plan; don't run both processes in parallel.

**Frameworks referenced**: none specific; this triage/categorise/escalate shape is broadly consistent with general security-operations practice.
