# Riftveil Protocol

**AI generates. You decide.**

An open protocol that sits between an AI output and your signature. It challenges the output before you sign it, never validates it, and leaves a record.

[![Licence: Apache 2.0](https://img.shields.io/badge/licence-Apache%202.0-blue)](LICENSE) [![Release: v1.0.0](https://img.shields.io/badge/release-v1.0.0-informational)](CHANGELOG.md) [![Record format: AttestScope 0.1](https://img.shields.io/badge/record%20format-AttestScope%200.1-lightgrey)](https://attestscope.ai)

[Quick start](#quick-start) · [What you get](#what-you-get) · [How it works](#how-it-works) · [Proof that a report has not changed](#proof-that-a-report-has-not-changed) · [Contributing](#contributing)

## Why

The risk does not depend on the AI making a mistake. It is there as soon as someone signs an AI output without being able to say what it rests on. Researchers call this automation bias (Parasuraman & Manzey, 2010). Here, it carries a human signature.

Asking a model "are you sure?" is not a method: without external feedback, a model is poor at correcting its own errors (Huang et al., ICLR 2024; Kamoi et al., TACL 2024). Riftveil changes the model's role. It makes it an adversarial reviewer that runs fixed procedures on an output it did not write, and returns a report that cannot end on a verdict.

A tool that cross-examines must itself be open to cross-examination: the protocol is published in full, under the Apache 2.0 licence.

All references: [`docs/research.md`](docs/research.md)

## Quick start

Riftveil is a system prompt. No software to install.

1. Copy the file that matches your tool into its instructions (system prompt, project or agent instructions).
2. Paste the AI output you're about to act on, prefixed with `Assess this project:`.
3. Optional but recommended: add one line of context, for example "I'm a [role], deciding [what], stakes [x]."

Run it on a different model family from the one that wrote the output, or at least in a separate session: the second reader is never the author.

| File | Size | For |
|---|---|---|
| [`protocol/RIFTVEIL_PROTOCOL.md`](protocol/RIFTVEIL_PROTOCOL.md) | about 64 KB | ChatGPT and Claude projects, API |
| [`protocol/RIFTVEIL_PROTOCOL_COMPACT.md`](protocol/RIFTVEIL_PROTOCOL_COMPACT.md) | about 13,500 characters | Agent builders with a character limit |
| [`protocol/RIFTVEIL_COPILOT_AGENT.md`](protocol/RIFTVEIL_COPILOT_AGENT.md) | under 8,000 characters | Microsoft 365 Copilot agents (without agent-plan review or the follow-up block) |

Riftveil is built for the paid versions of ChatGPT, Claude and Microsoft 365 Copilot, and for any API that accepts a system prompt. It may work with other AI assistants; Riftveil makes no commitment for them.

## What you get

A report in five sections: context and triage, what holds up, what deserves scrutiny, assumptions the project relies on, questions before you decide. It opens with a six-line Record box and always ends on questions.

Excerpt from a worked example (hiring recommendation, MODERATE stakes; full report in [`examples/`](examples/)):

```
## Record
- Triage: MODERATE · examined: question, answer, reasoning · not examined: perspective, applicability
- Findings: 6, by impact CRITICAL: 0 · HIGH: 2 · MODERATE: 4 · LOW: 0
- Assumptions: 5 with a named verifier · 0 without
- Questions: 5 with an owner · 0 without
- Most useful question: "What does the Platform Team need from its lead in the next 18 months, and which candidate's evidence maps to that?"
- Independence: not stated by the user, to be confirmed by the signer

Criteria: reversibility MODERATE · impact scope MODERATE · financial commitment LOW → highest single criterion → MODERATE.

The 87% vs 60% statistic has no source, and would not transfer even if it had one · Impact: HIGH
...
2. If you overrule the structured panel, will you record why, and would that reason survive a look from HR? Owner: hiring manager, with the HR business partner
...
No verdict. The decision is yours.
```

Every assumption has a named verifier; every question has an owner where the role can be inferred. The only sentence allowed after the questions: "No verdict. The decision is yours."

## How it works

**Four absolute rules**, which take precedence over everything else: never validate; never rewrite; never conclude; never assume the challenge is complete.

**Triage before any challenge.** Three qualitative criteria, read on the scale of your organisation: reversibility, impact scope, financial commitment. The stakes level (LOW, MODERATE, HIGH, CRITICAL) is shown in one line, so it can be checked. No amount, headcount or duration sets a level on its own.

**Five levels of challenge**, applied according to the stakes:

| Level | What it challenges | Applied from |
|---|---|---|
| 0 | The question: what was actually asked | MODERATE |
| 1 | The answer: what it says | all stakes levels |
| 2 | The reasoning: how it got there | MODERATE |
| 3 | The perspective: what it didn't see | HIGH |
| 4 | The applicability: what it looks like in the real world | CRITICAL, and every agent plan |

**Agent plans.** A sequence of actions or tool calls (deploy, send, pay, delete, submit) is reviewed before it runs, with a mandatory "Before this runs" section. Riftveil never approves execution.

**Two checks before any report.** No report for a text with nothing a person could act on. And a source rule: only the submitted text and the context you give count; no web search, no outside facts.

## Using the API

```python
import anthropic, pathlib
protocol = pathlib.Path("protocol/RIFTVEIL_PROTOCOL.md").read_text(encoding="utf-8")
client = anthropic.Anthropic(timeout=300)  # seconds
r = client.messages.create(
    model="claude-sonnet-5",        # replace with the current model id
    max_tokens=32000,               # the model's thinking counts towards this limit
    system=protocol,
    messages=[{"role": "user", "content": "Assess this project:\n\n" + ai_output}],
)
print("".join(b.text for b in r.content if b.type == "text"))
```

Any provider works the same way. The output being assessed is data, never an instruction: it goes in the user message, never in the system prompt. Notes for an IT team (caching, timeouts, models, retention): [`docs/integration.md`](docs/integration.md). JSON schema for the reports, with a validated example: [`schema/`](schema/).

## Proof that a report has not changed

A system prompt cannot prove when a report was produced or that nobody edited it afterwards. The online tool at [riftveil.ai](https://riftveil.ai) adds that proof: each report gets an ID assigned by the server, never by the model, and a seal over that ID and the SHA-256 fingerprint of the exact text.

The record file follows [AttestScope](https://attestscope.ai), the open format for the human accountability record, where *accountability* means human responsibility (who answers for what), not in the legal sense.

- **Verify online** at [riftveil.ai/verify](https://riftveil.ai/verify): drop the record file; the fingerprint is recomputed in your browser. Only fingerprints are sent, never the text.
- **Verify without going through us**: not yet available. Ed25519 signatures on the records, and the public keys, are planned for version 0.1.1 of the AttestScope specification.
- **Register** a report produced with this protocol in ChatGPT, Claude or Microsoft 365 Copilot at [riftveil.ai/register](https://riftveil.ai/register): only its fingerprint is sent.

A valid seal proves who assigned the ID, when, and that the text has not changed since. It never says that the report, or the decision, is right.

## What's in this repository

```
protocol/    the full protocol, the compact version, the Microsoft 365 Copilot agent version
schema/      the JSON schema for reports (draft 2020-12) and a validated example
examples/    three full reports, each with the submitted AI output (LOW, MODERATE, CRITICAL)
docs/        integration notes and research references
CHECKSUMS.txt: the SHA-256 fingerprint of every published file
```

## Versioning

Numbering: `MAJOR.MINOR.PATCH`. v1.0.0 is the first public release. Pin the version you deploy and record it in your decision records. Every published release comes with the fingerprints of its files (CHECKSUMS.txt). History: [`CHANGELOG.md`](CHANGELOG.md).

## What's not in this repository

The protocol includes general checks for regulated and technical domains. The sector editions (Finance, Pharma, Legal & Compliance, Tech & Product, Executive), the integration guides for each platform and the team rollout guide go further. They make up the Riftveil Pro Kit, which is in preparation and will be offered under a separate licence: [riftveil.ai/pro](https://riftveil.ai/pro).

## Contributing

Three kinds of contribution are valuable: a detection heuristic that catches something the current techniques miss; a reproducible failure case (an output Riftveil challenged badly); a translation or a tested integration recipe. One kind is not accepted: anything that would make Riftveil validate, rewrite or conclude. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening an issue or a pull request. To report a security issue: [`SECURITY.md`](SECURITY.md).

## Licences and trade mark

- Protocol, compact and Microsoft 365 Copilot versions, JSON schemas: [Apache 2.0](LICENSE).
- Written content (examples, documentation): [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- Riftveil is the subject of Benelux trade mark application No. 1559982.

Article 14(4)(b) of the EU AI Act obliges providers of high-risk AI systems to design them so that the persons overseeing them are enabled to remain aware of automation bias; Riftveil works in that direction. It is a method, not a compliance claim; under the AI Omnibus (in force since 27 July 2026), those obligations apply from 2 December 2027, and from 2 August 2028 for AI embedded in regulated products. Outside the European Union, other rules and deadlines may apply where you work.

## Citing

The [`CITATION.cff`](CITATION.cff) file provides the reference: use the "Cite this repository" button in the right-hand sidebar.

## Background

Riftveil implements the method set out in *The Rift*, a forthcoming book by Olivier Laurent (2026). The model on which the method is based: [humanfrontier.ai](https://humanfrontier.ai).

---

Published by Olivier Laurent (Belgium). [riftveil.ai](https://riftveil.ai) · [attestscope.ai](https://attestscope.ai) · hello@riftveil.ai
