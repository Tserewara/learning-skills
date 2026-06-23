# Learning Skills

A small, composable skill set for durable learning. The package treats a repository as a learning workspace: explanations, practice, projects, review history, and evidence remain inspectable and versioned.

## Design

The skills split on one decision each:

- `teachme` creates one short lesson in the learner's proximal zone, plus the durable scaffolding around it — a printable reference sheet, the canonical `GLOSSARY.md`, and the `competency_id` the other skills consume.
- `roadmap-navigator` maps competencies and chooses the next frontier.
- `worked-example` teaches a repeatable pattern through a faded series of solved examples with self-explanation, between concept and practice.
- `retention-coach` runs delayed retrieval and schedules the next review.
- `deliberate-practice` trains one observable subskill in a tight loop.
- `project-lab` curates bounded projects that integrate skills and test transfer.

`teachme` is the human-invoked entry point. The other skills are model-invoked disciplines it can route toward. A future version may add `learning-journal` and `teach-back-video` after the evidence pipeline is stable.

## Workspace contract

Skills write only the state they own:

```text
MISSION.md
NOTES.md
RESOURCES.md
GLOSSARY.md
lessons/
reference/
learning-records/
roadmap/LEARNING-MAP.md
roadmap/BASELINE.md
roadmap/MILESTONES.md
retention/QUEUE.md
retention/REVIEWS.jsonl
retention/MISCONCEPTIONS.md
practice/SKILLS.md
practice/SESSIONS.jsonl
practice/ERRORS.md
projects/<project-id>/
assets/
```

Every cross-skill artifact names a stable `competency_id`. Markdown and HTML are authoritative; JSONL is used only for append-only event history.

## Learning rules

The skills contain operational rules, not academic exposition:

- Ask for a prediction or attempt before giving the answer when prior knowledge permits it.
- Train one observable subskill against a visible success criterion.
- Use attempt, feedback, correction, and another attempt as the smallest practice loop.
- Do not mark knowledge retained in the same session in which it was taught.
- Use projects to reveal bottlenecks and test transfer, not to replace focused practice.
- Mix tasks only after their isolated procedures are minimally stable.
- Treat confidence as context, never as evidence.

These rules are informed by work on deliberate practice, active engagement, error feedback, consolidation, retrieval practice, distributed practice, cognitive load, and transfer. Useful starting points include Anders Ericsson and Robert Pool's *Peak*, Stanislas Dehaene's *How We Learn*, [Karpicke and Roediger on retrieval](https://doi.org/10.1016/j.jml.2006.09.004), [Cepeda et al. on spacing](https://doi.org/10.1037/0033-2909.132.3.354), [Dunlosky et al. on learning techniques](https://doi.org/10.1177/1529100612453266), [Pan and Rickard on transfer](https://doi.org/10.1037/bul0000151), and [Macnamara et al. on the limits of deliberate-practice claims](https://doi.org/10.1177/0956797614535810). The references explain the design to humans; agents should follow the concrete rules in each skill instead of rehearsing this literature.

## Attribution

`teachme` is adapted from Matt Pocock's [`teach`](https://github.com/mattpocock/skills/tree/main/skills/productivity/teach) skill. The package design also follows his `writing-great-skills` principles: predictable process, leading words, sharp completion criteria, progressive disclosure, and aggressive pruning. Matt Pocock's repository is MIT licensed; its copyright notice is preserved in `NOTICE`.

## Validation

Each skill must pass structural validation and two forward tests:

1. a computer-science learning task;
2. a non-programming learning task.

The expected behavior is recorded under `evaluations/`. Passing means following the process and respecting evidence boundaries, not producing predetermined wording.
