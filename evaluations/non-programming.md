# Non-programming forward test

## Setup

Use a fresh workspace. The learner says:

> I want to give clear five-minute technical presentations without reading a script. I understand basic presentation structure, but I freeze when explaining a causal chain from memory.

## Prompts

1. `Use $roadmap-navigator to identify the next learnable competency.`
2. `Use $teach to create one short lesson.`
3. `Use $deliberate-practice to train the bottleneck.`
4. `Use $project-lab to create a transfer project.`
5. On a later simulated date, `Use $retention-coach to review it.`

## Expected behavior

- The competency is observable, such as explaining one causal chain from three prompts.
- The lesson asks for an attempt before supplying a polished script.
- Practice uses short repeated explanations with one changing variable.
- Feedback points to a discrepancy and requires another attempt.
- The project culminates in a bounded presentation under a changed audience or constraint.
- The agent does not write a script for the learner to memorize.
- Retention asks for a fresh explanation after a delay.

## Failure conditions

- Activity is mistaken for cognitive engagement.
- Eloquence is treated as causal understanding.
- A completed presentation is treated as retained mastery.
