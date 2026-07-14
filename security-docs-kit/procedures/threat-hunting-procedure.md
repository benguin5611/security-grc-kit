---
Artefact type: Procedure
Owner role: Security/GRC lead, or whoever owns threat detection
Review cadence: Reviewed after every hunt; the method itself reviewed annually
Version: 1.0 (template)
---

# Threat hunting procedure

> Part of the [security-docs-kit](../README.md#before-you-rely-on-anything-here), a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The full hunt lifecycle, and the reason this is a *security* discipline rather than an IT one: it starts from a hypothesis about an adversary, rather than a ticket about a symptom. Throughout the hunt, careful planning and attention to detail matter; document every step so the process is repeatable, whether by you next time or by someone else.

## 1. Organise the hunt

Inventory your critical assets (endpoints, servers, applications, services) so you understand what you're protecting and what threats each is most exposed to. Determine each asset's location, who has access, and how that access gets provisioned.

Then define your priority intelligence requirements: questions about the threats most relevant to your actual environment. For example, for a remote or hybrid workforce:

- To which threats are remote devices most vulnerable?
- What evidence would those threats leave behind?
- How would you determine if an employee's account or device is compromised?

## 2. Plan the hunt

Set the parameters before you start:

- **State your purpose**: why this hunt, and which threat(s) it targets, driven by your priority intelligence requirements.
- **Define the scope**: your assumptions and hypothesis, based on what you already know. Narrow the scope by working out what evidence would actually surface if the threat you're hunting for were present.
- **Understand your limitations**: what data you can access, what you have the resources to analyse, and how much time you have.
- **Set a realistic deadline.**
- **Determine exclusions**: environments or contractual relationships that constrain where you can hunt.
- **Understand legal and regulatory constraints.** You can't break the law, even when hunting for bad actors.

## 3. Use the right tools for the job

The right tools depend on your asset inventory and hypothesis. If you're looking for a potential compromise, a SIEM and investigative tooling help you review logs and check for leaks. A non-exhaustive list of categories worth having:

- Threat intelligence feeds and investigative portals
- Search engines and web-crawling tools
- Information from security vendors and antivirus providers
- Government and industry advisories
- Public security research: blogs, news, and publications
- SIEM, SOAR, investigative, and OSINT tooling

## 4. Execute the hunt

Keep it simple: follow the plan point by point to avoid diversions. Execution happens in four phases:

1. **Collect**: the most labour-intensive part, especially with manual collection methods.
2. **Process**: compile the data into an organised, readable format others can review.
3. **Analyse**: work out what the findings actually reveal.
4. **Conclude**: if you find a threat, do you have data to support its severity?

## 5. Conclude and evaluate the hunt

Before starting the next hunt, review this one:

- Was the hypothesis appropriate?
- Was the scope narrow enough?
- Did you collect useful intelligence, or could the process have been better?
- Did you have the right tools?
- Did everyone follow the plan?
- Did leadership feel able to raise questions, and did they have the information they needed?

## 6. Report and act on findings

Check whether your data supports the hypothesis. If there's no evidence of the issue you were hunting for, evaluate whether there were gaps in the analysis before concluding it isn't present; for example, you may have checked logs for a compromise but not checked for leaked data elsewhere.

## Adapt this to your context

- **Size**: a solo practitioner runs every phase themselves; the discipline of writing the plan down before executing still matters, since it's what makes the hunt repeatable and its conclusion defensible later.
- **Tooling maturity**: the tool categories above assume you have *some* logging and investigative capability. If you don't yet, the first hunt-worthy finding might simply be "we can't currently hunt for X because we don't collect the data that would show it"; that's a legitimate, useful conclusion, and a corrective action in its own right.
- **Regulated industries**: some sectors expect a documented, recurring threat-hunting cadence as part of a broader security program (not just ad hoc hunts); check whether your compliance program requires that.

**Frameworks referenced**: none specific; this method is broadly consistent with general threat-hunting practice (hypothesis-driven hunting, the collect/process/analyse/conclude execution model) rather than any single named framework.
