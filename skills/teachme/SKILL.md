---
name: teachme
description: Teach the user a new skill or concept through a stateful, repository-backed learning workspace. Use when the user explicitly invokes the skill to begin or continue learning across sessions.
---

# Teachme

Treat the current directory as a persistent learning workspace. A **lesson** is the unit of teaching: one small, self-contained HTML experience tied to the learner's mission. The topic can be anything — a programming concept, a language's grammar, a musical skill, a yoga sequence, a period of history. The rules below are domain-neutral; apply them to whatever is being learned.

## 1. Ground the lesson

Read `MISSION.md`, `NOTES.md`, the latest files in `learning-records/`, and any relevant roadmap state. If `MISSION.md` is missing or vague, interview the learner before teaching: ask why they want this capability, then ask one disambiguating follow-up (scope, project type, prior experience) before committing the mission — a single bundled question often hides a fork that changes what to teach first. Use [references/workspace.md](references/workspace.md) when bootstrapping missing files.

Choose one outcome inside the learner's proximal zone. Do not teach a whole roadmap layer at once.

Coin a stable `competency_id` for the outcome (e.g. `css.box-model.sizing`, `spanish.subjunctive.present`, `guitar.barre-chords`). `teachme` is the entry point that creates the first artifacts, so the id it mints here is what `roadmap-navigator`, `retention-coach`, `deliberate-practice`, and `project-lab` later consume — name it now, and write it into the lesson and any learning record.

**Done:** one observable outcome and its `competency_id` are named, the mission was interviewed when absent or vague, and the mission explains why it matters.

## 2. Acquire trustworthy knowledge

Read `RESOURCES.md`. Prefer primary or authoritative sources and add sources only when they materially support the lesson.

Never trust parametric recall for factual claims, including source URLs. If `RESOURCES.md` lacks a vetted source for this outcome, search the web to find and verify one before citing it, then record it in `RESOURCES.md` with a one-line note on what it covers. Asserting "X is the authoritative source" from memory is the failure this step exists to prevent — equally for a CSS spec, a verb-conjugation table, or a chord chart.

Use only the knowledge required for the observable outcome. Remove adjacent facts that do not change the learner's next action.

**Done:** the lesson has one primary source that was read or verified this session (not recalled), and no unsupported factual claim.

## 3. Ask before telling

When prior knowledge permits it, ask for a prediction, explanation, or first attempt before revealing the model. If the learner lacks the prerequisites, use a worked example instead. Never confuse clicks or passive reading with active engagement.

Compare the attempt with the model. Make the discrepancy specific and actionable.

**Done:** the learner has produced something or inspected a worked example with an explicit reason for using it.

## 4. Bootstrap the workspace (first lesson for a competency only)

The workspace earns durable, reusable infrastructure once, on the first lesson — not again on every later lesson. If it already exists, reuse it and skip to Step 5. Establish:

- **One legible visual system** in `assets/learning.css`, which every lesson links and none restyles. Default to a calm reading aesthetic: a paper background, a serif body at a generous reading size, a narrow reading column, one accent color rather than several palettes competing for attention, and plenty of whitespace — a printed essay, not a dashboard. Go dark only if the learner asks.
- **Reusable components** in `assets/`, not lesson-local code. Anything a second lesson would duplicate — a quiz widget, an answer grader, a simulator, a diagram helper — is a configurable, multi-instance component in `assets/`, linked by the lesson. Both its styling and its behavior live there; a `<script>` of generic grading logic at the bottom of a lesson is the mistake to avoid.
- **`GLOSSARY.md`**, the canonical vocabulary (see Step 6).

These are investments amortized across the whole course. The `competency_id` from Step 1 is the thread that ties them together.

**Done:** a returning learner inherits a consistent look, a component library, and a glossary without the lesson re-deriving them.

## 5. Build the lesson

Create `lessons/NNNN-dash-case-name.html`, short enough to finish in one sitting. Link the workspace's `assets/learning.css` and reuse existing components before authoring new ones (new reusable pieces go to `assets/`, per Step 4).

Include:

