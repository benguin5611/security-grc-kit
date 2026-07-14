# Cross-linking checklist

An incident's record is only as useful as its weakest link. If the PIR, the tracking ticket, and any customer-facing record don't all point at each other, the next person investigating a related issue finds one artefact and assumes it's the whole story.

## The principle

**Every incident artefact should point at every other artefact.** Not just downward (PIR references the ticket) but across (the ticket references the PIR, the customer comms reference both, and so on). Treat this as a checklist to run explicitly after writing, not something that happens automatically as a side effect of good intentions.

## The checklist

- [ ] The PIR's supporting-documentation section links: the original source discussion, the tracking ticket, any public status update, any customer-facing ticket, and any dedicated communication channel used
- [ ] The PIR's communication section records the public status update's timeline and names the channel used for direct customer communication, if any
- [ ] The tracking ticket carries a comment or field linking back to the PIR, the communication channel, and any customer-facing ticket
- [ ] The tracking ticket's description references the original source discussion and the PIR
- [ ] The PIR's title or identifying metadata includes the tracking ticket's reference, once the ticket exists; don't leave a placeholder in the title after the ticket is created
- [ ] If a new discussion channel is created after the initial write-up (e.g. because new engineering findings emerge later), read it and update the PIR and ticket if it changes scope or root cause

## Why this is worth a checklist, not just good judgement

Under incident-response time pressure, cross-linking is exactly the kind of task that feels optional in the moment and turns out to matter six months later, when someone is trying to work out whether a new issue is a repeat of an old one. Running this as an explicit, separate step, done after the write-up rather than folded into it, is what makes it actually happen consistently rather than depending on whoever's writing that day remembering to do it.

## Adapt this to your context

- The specific artefacts named above (a ticket, a public status update, a customer-facing channel) assume a fairly typical toolset. Substitute your organisation's actual equivalents; the principle (every artefact points at every other one) is what transfers, not the specific tool names.
- A solo operator or very small team might not have a separate customer-facing ticketing system at all. In that case, "cross-link" might just mean one incident record with clearly labelled sections, rather than genuinely separate documents. The discipline still applies: don't let the story live in someone's memory alone.
