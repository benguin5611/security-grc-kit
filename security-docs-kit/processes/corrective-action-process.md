---
Artefact type: Process
Owner role: Security/GRC lead (Information Security Manager or equivalent), with the relevant Control Owner
Review cadence: Annual
Version: 1.0 (template)
---

# Corrective action management

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The complete lifecycle with proper definitions (major/minor nonconformity, opportunity for improvement, root cause): identify → investigate root cause → determine the action → implement → verify effectiveness.

## Definitions

- **Nonconformity**: a situation where your ISMS (or equivalent management system) fails to meet a requirement of the standard you're aligned to.
  - **Major nonconformity**: a significant deviation indicating a serious deficiency; requires immediate action to correct.
  - **Minor nonconformity**: a deviation that doesn't significantly impact the overall effectiveness of the system; still worth fixing, less urgent.
- **Opportunity for improvement (OFI)**: a situation that could be improved to increase effectiveness, efficiency, or performance, identified through audits, risk assessments, incidents, or feedback, not necessarily a nonconformity at all.
- **Corrective action**: action to eliminate the root cause of a nonconformity (or a potential one) so it doesn't recur. OFIs are tracked through this same workflow for simplicity; see the caveats below.

## 1. Identification

Corrective actions can be identified from any source, including:

- Security reviews
- Team or supplier meetings
- Risk assessments
- Internal and external audits
- Vulnerability scanning and penetration testing
- Information security incidents

Once identified, raise a corrective action record with, at minimum:

- Priority
- Component (what area/control it relates to)
- Type of nonconformity
- Assignee
- Control owner

Recommended additionally: a link to a corresponding risk register entry (if applicable) and a due date.

## 2. Investigation of root cause

The security/GRC lead works with the Control Owner to assess the true root cause, consulting information asset owners, third-party service providers, or external technical specialists as needed. Record the root cause with as much detail as possible; a vague root cause produces a corrective action that doesn't actually prevent recurrence.

## 3. Determination of the corrective action

Once the cause is understood, assess the potential impact of the corrective action itself (how it affects the confidentiality, integrity, or availability of your information assets) and use that to prioritise resourcing and set a remediation timeline.

## 4. Implementation

Design a plan that remediates the true root cause and limits ongoing impact; the expected benefit should justify the resources spent. Record the planned action, the timeline (if applicable), and who's responsible for implementation. Add dated progress updates as work proceeds. The Control Owner should approve the corrective action before it's implemented.

## Exceptions

Where implementing the full corrective action would disproportionately impact normal business operations, an exception may be applied. Before granting one, confirm:

- The exception doesn't apply to a mandatory clause of your compliance framework (e.g. ISO 27001's clauses 4 to 10).
- Reasonable effort has genuinely been made to assess remediation options.
- There's real evidence the proposed remediation would disproportionately impact operations.
- Compensating controls exist to reduce the risk of the unremediated nonconformity.

Document any approved exception in your policy-exceptions log with a rationale.

## 5. Verification of effectiveness

Once the Control Owner has implemented the corrective action and notified the security/GRC lead, the lead reviews its effectiveness:

- **If the nonconformity hasn't been adequately addressed**: require a redesign, or consider a policy exception (above).
- **If it has**: record the date and outcome of the review, and close the corrective action.

## Adapt this to your context

- **Regulatory notification obligations**: if you operate in a regulated sector, a "material" nonconformity that can't be remediated in a "timely manner" may trigger a mandatory notification to your regulator, on a specific clock; this varies significantly by regulator and jurisdiction (e.g. financial-services prudential regulators commonly have their own material-weakness notification rules). Check your specific obligations; don't assume a generic timeline.
- **Size**: a solo practitioner is both the person raising the corrective action and the one investigating and approving it. Document the reasoning anyway: the root-cause record is what actually prevents recurrence, whether or not a second person ever reviews it.
- **Exceptions discipline**: granting yourself an exception because a fix is inconvenient defeats the entire point of this process; reserve exceptions for genuine disproportionate-impact cases, evidenced, not preference.
- **OFIs in this workflow**: ISO 27001 keeps corrective action (clause 10.2, eliminating the cause of a nonconformity) separate from continual improvement (clause 10.1, where OFIs sit). Running OFIs through this same lifecycle is a deliberate simplification for a lean function; keep them labelled as OFIs so the two streams can be split out if an auditor wants the distinction kept clean.

**Frameworks referenced**: ISO/IEC 27001 (the nonconformity/corrective-action clauses this lifecycle is designed to satisfy).
