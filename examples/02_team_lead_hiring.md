<!-- Riftveil worked example · CC BY 4.0 -->
# Example 02: Hiring recommendation: two candidates for a team-lead role

**Domain:** HR / people decisions · **Stakes:** MODERATE · **Levels examined:** question, answer, reasoning

---

## The AI output

> **Recommendation: Engineering Team Lead, Platform Team**
>
> After reviewing both candidate packs, interview notes, and the structured panel scores, I recommend offering the role to **Maya R.** (internal, Senior Engineer, 6 years with the company) over **Daniel K.** (external, Team Lead at a larger fintech for 4 years).
>
> **Why Maya**
>
> Maya's leadership potential was evident throughout the payments-migration project, where she coordinated four engineers without formal authority and delivered on time. The team already trusts her, which removes the 3-6 month ramp-up an external hire would need to learn the codebase, the domain and the people. Internal promotions to first-line management succeed about 87% of the time versus roughly 60% for external hires into equivalent roles, largely because of this contextual knowledge. There is also a retention consideration: passing over a strong internal candidate for an external one is a well-known trigger for attrition, and Maya would be difficult to replace.
>
> **Why not Daniel**
>
> Daniel scored slightly higher on the structured interview (4.3 vs 4.0 on the panel rubric) and brings real management experience, including running performance cycles and hiring. However, his experience is in a 400-engineer organisation with dedicated process support; our 40-engineer setup requires a lead who is still hands-on. His examples of conflict resolution relied on escalation paths that do not exist here.
>
> **Risks and mitigation**
>
> Maya has no formal management experience. This is mitigated by enrolling her in the internal first-time-manager programme and pairing her with the Engineering Director as mentor for the first two quarters. Daniel's stronger interview performance reflects interview practice more than capability difference, which is common for external candidates.
>
> **Recommendation:** offer to Maya at the Team Lead band, with Daniel kept warm for a future senior IC or lead opening.

---

## The Riftveil Report

## Record
- Triage: MODERATE · examined: question, answer, reasoning · not examined: perspective, applicability
- Findings: 6, by impact CRITICAL: 0 · HIGH: 2 · MODERATE: 4 · LOW: 0
- Assumptions: 5 with a named verifier · 0 without
- Questions: 5 with an owner · 0 without
- Most useful question: "What does the Platform Team need from its lead in the next 18 months, and which candidate's evidence maps to that?"
- Independence: not stated by the user, to be confirmed by the signer

## 1. Context and triage
This project is read as a hiring recommendation for a first-line engineering management role, likely written for the hiring manager and an HR business partner, informing a choice between two shortlisted candidates. Triage: MODERATE, because the decision is reversible with effort (probation period, role redesign), it affects one team, and the marginal financial commitment between the two options is small: a lead will be paid either way. Examined: question, answer, reasoning; not examined: perspective, applicability.
Criteria: reversibility MODERATE · impact scope MODERATE · financial commitment LOW → highest single criterion → MODERATE. A budget line or headcount plan attached to the role, or a competing offer for either candidate, would raise the triage to HIGH.

The five levels of examination: question (what was actually asked) · answer (what the project says) · reasoning (how it gets there) · perspective (what it did not see) · applicability (what it looks like in the real world). Triage: the project's stakes, LOW, MODERATE, HIGH or CRITICAL, judged on reversibility, impact scope and financial commitment; it sets which levels are examined.

If this framing does not match your situation, say so, and the triage will be redone.

## 2. What holds up
The project names both candidates' evidence bases (project record, structured panel scores, management history) and states a risk of its own recommendation. It names organisational scale and retention as factors in its choice.

## 3. What deserves scrutiny

Note on reasoning: an AI model does not reason in the human sense; the reasoning checks below test logical consistency, not the process that produced the project.

**The recommendation overrides the structured evidence with unstructured evidence, and does not say so · Impact: HIGH**
Observed: Daniel scored higher on the structured panel (4.3 vs 4.0). The recommendation goes the other way, on the strength of "leadership potential was evident throughout the payments-migration project" and "The team already trusts her". The panel result is then explained away as "interview practice".
Effect on the decision: structured interviews exist to reduce the weight of impressions like these. If the process is to be overruled, that should be a visible decision by the hiring manager, not an unmarked step inside a recommendation. The explanation also cuts both ways: an internal candidate's project record is observed by colleagues who already trust her, and the project does not say whether that was weighed against the panel score.
To check: ask the panel lead whether "leadership" was a scored dimension and what Maya scored on it. Ask who contributed the migration-project observations and whether any of them would report to Maya in the new role.

