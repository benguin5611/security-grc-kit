---
Artefact type: Reference (index)
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Annual
Version: 1.0 (template)
---

# Researcher-facing security

> Part of the [security-docs-kit](../../README.md#before-you-rely-on-anything-here), a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer, and each artefact's own "Adapt this to your context" section, before relying on it.

The three artefacts a security function needs to run a credible, low-friction vulnerability-disclosure channel:

- [PGP key management](pgp-key-management.md): the lifecycle for the key that lets researchers encrypt sensitive reports to you.
- [Vulnerability disclosure procedure](vulnerability-disclosure-procedure.md): the internal workflow for triaging, remediating, and closing out what comes in.
- [Report a vulnerability (public-facing template)](report-a-vulnerability-template.md): what you'd actually publish, e.g. linked from your `security.txt`.

These three are meant to work together: the public template tells a researcher how to report and what to expect; the internal procedure is what actually happens once a report lands; PGP key management is the mechanics that let a report contain sensitive detail safely in transit.
