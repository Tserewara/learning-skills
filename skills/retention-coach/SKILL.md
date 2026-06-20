---
name: retention-coach
description: Run delayed retrieval and maintain a review queue. Use after learning when a concept, distinction, procedure, or mental model must remain available across sessions.
---

# Retention Coach

A **review** begins with retrieval and ends with a scheduling decision. Re-reading before attempting is not a review.

## 1. Build the queue

Read `learning-records/`, roadmap evidence, practice errors, project postmortems, and `retention/QUEUE.md`. Add only knowledge or procedures whose future availability matters to the mission. Give each item a `competency_id`, prompt, expected evidence, last result, and due date.

Prefer prompts that require reconstruction, discrimination, explanation, or a short execution. Use recognition only as scaffolding after a failed attempt.

Use [references/retention-state.md](references/retention-state.md) for file formats.

**Done:** every queued item has a meaningful prompt, evidence criterion, and due date.

## 2. Run due retrieval

Choose due items first. Add at most one stable, related item when mixing requires selecting between similar strategies. Do not mix procedures that are still unstable in isolation.

Ask the learner to respond without notes. Capture confidence after the answer, never before. Let productive effort happen before offering a cue.

**Done:** each selected item has an unaided response or an explicit failure to retrieve.

## 3. Close the error loop

Compare the response with the evidence criterion. Name the smallest discrepancy. Give the minimum cue or worked correction needed, then require another attempt in a changed form.

Record durable misconceptions in `retention/MISCONCEPTIONS.md`. Do not reward polished wording that lacks the causal relationship or procedure being tested.

**Done:** the learner has corrected the discrepancy or the item is routed back to `teachme` or `deliberate-practice`.

## 4. Schedule from performance

Use the result, not confidence, as the default signal:

- failed after correction: revisit within 1 day;
- correct with substantial cue: 1–3 days;
- correct independently: advance through 1, 7, 30, and 90-day horizons;
- correct independently in a new form: keep or extend the current horizon.

Adjust for the learner's actual need date and prior review history. Never mark an item `retained` in the session that introduced it.

Append the event to `retention/REVIEWS.jsonl` and update the queue.

**Done:** every attempted item has a recorded result, next due date, and route for unresolved errors.
