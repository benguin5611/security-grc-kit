---
Artefact type: Reference
Owner role: Chief Technology Officer or equivalent accountable executive
Review cadence: Per audit period
Version: 1.0 (template)
---

# SOC 2 management assertion template

> Part of [soc2-kit](README.md#before-you-rely-on-anything-here). Read that disclaimer before relying on this template.

A SOC 2 report opens with a formal assertion from your organisation's management, stating what you're claiming and for what period. It's a short document, but every sentence in it is a specific claim your auditor will test. This template follows the conventional structure; the bracketed placeholders need your organisation's real, current facts, and the final assertion should be reviewed by whoever will actually sign it, not drafted and signed without their involvement.

**Do not sign or submit a version of this with any placeholder left unfilled.** An assertion with an unresolved bracket in it isn't a draft that got submitted by mistake; it's a formal claim to an auditor with a hole in it.

## Structure

### Title and commitment statement

State that the accompanying system description (see the [system description template](system-description-template.md)) was prepared for a named examination period, based on the applicable description criteria (name the specific edition, e.g. "DC section 200, 2018 Description Criteria for a Description of a Service Organization's System in a SOC 2 Report, in AICPA Description Criteria").

### Purpose statement

State that the description is intended to give report users information to assess risks arising from interacting with your system, including:
- The services provided.
- The system components used to deliver them.
- Your service commitments and system requirements.
- The criteria used to evaluate the design and operation of the system.

### Scope and carve-out statement

If you exclude subservice organisations' own controls from your report's scope (the carve-out method, the common approach), state this explicitly and name the subservice organisations you rely on, or refer to the subservice organisations section of your system description if you're keeping that detail out of the assertion itself. State that complementary controls at those subservice organisations, and complementary controls expected of user entities, are both necessary alongside your own controls to achieve your stated commitments.

### The three assertions

State, to the best of management's knowledge and belief, that:

**a.** The description presents the system as designed and implemented throughout the stated examination period, in accordance with the applicable description criteria.

**b.** The controls stated in the description were suitably designed throughout the examination period to provide reasonable assurance that your service commitments and system requirements would be achieved, assuming your own controls operated effectively, subservice organisations applied their assumed complementary controls, and user entities applied their assumed complementary controls, throughout that period.

**c.** The controls stated in the description operated effectively throughout the examination period to provide reasonable assurance that your service commitments and system requirements were achieved, on the same set of assumptions as (b).

### Closing statement and signature

A brief closing statement connecting the assertion to your organisation's actual commitment to the relevant standard, followed by:

```
Signed:

[Signature]

[Full name]
[Title, e.g. Chief Technology Officer]
```

## Adapt this to your context

- Whoever signs this needs personal, informed confidence in all three assertions; treat obtaining that sign-off as a genuine review step, not paperwork tacked onto the end of the audit process.
- The exact wording of the description-criteria citation, and the specific criteria categories referenced, need to match what your service auditor has actually agreed to examine; confirm the current citation with them rather than assuming last year's wording still applies.
- If your organisation is examined under a different standard's assertion format (for example, a different national equivalent), adapt the structure to match, since the underlying content (what you're claiming, for what period, on what assumptions) is what matters, not this specific template's wording.

**Frameworks referenced**: AICPA Trust Services Criteria (TSP section 100), AICPA description criteria (DC section 200), International Standard on Assurance Engagements (ISAE) 3000
