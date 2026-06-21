---
name: teachme
description: Teach the user a new skill or concept through a stateful, repository-backed learning workspace. Use when the user explicitly invokes the skill to begin or continue learning across sessions.
---

# Teachme

Treat the current directory as a persistent learning workspace. A **lesson** is the unit of teaching: one small, self-contained HTML experience tied to the learner's mission.

## 1. Ground the lesson

Read `MISSION.md`, `NOTES.md`, the latest files in `learning-records/`, and any relevant roadmap state. If `MISSION.md` is missing or vague, interview the learner before teaching: ask why they want this capability, then ask one disambiguating follow-up (scope, project type, tools) before committing the mission — a single bundled question often hides a fork that changes what to teach first. Use [references/workspace.md](references/workspace.md) when bootstrapping missing files.

Choose one outcome inside the learner's proximal zone. Do not teach a whole roadmap layer at once.

Coin a stable `competency_id` for the outcome (e.g. `css.box-model.sizing`). `teachme` is the entry point that creates the first artifacts, so the id it mints here is what `roadmap-navigator`, `retention-coach`, `deliberate-practice`, and `project-lab` later consume — name it now, and write it into the lesson and any learning record.

**Done:** one observable outcome and its `competency_id` are named, the mission was interviewed when absent or vague, and the mission explains why it matters.

## 2. Acquire trustworthy knowledge

Read `RESOURCES.md`. Prefer primary or authoritative sources and add sources only when they materially support the lesson.

Never trust parametric recall for factual claims, including source URLs. If `RESOURCES.md` lacks a vetted source for this outcome, search the web to find and verify one before citing it, then record it in `RESOURCES.md` with a one-line note on what it covers. Asserting "X is the authoritative source" from memory is the failure this step exists to prevent.

Use only the knowledge required for the observable outcome. Remove adjacent facts that do not change the learner's next action.

**Done:** the lesson has one primary source that was read or verified this session (not recalled), and no unsupported factual claim.

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
- a link to this competency's reference sheet and the next lesson (cross-link the workspace into a graph, not a pile of files);
- a prompt to ask follow-up questions.

**Make the feedback loop close on the page, automatically.** A visualizer the learner only drags is manipulation, not retrieval — the answer appears whether or not they committed to one. Prefer an in-page attempt the lesson can grade itself (assert the real rendered result, show pass/fail) over an honor-system reveal or an attempt outsourced to an external editor the lesson cannot see. Gate any answer behind a commitment (a prediction, a produced artifact) before revealing it. For multiple-choice retrieval, make every option the same length so formatting leaks no clue.

**Prefer the hardest retrieval the learner can actually do; don't lower the ceiling for polish.** Producing an artifact (write the CSS, derive the value, name the cause) is stronger retrieval than predicting a number, which is stronger than picking from options. A more finished lesson is not a better lesson if it quietly swapped a produce-it task for a recognize-it one. Include at least one make-something attempt the learner could not pass by recognition, and let multiple choice support it rather than replace it.

**A checker must accept every correct answer, not one phrasing of it.** A false negative — telling a learner their right answer is wrong — is worse than no checker at all, especially when the mission is to rebuild their confidence. Do not grade free-form code by matching one string: `padding: 0 16px`, `padding: 0px 16px`, and `padding-left/right` are the same answer; `border: 2px solid` and `border: solid 2px black` are both valid. Grade the rendered effect when you can (read computed style off a live element), or accept the full set of equivalent forms; verify your own arithmetic before asserting an expected value.

**Assets are reusable components, not lesson-local code.** Reuse what is in `assets/` before authoring anything. When the lesson needs something new and reusable — a quiz widget, a live editor, a simulator — write it as a configurable, multi-instance component in `assets/` and link it; never inline a `<script>` or `<style>` block a second lesson would duplicate. A static visualizer can stay inline; anything a future lesson would reuse moves to `assets/`. Moving the styles out but leaving the behavior inline is half the job: a generic quiz/checker function (e.g. `answerQuiz`, a numeric or code grader) is reusable and belongs in `assets/`, not in a `<script>` at the bottom of the lesson. Before finishing, scan the lesson's own `<script>` and `<style>` for anything not specific to this one lesson, and move it.

**Commit to one legible visual system, and let lessons inherit it.** The first lesson earns the workspace's design system in `assets/learning.css`; every later lesson links it and does not restyle what it already defines. Default to a light, calm reading aesthetic: a paper background, a serif body at a generous reading size, a narrow reading column (~46rem), one accent color rather than several semantic palettes competing for attention, thin rules, and plenty of whitespace — fewer things on screen at once. Aim for a printed essay, not an IDE dashboard; go dark only if the learner asks. Lesson-local `<style>` is only for the few widgets unique to that lesson.

**Syntax-highlight every code block, offline.** Code the learner reads to build a mental model deserves the same legibility as their editor. Highlight with a small reusable component in `assets/` (e.g. `assets/highlight.css` plus a light tokenizer, or pre-tokenized markup) — never a CDN `<script>`, which breaks the offline, opened-from-disk contract and leaks an external dependency. Choose colors that survive printing.

Put durable compressed knowledge in `reference/`, not in the lesson — lessons are rarely revisited, reference sheets are. Produce or update `reference/<competency>.html` as the printable cheat sheet for this outcome (the compressed essence: tables, syntax, a symptom→cause diagnostic). It and the lesson must print well: no clipped diagrams, interactive-only widgets hidden in print.

If a CLI is available, open the lesson for the learner (e.g. `xdg-open`/`open`) rather than only printing its path.

**Done:** the HTML opens without missing local assets, prints cleanly, links its reference sheet and next step, and leads to at least one make-something attempt — not just recognition — that the lesson grades itself, with a checker that accepts every correct form of the answer. Code blocks are syntax-highlighted offline, the lesson inherits the workspace's one visual system, and no reusable script or style remains inlined.

## 5. Keep the language canonical

Maintain `GLOSSARY.md` as the workspace's canonical vocabulary. The lesson, reference sheet, and learning records must use its terms; consistent naming across lessons is itself a retention asset. Add a term only once the learner can use it correctly — a glossary records compressed understanding, it is not a dictionary read to learn. Be opinionated: pick one canonical term per concept and list the rest as aliases to avoid. Keep definitions to one or two operational sentences, and use the glossary's own terms inside other definitions. Use [references/workspace.md](references/workspace.md) for the format.

**Done:** terms the learner can already use are canonical in `GLOSSARY.md`, and the lesson does not introduce a competing name for a concept already defined there.

## 6. Record evidence, not exposure

Do not create a learning record because the lesson was read. Create `learning-records/NNNN-dash-case-name.md` only after the learner demonstrates non-trivial understanding or discloses prior knowledge with a stated depth. Use [references/learning-record.md](references/learning-record.md).

Record misconceptions in the owning skill's state. Update `NOTES.md` only for durable teaching preferences.

**Done:** demonstrated learning is recorded, or the absence of evidence is stated without upgrading mastery.

## Route the next need

- Use `roadmap-navigator` when the next competency or prerequisite is unclear.
- Use `retention-coach` when understanding exists but needs delayed retrieval.
- Use `deliberate-practice` when one subskill needs fluency through repeated attempts.
- Use `project-lab` when several stable skills need integration or transfer.

Do not recreate those workflows inside a lesson.
