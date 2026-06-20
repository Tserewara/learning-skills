---
name: roadmap-navigator
description: Navigate a roadmap as a competency graph. Use when a learner needs a baseline, prerequisite check, scope decision, milestone, or the next learnable competency.
---

# Roadmap Navigator

A **frontier** is the smallest valuable competency whose prerequisites are evidenced. Choose one frontier; do not turn the roadmap into a content checklist.

## 1. Map capabilities

Read the roadmap, `MISSION.md`, learning records, and existing `roadmap/` state. Convert topic labels into observable capabilities. Give each capability a stable `competency_id` such as `net.tcp.retransmission`.

Connect prerequisites only when failure in one capability would block practice in another. Mark optional depth explicitly.

Write or update `roadmap/LEARNING-MAP.md` using [references/map-format.md](references/map-format.md).

**Done:** every active node names an observable behavior, evidence state, and real prerequisite or explicitly has none.

## 2. Establish the baseline

Sample the map with short, unaided probes. Prefer explanation, prediction, debugging, derivation, or execution over recognition. Never fill missing evidence with confidence or professional seniority.

Write `roadmap/BASELINE.md`. Use these states:

- `unknown`: no evidence;
- `recall`: reconstructs the core idea;
- `guided`: succeeds with scaffolding;
- `independent`: succeeds without scaffolding;
- `transfer`: succeeds in a materially new situation;
- `retained`: succeeds independently after a delay.

**Done:** sampled nodes cite the probe and result; unsampled nodes remain `unknown`.

## 3. Choose the frontier

Select the node that best satisfies all four:

1. prerequisites are at least `independent` or deliberately included in the task;
2. it advances the mission;
3. it fits the current time budget;
4. it creates evidence reusable by later nodes.

Prefer foundational bottlenecks over attractive electives. Present the choice, rejected alternatives, budget, and exit criterion.

**Done:** exactly one frontier is selected and the learner can explain why it comes next.

## 4. Route execution

- Route new mental models to `teachme`.
- Route fragile prior learning to `retention-coach`.
- Route a narrow performance bottleneck to `deliberate-practice`.
- Route integration of stable competencies to `project-lab`.

Update `roadmap/MILESTONES.md` only with evidence-backed progress. Do not mark a roadmap section complete because its resources were consumed.

**Done:** the next action names its owning skill, evidence to produce, and stopping condition.
