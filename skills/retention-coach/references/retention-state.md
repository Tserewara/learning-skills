# Retention state

## QUEUE.md

```markdown
## <item-id>

- Competency: <competency_id>
- Prompt:
- Evidence criterion:
- Last result: new | failed | cued | independent | transfer
- Horizon: 1d | 7d | 30d | 90d | custom
- Due: YYYY-MM-DD
```

## REVIEWS.jsonl

Append one JSON object per attempt:

```json
{"at":"YYYY-MM-DDTHH:MM:SSZ","item_id":"...","competency_id":"...","result":"failed|cued|independent|transfer","confidence":0,"error_tags":[],"next_due":"YYYY-MM-DD"}
```

Confidence is an integer from 0 to 3 and remains diagnostic only. Never rewrite prior events.

## MISCONCEPTIONS.md

Record the mistaken model, evidence that surfaced it, correction attempted, and next probe. Remove nothing; mark a misconception resolved only after a delayed successful probe.
