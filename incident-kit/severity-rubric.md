# Severity calibration

Assess severity before writing anything else. It drives the PIR title, the tracking ticket's priority, and the tone of any customer communication.

| Severity | Label | Criteria |
|---|---|---|
| P1 | Highest | Active security breach, data exfiltration, complete service outage, malicious code execution |
| P2 | High | Customer-visible data corruption, a significant feature outage, a breaking change to an integration or API contract |
| P3 | Medium | Degraded performance, a partial feature failure, internal-only impact |

## Deciding the borderline cases

**P1 vs P2, is there a security dimension?** When an incident sits between the two, ask: was customer data compromised, or could it have been? If the answer is yes, or genuinely uncertain, call it P1. Data-confidentiality risk should never be rounded down to make a quieter incident.

**P2 vs P3, is it customer-visible?** An internal-only degradation that no customer would notice, even if it's operationally annoying, is P3. The moment a customer could plausibly notice or be affected, it's at least P2.

**When multiple criteria conflict** (e.g. a low-likelihood event with a very high potential impact), rate on the worst plausible outcome rather than the average case. Severity exists to drive urgency and communication decisions; erring toward the higher tier costs a few minutes of over-caution, while erring low risks a customer finding out about a P1 from someone other than you.

## Adapt this to your context

- Three tiers is deliberately minimal for a lean team. Larger organisations, or ones with contractual SLA tiers, often need four or five (splitting P1 into a "total outage" vs "active breach" distinction, for example). Extend the table rather than trying to force everything into three rows if your real incident history doesn't fit.
- If your organisation already has a severity scheme defined elsewhere (a customer-facing SLA, an existing incident-management standard, a regulator's own severity taxonomy), map this rubric to that scheme rather than running two competing ones in parallel.
- "Customer-visible" is doing a lot of work in the P2/P3 split above. For a product with no direct end users (an internal tool, an API-only service with a single downstream consumer), redefine it as "visible to the tool's actual audience" rather than assuming a public-facing product.