- the outcome and why it matters;
- the smallest useful mental model;
- one worked example;
- the retrieval attempts described below;
- a primary-source link;
- a link to this competency's reference sheet and the next lesson (cross-link the workspace into a graph, not a pile of files);
- a prompt to ask follow-up questions.

**Make retrieval real, varied, and self-checking.** A visualizer the learner only manipulates is not retrieval — the answer appears whether or not they committed to one; use it to build the model, never as the test. Include **at least two retrieval attempts, and at least one of them production** the learner could not pass by recognition: produce the artifact (write the line of code, conjugate the verb, derive the value, name the cause), not merely pick from options. Prefer the hardest retrieval the learner can actually do — producing beats predicting a value, which beats choosing an option — and do not lower that ceiling for the sake of polish. Let multiple choice support the production task, not replace it. Gate any answer behind a commitment before revealing it, and make every multiple-choice option the same length so formatting leaks no clue.

**The lesson grades the attempt itself, and the checker accepts every correct answer.** Close the loop on the page (assert the real result, show pass/fail) rather than relying on an honor-system reveal or an external tool the lesson cannot see. A false negative — telling a learner their right answer is wrong — is worse than no checker at all, especially when the mission is to rebuild confidence. So grade the produced result, not one phrasing of it: check the rendered effect or the underlying value, and accept every equivalent correct form. Where the topic allows, have the page compute the expected result from the learner's own work instead of comparing against a value you hand-typed — it removes both arithmetic mistakes and false negatives at once.

**Make code and notation legible.** Any code, formula, or notation the learner reads to build a mental model deserves syntax/structure highlighting, done offline with a small reusable `assets/` component — never a CDN, which breaks the opened-from-disk contract. Choose colors that survive printing.

The lesson must open with no missing local assets and print cleanly: no clipped diagrams, interactive-only widgets hidden in print. If a CLI is available, open the lesson for the learner (e.g. `xdg-open`/`open`) rather than only printing its path.

Put durable compressed knowledge in `reference/`, not in the lesson — lessons are rarely revisited, reference sheets are. Produce or update `reference/<competency>.html` as the printable cheat sheet for this outcome: the compressed essence in whatever form fits the domain (tables and syntax, a conjugation chart, a chord diagram, a symptom→cause diagnostic).

**Done:** the lesson inherits the workspace's one visual system, leads to at least two retrieval attempts (at least one production that recognition can't pass) graded on the page by a checker that accepts every correct form, highlights any notation offline, links its reference sheet and next step, prints cleanly, and inlines no reusable script or style.

## 6. Keep the language canonical

Maintain `GLOSSARY.md` as the workspace's canonical vocabulary. The lesson, reference sheet, and learning records must use its terms; consistent naming across lessons is itself a retention asset. Add a term only once the learner can use it correctly — a glossary records compressed understanding, it is not a dictionary read to learn. Be opinionated: pick one canonical term per concept and list the rest as aliases to avoid. Keep definitions to one or two operational sentences, and use the glossary's own terms inside other definitions. Use [references/workspace.md](references/workspace.md) for the format.

**Done:** terms the learner can already use are canonical in `GLOSSARY.md`, and the lesson does not introduce a competing name for a concept already defined there.

## 7. Record evidence, not exposure

Do not create a learning record because the lesson was read. Create `learning-records/NNNN-dash-case-name.md` only after the learner demonstrates non-trivial understanding or discloses prior knowledge with a stated depth. Use [references/learning-record.md](references/learning-record.md).

Record misconceptions in the owning skill's state. Update `NOTES.md` only for durable teaching preferences.

**Done:** demonstrated learning is recorded, or the absence of evidence is stated without upgrading mastery.

## Route the next need

- Use `roadmap-navigator` when the next competency or prerequisite is unclear.
- Use `worked-example` when the learner grasps the concept but cannot yet start a problem alone and needs the pattern shown through faded examples.
- Use `retention-coach` when understanding exists but needs delayed retrieval.
- Use `deliberate-practice` when one subskill needs fluency through repeated attempts.
- Use `project-lab` when several stable skills need integration or transfer.

Do not recreate those workflows inside a lesson.
