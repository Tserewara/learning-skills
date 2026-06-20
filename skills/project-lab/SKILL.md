---
name: project-lab
description: Curate and evaluate bounded learning projects. Use when a learner must integrate stable competencies, expose bottlenecks, build procedural fluency, or demonstrate transfer in a new context.
---

# Project Lab

A **project** integrates competencies under constraints. It reveals bottlenecks; it does not replace the drills that correct them.

## Create a project

### 1. Select evidence targets

Read the mission, roadmap frontier, learning records, practice state, and prior projects. Select 2–4 competencies: most should already be at least `independent`; at most one may be the new stretch target.

Choose the least-supported stage that fits the evidence:

1. guided reproduction;
2. constrained extension;
3. reconstruction without reference;
4. transfer under a new requirement.

**Done:** every selected competency has a role in the project and the stage is justified by prior evidence.

### 2. Bound the project

Set a time budget, non-goals, allowed references, deliverables, observable tests, milestones, and stop conditions. Prefer a complete narrow system over a broad unfinished one.

Add one realistic failure or requirement change. Keep hints graduated and hidden until requested.

Create `projects/<project-id>/BRIEF.md` and `RUBRIC.md` using [references/project-format.md](references/project-format.md). Optionally create a clean `BRIEF.html` from the bundled template.

**Done:** another person can start the project and determine success without asking what “done” means.

### 3. Protect the learner's work

Do not implement the project for the learner. Answer questions with the smallest intervention that restores progress: question, cue, partial example, then worked example. Record every level of scaffolding used.

When a repeated error blocks progress, extract it as a drill and route it to `deliberate-practice`. Return to the project after the bottleneck improves.

**Done:** help preserves ownership, and blockers are either resolved by the learner or isolated into an explicit practice task.

## Evaluate a project

Run the declared tests and inspect artifacts through the rubric. Require the learner to explain one causal chain, diagnose one injected failure, and handle one small requirement change without a tutorial.

Write `EVIDENCE.md` with claims linked to artifacts and `POSTMORTEM.md` with prediction, result, error, corrected model, and next experiment. Upgrade roadmap evidence only for competencies actually demonstrated.

Schedule a smaller future reconstruction through `retention-coach`.

**Done:** every rubric claim is supported, rejected, or marked unknown; unknown is never upgraded by project completion alone.
