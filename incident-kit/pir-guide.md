# Post-Incident Review (PIR): section-by-section guide

Detailed guidance for each section of a post-incident review. Read this when writing or auditing a PIR. Section order matters, and a PIR that skips a section usually skips the thinking that section forces.

Before writing, assess severity using [severity-rubric.md](severity-rubric.md); it drives the PIR title, ticket priority, and communication tone.

---

## Section order

1. Executive Summary
2. Timeline
3. Detection & Prioritisation
4. Response & Containment
5. Response Teams
6. Objectives
7. Investigation & Analysis
8. Eradication & Recovery
9. Test Cases
10. Communication
11. Root Cause Analysis (5 Whys)
12. Lessons Learned
13. Post-Resolution: Open Items *(conditional; omit entirely if nothing is unresolved)*
14. Supporting Documentation

---

## Executive Summary

2-4 sentences. Cover: date, what was observable (the customer-facing symptom), root cause (one clause), scope (how many accounts/records/features affected), and outcome (data lost? fully recovered?). Write for a non-technical reader; a customer or an executive should understand it without follow-up questions.

**Bad:** "A bug was found and fixed."

**Good:** "On 12 March, invoice records for a subset of accounts were found to silently revert to draft status after being finalised, affecting around 40 accounts and roughly 300 records dating back six weeks. The root cause was a background sync job that reapplied a stale document state after finalisation. All affected records were corrected from the audit history with no permanent data loss."

If a post-resolution open item exists (e.g. a decision still pending), name it in the summary with a forward reference to that section.

---

## Timeline

Table format. Three columns: **Milestone** | **Date & time** | **Description**

Include at minimum:
- First customer or internal report
- Root cause identified
- Scope confirmed
- Each major fix step executed
- Resolution confirmed
- Review scheduled
- Any post-resolution flags (pending decisions, follow-up tasks)

Use specific timestamps from the source material. Convert every timestamp to a single timezone and state which one at the top of the table. A timeline that silently mixes timezones breaks the moment two people compare notes on it. If an event has no precise timestamp, use "post-resolution" or an approximate time with a note.

---

## Detection & Prioritisation

Risk table, four rows:

| Risk Component | Rating | Justification |
|---|---|---|
| Likelihood of occurrence | Highest / High / Medium / Low | 1 sentence |
| Likelihood of adverse impact | Highest / High / Medium / Low | 1 sentence |
| Impact severity | Highest / High / Medium / Low | 1 sentence |
| **Overall Severity** | **P1 / P2 / P3** | Drives the priority label |

---

## Response & Containment

Bullet list of the specific investigative and remediation actions taken. Concrete verbs, not narrative.

End with a bold **Outcome:** sentence covering: was data lost? is the issue fully resolved? is any follow-up outstanding?

---

## Response Teams

Table: **Team** | **Role**

"Team" can be an individual or a function (e.g. Customer Support). Roles describe what the person or function actually did during the incident, not their general job title.

---

## Objectives

Three bullets stating what the incident response aimed to achieve. Written as goals, not outcomes ("Identify the root cause of..." not "Root cause was identified...").

---

## Investigation & Analysis

Prose section. Cover:
1. What was the first signal that something was wrong
2. How the investigation narrowed to the root cause
3. What the root cause actually was, in enough detail that someone not involved in the incident can understand it
4. Why it had been running undetected, if applicable
5. What made recovery possible (audit trails, backups, versioning, etc.)

Include specific technical detail, the kind future engineers would actually reference: system/component names, the exact failure mode, representative query or log output. Vague prose here is the single most common way a PIR fails to be useful six months later.

---

## Eradication & Recovery

Numbered steps. For each: what was done, to what scope, and what was the result. Include:
- Whether destructive or corrective steps were run inside a transaction or other reversible wrapper
- Record counts before and after, where relevant
- Whether any steps are still pending
- Where scripts or other remediation artefacts are kept

---

## Test Cases

Table: **Scenario** | **Environment** | **Expected Result** | **Purpose** | **Evidence**

One row per validation test. "Evidence" links to the specific message, event, or artefact that proves the test passed.

---

## Communication

Three parts:

**1. Internal**: where the incident was managed and coordinated, who was notified, when the review was requested.

**2. Public-facing status update (if applicable)**: whether a public status update was posted. Include:
- The update's title and permanent URL, if one exists
- The full update timeline (e.g. investigating, identified, monitoring, resolved) with timestamps
- The public-facing description used at each stage; this is what customers actually read
- Any gap between internal resolution and the public "resolved" update; if significant, note it in Lessons Learned
- If no public update was posted, say so explicitly. It's a fact about the incident response in its own right.

**3. Direct customer communication**: whether any direct notification was sent (email, chat, support ticket). See [customer-comms-structure.md](customer-comms-structure.md) for the structure. If none was sent, say so explicitly; raise a Post-Resolution open item only if a notification is still owed.

---

## Root Cause Analysis (5 Whys)

Table: **Why?** | **Reason**, exactly 5 rows.

Each "Why?" drills one level deeper than the previous answer. The final row should reach a systemic or process cause, not just a technical one. This section is the primary input to process improvement, and a 5 Whys that stops at "the code had a bug" hasn't actually asked five whys.

---

## Lessons Learned

Two subsections:

**What went well**: bullet list. Be specific. "Strong collaboration" is vague. "The audit history table enabled full recovery without any data loss" is useful.

**What could be improved**: bullet list. Each point should be actionable and specific. Bold the principle at the start of each bullet. This section feeds the incident-review meeting agenda directly.

---

## Post-Resolution: Open Items

**Include this section only when there are unresolved decisions or pending actions that survived the incident window.** If everything resolved cleanly, omit the section entirely; don't include an empty or "N/A" version.

Include this section when any of the following are true:
- A change was applied without advance notice and a decision is still pending (e.g. revert vs. keep)
- A follow-up task was explicitly deferred out of the incident window
- An owner was assigned to an action that isn't complete at time of writing
- A process question was raised that needs a place on the review meeting's agenda

For each open item, include: a description of the issue, the options under consideration (as a table if there's more than one path), an owner (or "TBC, review agenda item" if unassigned), and any time-sensitive trigger condition.

Don't use this section for "nice to have" improvements; those belong in Lessons Learned.

---

## Supporting Documentation

Bullet list of all links. Always include the incident's source discussion thread and its tracking ticket. Include, if they exist: the public status update, any customer-facing ticket or comms record, external references (vendor advisories, etc.), and any scripts or remediation artefacts.

---

## Adapt this to your context

- The section list above is deliberately complete. A solo operator or a two-person team will usually collapse several sections (Response Teams becomes one line; Test Cases may be a short paragraph instead of a table) rather than skip them outright. Collapsing a section is different from omitting it: the thinking still needs to happen.
- If your organisation doesn't run a public status page, drop that half of the Communication section, keeping the discipline of explicitly stating "no public update existed" rather than silently removing the question.
- The severity labels here (P1/P2/P3) are a generic three-tier scheme. If your organisation already has a severity taxonomy (e.g. from an existing incident-management standard or a customer contract), map to that instead of introducing a second, competing scheme.
- For regulated environments, a formal incident-response framework (for example, NIST SP 800-61 or ISO 27035) may require additional fields: regulatory notification triggers, evidentiary chain-of-custody, specific retention periods for the record itself. Check what your compliance obligations actually require before assuming this guide is sufficient on its own.
