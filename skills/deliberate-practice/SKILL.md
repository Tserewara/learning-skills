---
name: deliberate-practice
description: Train one observable subskill through repeated attempts and tight feedback. Use when a learner understands a concept but execution is slow, inconsistent, error-prone, or dependent on scaffolding.
---

# Deliberate Practice

A **drill** isolates one bottleneck and makes improvement visible. Projects are not drills.

## 1. Name the bottleneck

Read the mission and recent evidence. Convert a broad goal into one observable subskill. Reject goals such as “practice networking” or “get better at proofs.” Prefer goals such as “derive the subnet range without a calculator” or “state the invariant before each induction step.”

Define the task, constraints, success signal, error classes, and time budget. Use [references/practice-state.md](references/practice-state.md).

**Done:** one subskill has a binary or measured success signal that can be observed in a short attempt.

## 2. Establish a baseline

Run one representative attempt before teaching a workaround. Capture result, latency when meaningful, scaffolding used, and error tags. If the learner cannot begin because the mental model is missing, stop and route to `teachme`.

**Done:** the baseline exposes a trainable error or proves that a different bottleneck should be selected.

## 3. Build a tight loop

Create the smallest task that reproduces the error. Prefer automatic feedback from tests, properties, instruments, reference traces, or an explicit rubric. Keep unrelated complexity out.

Set difficulty slightly above the current reliable performance. If repeated failure produces no correction, reduce scope or add one cue. If every attempt is trivial, remove scaffolding or add one relevant variation.

**Done:** the learner can run the task repeatedly and receive specific feedback within the attempt cycle.

## 4. Attempt, correct, repeat

Run 3–5 focused attempts:

1. attempt without new help;
2. identify the smallest discrepancy;
3. explain why it occurred;
4. apply one correction;
5. retry with the same pattern in a changed surface form.

Change one variable at a time. Do not replace the learner's attempt with a polished solution.

**Done:** the target error declines, the success signal improves, or the session has clear evidence that the task or mental model must change.

## 5. Preserve the result

Append the session to `practice/SESSIONS.jsonl`; update `practice/SKILLS.md` and `practice/ERRORS.md`. Schedule a future reconstruction through `retention-coach`. Route integration to `project-lab` only after the subskill is independently stable.

**Done:** the session records baseline, attempts, feedback, final result, unresolved error, and next probe.
