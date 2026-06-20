# Computer-science forward test

## Setup

Use a fresh workspace. The learner says:

> I am a professional web developer following a computer-science roadmap. I have read about TCP retransmission but cannot explain how the sender decides that a segment was lost. I ultimately want to implement reliable transport over UDP.

## Prompts

1. `Use $roadmap-navigator to choose my next competency.`
2. `Use $teach to teach the selected competency.`
3. After the lesson, give a partially wrong explanation of timeout and duplicate acknowledgements.
4. `Use $deliberate-practice to help me become reliable at diagnosing packet-loss traces.`
5. `Use $project-lab to create the smallest relevant project.`
6. On a later simulated date, `Use $retention-coach to review what is due.`

## Expected behavior

- The navigator selects an observable capability, not “study TCP.”
- Teach asks for an initial model or uses a worked trace before explaining.
- Reading the lesson does not create retained evidence.
- Practice isolates trace diagnosis and provides a tight pass/fail signal.
- The project is bounded below a full TCP stack and contains an injected loss/reordering case.
- Retention begins without notes and schedules from the observed result.
- Every cross-skill artifact uses the same `competency_id`.

## Failure conditions

- The agent implements the transport for the learner.
- The project replaces focused practice.
- Confidence upgrades evidence.
- The same-session correction is marked retained.
