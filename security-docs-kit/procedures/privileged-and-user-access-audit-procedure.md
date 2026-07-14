---
Artefact type: Procedure
Owner role: Security/GRC lead (Information Security Manager or equivalent), with each System Owner
Review cadence: User access: every 12 months; privileged access on critical systems: every 3 months
Version: 1.0 (template)
---

# Privileged & user access audit

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The periodic attestation that proves access control actually runs, carrying the nuance that makes it genuinely useful: access is justified by *need*, not by arbitrary login recency, so the System Owner (not a stale-account timer) decides what stays.

## The core principle

User and privileged access exist based on business need, not a fixed usage timeframe. A user who hasn't logged into a system in months may still legitimately need their access, for example to avoid a single point of failure on a system with one primary admin. This is why the **System Owner** decides whether access should remain or be revoked, rather than an automated recency rule. A reasonable default: flag anything unused for more than 3 months for the System Owner's explicit decision, rather than auto-revoking it.

## User access audit (every 12 months, all systems)

1. Pull your list of all systems from your asset register, filtered to those that are access-controlled.
2. Create a review task for each system.
3. Confirm with each System Owner: are current users fit for purpose, with no stale permissions? If someone no longer needs access, have the System Owner remove it.
4. Review service accounts too, to confirm they're still fit for purpose.
5. Request evidence from the System Owner (a screenshot or export showing current user access) and attach it to the review record.
6. Update your asset register to reflect any changes.
7. Once every system's review is complete, move the parent review task to a review/approval state.
8. The security/GRC lead reviews the completed review; if it's been done correctly, close it out.

## Privileged access audit (every 3 months, critical systems only)

Same shape, scoped to systems your asset register marks as critical:

1. Pull your list of critical, access-controlled systems from the asset register.
2. Create a review task for each.
3. Confirm with each System Owner that admin/privileged access is fit for purpose and free of stale permissions; remove anything no longer needed.
4. Request evidence (a screenshot or export of current administrator access) and attach it to the review record.
5. Update the asset register.
6. Once complete, move the parent review task to review; the security/GRC lead closes it out once satisfied.

## Adapt this to your context

- **Cadence**: 12 months (user access) and 3 months (privileged access on critical systems) are common baselines rather than a universal mandate; some frameworks or regulators require shorter cycles, or reviews for *all* access rather than just critical-system privileged access. Check what actually applies to you.
- **Size**: a solo practitioner is frequently also the System Owner for many of these systems. Document the confirmation anyway: a dated attestation, even self-issued, is what makes the review demonstrable later; a periodic external or peer spot-check is a reasonable compensating control.
- **Evidence retention**: how long you need to retain audit evidence for is set by your compliance program or regulator, not this procedure; check before purging old review records.

**Frameworks referenced**: ISO/IEC 27001 Annex A's access-control objectives.
