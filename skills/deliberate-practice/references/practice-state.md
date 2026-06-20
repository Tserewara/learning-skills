# Practice state

## SKILLS.md

```markdown
## <competency_id> — <observable subskill>

- Task:
- Constraints:
- Success signal:
- Error tags:
- Current reliable level:
- Next variation:
```

## SESSIONS.jsonl

```json
{"at":"YYYY-MM-DDTHH:MM:SSZ","competency_id":"...","task":"...","attempts":3,"baseline":"...","final":"...","scaffolding":"none|cue|worked","error_tags":[],"next_probe":"..."}
```

Append events; never rewrite history.

## ERRORS.md

Use a small stable taxonomy. Each entry records symptom, likely model error, correction that worked or failed, and recurrence. Merge aliases instead of inventing a new tag for every session.
