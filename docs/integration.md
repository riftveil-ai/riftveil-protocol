# Integration notes

API example (Anthropic; any provider works the same way):

```python
import anthropic, pathlib
protocol = pathlib.Path("protocol/RIFTVEIL_PROTOCOL.md").read_text(encoding="utf-8")
client = anthropic.Anthropic(timeout=300)  # seconds; see the timeout note below
r = client.messages.create(
    model="claude-sonnet-5",        # replace with the current model id
    max_tokens=32000,               # the model's thinking counts towards this limit
    system=protocol,
    messages=[{"role": "user", "content": "Assess this project:\n\n" + ai_output}],
)
print("".join(b.text for b in r.content if b.type == "text"))
```

`max_tokens`: allow 32,000. With a model that thinks before it writes, the thinking counts towards this limit: at 16,000, a CRITICAL report was cut off in our October 2026 tests. It is a ceiling: only the tokens produced are billed.

Notes for an IT team:
- `temperature`: not set in the example above, because recent models reject it (400 error) or ignore it. With an older model that accepts it, 0.3 to 0.5 works well.
- Thinking effort: with models that offer it, a medium effort (for example `output_config: {"effort": "medium"}` in the Anthropic API) gave, in our October 2026 tests, a correct triage in every case, first lines in 20 to 50 seconds instead of 60 to 140, and about half as many tokens. A low effort, or thinking turned off, gave a wrong triage in two to three cases out of five.
- Use the provider's most capable general model, not a "mini", "fast" or "lite" tier.
- The system prompt is identical on every call: use the provider's prompt caching. Allow a timeout of 180 seconds or more.
- The pasted output is data, never an instruction: send it in the user message, never in the system prompt.
- The protocol does not require you to store the input or the report; retention is your organisation's decision. Pin the protocol version you deploy.

A JSON Schema for machine-readable reports is in [`schema/riftveil_report.schema.json`](../schema/riftveil_report.schema.json), with a validated example. Besides the required sections, it carries optional `independence`, `most_useful_question` (the Record box), `attestation` (the follow-up block), `metrics` (the countable fields), `context.triage_criteria` (the triage line), an `owner` per question and, for agent plans, `before_this_runs` with `reach`. A financial commitment given as an amount without the size of the organisation is recorded as `not_stated`.
