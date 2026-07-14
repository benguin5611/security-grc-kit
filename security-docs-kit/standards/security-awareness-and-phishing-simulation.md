---
Artefact type: Standard
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Annual
Version: 1.0 (template)
---

# Security awareness & phishing simulation

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function, not a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

This is the structure for running a security awareness program and phishing-simulation campaign, genericised from tool-specific mechanics down to the pattern: an annual remedial-training track, and a quarterly phishing-simulation cadence with a clicker-to-remedial-training pipeline.

## Annual remedial training campaign

Run one standing campaign per year:

- **Name it clearly and consistently** (e.g. "Remedial Phishing Training \<Year\>") so it's identifiable across years.
- **Runs the full calendar year**: start on the first day of the year, end on the last.
- **Content**: assign whatever phishing-awareness training module your platform provides.
- **Enrolment is automatic and reactive**: anyone who fails (clicks on) a simulated phishing email during the year gets enrolled into remedial training.
- **Exit on completion**: once someone completes the remedial training, remove them from the enrolled group. The campaign should always reflect who currently needs the training, not everyone who's ever needed it.

## Quarterly phishing simulation campaigns

Run one simulation campaign per quarter, each with a defined topic and template:

1. **Create a topic for the year**: a naming convention like "\<Year\> Phishing Campaign" that groups all of that year's simulation templates together.
2. **Select or clone a template for each quarter**, filtering for:
   - **Difficulty**: moderate or above; an obviously fake simulation teaches nothing.
   - **Language**: confirm the language matches your workforce.
   - **Topic relevance**: pick a scenario that's actually plausible for your business (a password-reset lure, a fake invoice, a delivery notification, whatever fits your context).
3. **Configure each quarter's campaign**:
   - **Name**: a consistent pattern (e.g. "Q1 \<Year\>: \<Topic\>").
   - **Audience**: all staff, unless you have a specific reason to scope it down.
   - **Frequency**: one-time per quarter, not recurring within the quarter.
   - **Send window**: spread sends over several working days rather than all at once, so results reflect genuine behaviour rather than a single moment.
   - **Tracking window**: track click/report activity for a defined period after send (a week is reasonable).
   - **Clicker handling**: anyone who clicks gets automatically enrolled into the annual remedial-training campaign above.

## Adapt this to your context

- **Platform-agnostic by design**: this deliberately doesn't name a specific phishing-simulation or training platform. The pattern (annual remedial track plus quarterly simulation cadence plus automatic clicker enrolment) works on any commercial platform or an in-house equivalent. Fill in your own platform's specific admin steps.
- **Size**: a solo practitioner still gets value from running this against a small team, or even just themselves and a handful of colleagues. The discipline of a defined, repeatable cadence is the point, not the headcount.
- **Compliance program**: some frameworks require documented evidence of security-awareness training and phishing-simulation results at a minimum frequency. Check whether quarterly is sufficient for your specific requirements, or whether a different cadence is mandated.

**Frameworks referenced**: ISO/IEC 27001 Annex A's security-awareness and training objectives.
