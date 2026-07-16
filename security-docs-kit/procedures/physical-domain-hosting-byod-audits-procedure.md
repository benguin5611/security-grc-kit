---
Artefact type: Procedure
Owner role: Security/GRC lead (Information Security Manager or equivalent)
Review cadence: Quarterly (each audit below)
Version: 1.0 (template)
---

# Physical / domain-hosting / BYOD audits

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here): a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

Three periodic security-audit checklists, each quarterly, each cheap to run and easy to let slide if it isn't scheduled somewhere concrete.

## Physical access audit

1. Review the list of staff with physical access (office keys, access cards, door codes).
2. Review the physical-key/card inventory to confirm it's current.
3. Update your asset register with any changes.
4. If access needs to be removed and you rely on a third party (a building manager, an office-services provider) to do it, raise that with them directly.
5. Once complete, have the security/GRC lead review and sign off.

## Domain and web-hosting audit

Review your asset register for all domain registrars and web-hosting vendors in use. For each domain:

- Confirm registration is set to auto-renew, and contact/payment details on file are current.
- Confirm SPF, DKIM, and DMARC DNS records are valid for the domain and its subdomains, and that DMARC aggregate reports are actually being collected and reviewed somewhere (a DMARC-analysis service, generically; several free and paid options exist).
- Confirm DNSSEC is enabled (a public DNSSEC-test tool can verify this).
- Confirm hosting-platform rules are valid (redirects, page rules, WAF rules, etc.).
- Confirm DDoS protection is enabled.
- Review the minimum TLS version in use.
- Confirm `security.txt` is present and current.
- Confirm every DNS record has a comment describing its purpose: an unlabelled record is the one nobody remembers the reason for in two years.
- Check for dangling DNS records (records pointing at a resource you no longer control; a classic subdomain-takeover vector; OWASP's testing guide and your cloud provider's own documentation both cover this).
- Assess the risk of typosquatted domains, look-alike domains that could be used for phishing or brand impersonation (a public typosquat-checking tool can surface candidates). Distinguish genuine risks from domains you've deliberately registered yourself for typosquat protection, and from unrelated third parties who happen to hold a similar-looking domain for a legitimate purpose of their own.

Reflect any changes in your asset register's domains tab, and raise anything concerning with the security/GRC lead.

## BYOD / mobile device audit

Review enrolled personal (BYOD) devices in your MDM for decommissioned, duplicate, or stale entries:

- **Delete** any device that belongs to an offboarded user, or is decommissioned and no longer in use.
- **Identify duplicates**: look for devices matching on details like email address, device name, or serial number, but with a mismatch elsewhere (OS version, last-sync date). A device that hasn't synced in weeks alongside a near-identical entry that synced hours ago is a strong duplicate signal; confirm using the serial number before acting.
- **Identify stale devices**: a device with a different name/OS version but the same user and an old last-sync date, superseded by a newer entry for the same person, is a candidate for removal.
- **When in doubt, don't delete**: escalate to the security/GRC lead rather than guessing.
- **Use "delete", not "wipe", for routine cleanup.** Reserve device wipe for actual offboarding or lost/stolen-device scenarios; wiping a device that's simply a stale duplicate entry could destroy someone's personal data unnecessarily.

## Adapt this to your context

- **Cadence**: quarterly is a reasonable default for all three; a specific compliance program or a particularly dynamic domain/device estate might warrant a shorter cycle.
- **Size**: a solo practitioner runs all three alone; the value of scheduling them (rather than "whenever I remember") is that a domain or device audit is exactly the kind of thing that's invisible until it's a live incident, and easy to defer indefinitely without a forcing function.
- **BYOD policy**: this audit assumes a BYOD program already exists with some MDM enrolment. If you don't allow BYOD at all, this section doesn't apply, but confirm that's actually enforced, not just assumed.

**Frameworks referenced**: none specific; the domain-hosting checklist draws on widely published DNS/email-security best practice (SPF/DKIM/DMARC, DNSSEC, subdomain-takeover awareness) rather than a single named standard.