**The 87% vs 60% statistic has no source, and would not transfer even if it had one · Impact: HIGH**
Observed: two precise percentages on internal-versus-external promotion success, presented as fact with no study, population or definition of "succeed".
Effect on the decision: figures this precise with no source may have been generated rather than measured, and the project gives nothing to rule that out. Even if a survey stands behind them, it would describe other organisations, and it may be skewed by selection: if internal candidates are promoted once they have already shown the behaviour, their success rate partly measures the decision, not the candidate type.
To check: ask your HR business partner for your own numbers: first-line leads promoted internally versus hired externally in the last five years, and how many were still in role at 18 months.

**Retention risk is counted on one side only · Impact: MODERATE**
Observed: the project counts the risk of losing Maya if she is passed over. It does not count the loss of her engineering output if she codes less, the risk that she leaves within 12 months because she dislikes managing, or the team losing a strong internal candidate from hands-on engineering and gaining a first-time manager at the same time.
Effect on the decision: "Maya would be difficult to replace" is an argument for keeping her as an engineer as much as for promoting her. The asymmetry makes the recommendation look safer than it is.
To check: ask the Engineering Director whether Maya has said she wants to manage, or whether it is assumed. Ask who absorbs her current technical scope from day one.

**Trust as a peer is treated as trust as a manager · Impact: MODERATE**
Observed: "The team already trusts her" is used as evidence that the ramp-up disappears. The migration project was peer coordination without authority.
Effect on the decision: the peer-to-manager transition inside the same team changes the relationship itself: the person who coordinated peers without authority would now have authority over them. The project collapses two relationships into one.
To check: ask whether anyone on the team was consulted, and whether any team member applied for the role and was not shortlisted.

**The mitigation assumes bandwidth nobody has confirmed · Impact: MODERATE**
Observed: the no-management-experience risk is "mitigated" by a training programme and two quarters of mentoring by the Engineering Director.
Effect on the decision: a mitigation that depends on a senior person's calendar is a hope until that person has agreed.
To check: ask the Engineering Director directly, with the hours per week attached.

**The question answered is which candidate, not what this team needs · Impact: MODERATE**
Observed: the role is described through the candidates; apart from "a lead who is still hands-on", there is no statement of what the Platform Team needs from its lead over the next 18 months: stabilisation, growth, hiring, a process rebuild.
Effect on the decision: if the team is about to double, Daniel's hiring and performance-cycle experience is the core requirement, not a nice-to-have. If the team is stable, Maya's profile fits. The project supplied its own frame.
To check: ask the hiring manager to write the one-paragraph mandate for the role before reading either file again.

## 4. Assumptions the project relies on
1. The structured panel scores are less reliable than project observations. If false, the recommendation is backwards. → Who can verify: the panel lead, with the rubric.
2. Maya wants to manage. If false, you promote someone into a role she may leave. → Who can verify: the Engineering Director, from direct conversation.
3. Someone will absorb Maya's technical scope. If false, the team loses delivery capacity in the transition quarter. → Who can verify: the hiring manager, with the sprint plan.
4. The Engineering Director has two quarters of mentoring capacity. If false, the stated mitigation does not exist. → Who can verify: the Engineering Director.
5. The team's next 18 months resemble its last 18 months. If the team is scaling, the external candidate's experience becomes the requirement. → Who can verify: the owner of the headcount plan.

## 5. Questions before you decide
1. What does the Platform Team need from its lead in the next 18 months, and which candidate's evidence maps to that? Owner: hiring manager
2. If you overrule the structured panel, will you record why, and would that reason survive a look from HR? Owner: hiring manager, with the HR business partner
3. Has Maya told anyone she wants this role, or has it been assumed on her behalf? Owner: Engineering Director
4. Has the Engineering Director agreed to the mentoring commitment, in hours per week? Owner: Engineering Director
5. What did the team say, or has nobody asked? Owner: hiring manager

No verdict. The decision is yours.

---

## What this example teaches

- **2.2 Logical Gap Analysis: the evidence hierarchy inversion.** When an output cites a structured measure and then decides against it, look for the sentence that explains the override. If there isn't one, the reasoning has a hidden leap.
- **1.4 Claim Sourcing Audit: precise percentages on people decisions.** "87% vs 60%" reads as research. Replace it with your own organisation's five-year data; the argument either survives or it doesn't.
- **2.1 Assumption Surfacing: asymmetric risk accounting.** Retention risk, ramp-up cost and mitigation capacity were each counted on one side only. Write each risk twice, once per option.
- **0.1 Framing Bias Detection: "which candidate" hides "what role".** A comparison between two people quietly defines the job as whatever the better candidate is good at.
- **Generic lesson:** people decisions are where AI outputs feel most reasonable and are least checkable, because the evidence is anecdote wearing the vocabulary of assessment.
