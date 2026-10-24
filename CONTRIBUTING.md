# Contributing to the Riftveil Protocol

Thank you. Three kinds of contribution are useful; one kind is not.

## Useful

**A detection heuristic.** A concrete, procedural check that surfaces something the current techniques miss. Open an issue first with: the technique it belongs to (or a proposed new one), the procedure in numbered steps, and one real (anonymised) output where it would have made a difference.

**A failure case.** An AI output where Riftveil produced a weak, wrong or narratively coherent-but-useless challenge. Attach the input, the report, and what a competent human would have flagged instead. These are the most valuable contributions we get.

**A translation or integration recipe.** Native-quality translations of the protocol (not machine translations), or a tested step-by-step for running it in a tool we don't cover yet.

## Not accepted

Anything that would make Riftveil **validate, rewrite or conclude**, or present its challenge as complete. No "overall assessment" sections, no confidence scores, no rewritten versions of the output, no closing summaries. These four rules are the product. A pull request that softens them will be closed with thanks.

## Process

1. Open an [issue](https://github.com/riftveil-ai/riftveil-protocol/issues) before a pull request for anything beyond a typo.
2. Keep the protocol's voice: procedural, specific, no filler.
3. One change per pull request. Update `CHANGELOG.md`.
4. By contributing you agree your contribution is licensed under Apache 2.0 (protocol) or CC BY 4.0 (written content). Riftveil is the subject of Benelux trade mark application No. 1559982.

## Versioning

`MAJOR.MINOR.PATCH`, starting from v1.0.0, the first public release. A PATCH bump (v1.0.1, v1.0.2) tightens how the protocol is applied (checks, wording, examples, the wording of a triage criterion's steps) without changing a rule, a level or a technique. A MINOR bump adds or refines techniques without changing the report structure. A MAJOR bump changes levels, the triage mechanics (criteria, levels, escalation rule) or the report format: teams that pinned a version should re-read before upgrading.
