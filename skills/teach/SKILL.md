---
name: teach
description: Teach the user a new skill or concept through a stateful, repository-backed learning workspace. Use when the user explicitly invokes the skill to begin or continue learning across sessions.
---

# Teach

Treat the current directory as a persistent learning workspace. A **lesson** is the unit of teaching: one small, self-contained HTML experience tied to the learner's mission.

## 1. Ground the lesson

Read `MISSION.md`, `NOTES.md`, the latest files in `learning-records/`, and any relevant roadmap state. If `MISSION.md` is missing or vague, ask why the learner wants this capability before teaching it. Use [references/workspace.md](references/workspace.md) when bootstrapping missing files.

Choose one outcome inside the learner's proximal zone. Do not teach a whole roadmap layer at once.

**Done:** one observable outcome and its `competency_id` are named, and the mission explains why it matters.

## 2. Acquire trustworthy knowledge

Read `RESOURCES.md`. Prefer primary or authoritative sources and add sources only when they materially support the lesson. Do not rely on parametric recall for factual claims.

Use only the knowledge required for the observable outcome. Remove adjacent facts that do not change the learner's next action.

**Done:** the lesson has one primary source and no unsupported factual claim.

## 3. Ask before telling

When prior knowledge permits it, ask for a prediction, explanation, or first attempt before revealing the model. If the learner lacks the prerequisites, use a worked example instead. Never confuse clicks or passive reading with active engagement.

Compare the attempt with the model. Make the discrepancy specific and actionable.

**Done:** the learner has produced something or inspected a worked example with an explicit reason for using it.

## 4. Build the lesson

Create `lessons/NNNN-dash-case-name.html`. Keep it short enough to finish in one sitting. Link `assets/learning.css`; copy the bundled stylesheet there if the workspace lacks it.

Include:

- the outcome and why it matters;
- the smallest useful mental model;
- one worked example;
- one attempt with a tight feedback loop;
- a primary-source link;
- a prompt to ask follow-up questions.

Reuse existing assets before creating new ones. Put durable compressed knowledge in `reference/`, not in the lesson.

**Done:** the HTML opens without missing local assets and leads to one tangible attempt.

## 5. Record evidence, not exposure

Do not create a learning record because the lesson was read. Create `learning-records/NNNN-dash-case-name.md` only after the learner demonstrates non-trivial understanding or discloses prior knowledge with a stated depth. Use [references/learning-record.md](references/learning-record.md).

Record misconceptions in the owning skill's state. Update `NOTES.md` only for durable teaching preferences.

**Done:** demonstrated learning is recorded, or the absence of evidence is stated without upgrading mastery.

## Route the next need

- Use `roadmap-navigator` when the next competency or prerequisite is unclear.
- Use `retention-coach` when understanding exists but needs delayed retrieval.
- Use `deliberate-practice` when one subskill needs fluency through repeated attempts.
- Use `project-lab` when several stable skills need integration or transfer.

Do not recreate those workflows inside a lesson.
