# Customer communication structure

Only draft customer communication once every remediation decision is settled. If a breaking change or a revert-versus-keep decision is still open, the framing changes significantly depending on which way it lands. Drafting before that's decided produces a message you'll need to rewrite, or worse, contradict.

## The five things every incident communication covers

Adapt the emphasis to the specific incident, but cover all five. Skipping one is the most common way an incident communication reads as evasive, even when it isn't meant to.

1. **What happened**: a brief, non-technical description of the observable impact, ahead of the root cause; cover what the customer actually saw or experienced.
2. **What was affected**: specifically what the customer could or couldn't see or do, and for how long. Be concrete about scope; vague scope reads as either minimising or not actually knowing.
3. **What you've done**: what's resolved, and what's still in progress. Distinguish clearly between the two.
4. **What they need to do**: a specific action item, or an explicit statement that no action is needed. Don't leave this implicit; an incident update with no clear next step for the reader gets re-read looking for one.
5. **What you're doing about it**: the review process, a process change, or a prevention measure. This is what turns an apology into evidence of a functioning organisation.

## Format

Draft at least two formats when the audience and channel differ:

- **The detailed version** (email, a support ticket reply, a formal notice): full detail across all five points.
- **The condensed version** (a chat message, an in-app banner, a status update): short, and pointing to the detailed version for anything beyond a one-line summary.

## Tone

Own mistakes directly. Avoid passive voice for errors that were your organisation's fault; "we introduced a bug that..." reads very differently from "a bug caused...". If this is a repeat impact on the same customer, name that fact rather than omitting it. Pretending a prior incident didn't happen reads far worse on discovery than acknowledging it upfront.

## Adapt this to your context

- If your product has no direct end users to notify (an internal tool, a component another team owns downstream), point 4 ("what they need to do") often becomes "nothing, this notice is for your records," which is a legitimate answer in its own right rather than a section to cut.
- Regulated environments may have a mandatory notification content and timeframe (for example, specific breach-notification obligations under a privacy or data-protection law) that supersedes or extends this structure. Check what's legally required before assuming this five-point structure alone is sufficient.
- For a very small team without a dedicated communications function, the "condensed" and "detailed" versions might be the same message sent to a smaller list. The discipline of covering all five points matters more than having two distinct formats.
