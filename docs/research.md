# Research

The references the protocol relies on, and what they show.

Riftveil exists to work on one failure mode: **automation bias with a human signature**. A professional approves an AI output (signs it, forwards it, submits it), and the approval is a rubber stamp rather than independent judgment, usually under time pressure, behind text that reads as if someone had already checked. Automation bias is documented (Parasuraman & Manzey 2010; Bainbridge 1983), and Article 14(4)(b) of the EU AI Act obliges providers of high-risk systems to design them so that the people overseeing them can remain aware of it: a direction, not a compliance label; under the AI Omnibus (in force since 27 July 2026), those obligations apply from 2 December 2027, and from 2 August 2028 for AI embedded in regulated products. Outside the European Union, other rules and deadlines may apply where you work. Riftveil gives the signature its value back: a record, assumptions with a named verifier, questions with an owner. A signature with a record behind it is no longer a rubber stamp.

The record has to come from outside the model. Asking a model "are you sure?" is not a method. The research is consistent:

- Without external feedback, self-correction can degrade rather than improve performance (Huang et al., Google DeepMind, *ICLR 2024*).
- Models fail to correct their own errors 64.5% of the time while correcting identical errors presented as coming from an external source (Tsui, 2025, 14 open-weight, non-reasoning models). The same paper shows a simple prompt cue reduces the blind spot substantially; the case for a protocol rests on record and role, not on prompts being useless.
- No successful self-correction with LLM-only feedback has been demonstrated (Kamoi et al., *TACL 2024*).
- Prompting alone does not produce reliable self-correction; obtaining it required dedicated reinforcement-learning training (Kumar et al., SCoRe, Google DeepMind, *ICLR 2025 Oral*).
- Self-correction improves accuracy overall, but gains are limited for reasoning models under additional self-correction (*CorrectBench, NeurIPS 2025*).
- Models rarely express uncertainty spontaneously; fluent, unhedged output induces overconfidence in the reader (Zhou et al., 2024).
- When challenged, models can counter-attack rhetorically rather than reconsider ("persuasion bombing"): Randazzo et al., *HBS Working Paper 26-021*, 2026; reported in *Harvard Business Review*, March 2026.

Riftveil is not external feedback in the sense those papers use (ground truth, tools, humans, another oracle). What it changes is the model's role and the record: the model becomes an adversarial reviewer running fixed procedures (five levels of challenge, procedural detection heuristics) on an output that arrives as an external object, and it produces a record that cannot end on a verdict, in which every assumption has a human verifier and every question an owner. The structure is for the human's check. It mitigates the limitation; it does not remove it. The final arbiter is the human and their context.
