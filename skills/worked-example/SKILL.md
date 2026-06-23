---
name: worked-example
description: Teach a repeatable pattern through a faded series of solved examples with self-explanation. Use when a learner cannot yet start a problem alone and needs to extract the pattern before practicing it.
---

# Worked Example

A **worked set** is a short, fading series — one fully solved example, one or more completion problems with growing gaps, then one open problem — that carries a repeatable pattern into the learner's schema. A worked set teaches the *pattern*; a drill trains *execution*. The worked set comes first, while the learner cannot yet start alone. Reading a solution is not studying it: without self-explanation it is passive review, and the pattern does not transfer.

This skill sits between `teachme` (which introduces a concept with a single example) and `deliberate-practice` (which assumes the pattern is understood and trains its execution). Reach for it when the learner understands *what* a thing is but stares at a blank page when asked to *do* it.

The pattern can be anything repeatable: a code idiom, a proof structure, a verb conjugation, a chord voicing, a case diagnosis. The rules below are domain-neutral.

## 1. Name the pattern

Read `MISSION.md`, `NOTES.md`, the latest `learning-records/`, and any roadmap state. Convert the goal into **one** pattern a learner extracts by studying instances — not a broad concept and not a single fact. Reject targets such as "understand recursion" or "learn the subjunctive." Prefer "write a recursive function with a base case and a shrinking argument" or "form the present subjunctive of regular -ar verbs."

Reuse the `competency_id` minted by `teachme` or `roadmap-navigator` for this outcome; do not coin a competing one. If none exists, the learner is not ready for a worked set — route to `teachme` to introduce the concept first.

**Done:** one extractable pattern and its existing `competency_id` are named, and the pattern is narrow enough that three examples share a visible structure.

## 2. Source the examples

Read `RESOURCES.md`. Draw every example from a vetted source, not from parametric recall — a wrong worked example teaches a wrong pattern, and the learner has no base to catch it. Verify any source URL this session rather than asserting it from memory, and record new sources in `RESOURCES.md` with a one-line note.

Choose examples that share the same deep structure under different surface forms. Surface variety is what lets the learner separate the pattern from its decoration; three near-identical examples teach memorization, not transfer.

**Done:** every example traces to a verified source, and the set varies surface form while holding structure constant.

## 3. Build the faded set

Construct the sequence, fading the scaffold one step at a time:

1. **One fully worked example** — every step shown, each step labeled with the sub-goal it achieves, not just the mechanics. The learner must see *why* the step exists, not only *what* it does.
2. **One or two completion problems** — the same structure with steps removed, gaps growing across the set. Remove the steps that carry the pattern, not the trivial ones.
3. **One open problem** — same structure, no scaffold, a new surface form.

Fade in this order because a learner without the schema cannot afford the working-memory cost of an open problem; the solved example loads the schema, the completion problems force partial retrieval, and the open problem consolidates. Do not start at the open problem, and do not stay on the solved example once the learner can fill gaps.

**Done:** the set runs solved → completion → open, each rung removes scaffold the previous rung supplied, and the final rung shares structure but not surface with the first.

## 4. Require self-explanation

A worked set works only if the learner explains it. At each step of the solved example, ask the learner to state *why* this step follows — before revealing the rationale. Compare their explanation to the model and make any gap specific. On completion problems, gate each gap behind the learner's committed answer before showing it; grade the produced result on the page and accept every equivalent correct form. A false negative on a learner rebuilding from a blank page is worse than no check.

Passive clicks through a solution are the failure this step exists to prevent. If the learner only reveals steps without explaining them, the worked set has not happened.

**Done:** the learner produced a why-explanation for each solved step and a committed answer for each completion gap, each checked against the model.

## 5. Build the artifact

Create `lessons/NNNN-dash-case-name.html`, short enough to finish in one sitting. Link the workspace's `assets/learning.css` and reuse existing components before authoring new ones; a collapsible step-with-self-explanation widget and an on-page grader are reusable pieces that belong in `assets/`, not inlined.

Include: the pattern and why it matters; the worked set's three rungs; the self-explanation prompts and on-page checks; a primary-source link; a link to this competency's reference sheet and to the next step; and a prompt to ask follow-up questions. Highlight any code or notation offline, never via CDN. The lesson must open with no missing local assets and print cleanly.

Update `reference/<competency>.html` with the compressed pattern — the skeleton the learner reconstructs from memory (the step sequence, the invariant, the conjugation frame), not the full examples.

**Done:** the lesson inherits the workspace's one visual system, presents the faded set with on-page self-explanation and grading, highlights notation offline, links its reference sheet and next step, prints cleanly, and inlines no reusable script or style.

## 6. Record evidence, not exposure

Create `learning-records/NNNN-dash-case-name.md` only after the learner completes the open problem unaided or explains the pattern in their own terms — not because the lesson was read. Record where the scaffold was still needed: the rung at which the learner stalled is the bottleneck the next skill targets. Update `NOTES.md` only for durable teaching preferences.

**Done:** demonstrated pattern extraction is recorded with the rung where scaffold was still needed, or the absence of evidence is stated plainly.

## Route the next need

- Use `deliberate-practice` once the pattern is understood but execution is slow, inconsistent, or error-prone — the worked set ends where the drill begins.
- Use `retention-coach` to schedule delayed reconstruction of the pattern so it survives across sessions.
- Use `teachme` if self-explanation reveals a missing concept underneath the pattern.
- Use `project-lab` only after the pattern is independently stable and ready to integrate.

Do not recreate those workflows inside a lesson.
