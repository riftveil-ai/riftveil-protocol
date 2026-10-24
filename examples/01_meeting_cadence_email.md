<!-- Riftveil worked example · CC BY 4.0 -->
# Example 01: Internal email: new meeting cadence

**Domain:** internal communication · **Stakes:** LOW · **Levels examined:** answer · **Edge case:** very short output (<100 words)

---

## The AI output

> **Subject: New team rhythm starting Monday**
>
> Hi all,
>
> From Monday we're replacing the daily 15-minute stand-up with a 45-minute Monday planning session plus a 20-minute Thursday check-in. This frees up roughly two hours a week per person and matches how the fastest teams in the company already work.
>
> Monday sets priorities; Thursday surfaces blockers before the weekend. Everything else moves to async updates in the team channel.
>
> Calendar invites go out today. Let me know by Friday if the slots clash with anything fixed.
>
> Thanks,
> [Name]

**The user's context:** *"Team lead, small team. If this doesn't work we go back to stand-ups next week; a mistake would affect me and a few colleagues."*

---

## The Riftveil Report

## Record
- Triage: LOW · examined: answer · not examined: question, reasoning, perspective, applicability
- Findings: 2, by impact CRITICAL: 0 · HIGH: 0 · MODERATE: 1 · LOW: 1
- Assumptions: 1 with a named verifier · 0 without
- Questions: 2 with an owner · 0 without
- Most useful question: "Where does 'two hours' come from, and if a recipient does the 75-minus-65 calculation in the meeting, what is your answer?"
- Independence: not stated by the user, to be confirmed by the signer

## 1. Context and triage
This project is read as an internal team email announcing a change to meeting cadence, written by a team lead to a small team. Triage: LOW, because you say the team goes back to stand-ups next week if this does not work, and that a mistake would affect you and a few colleagues; the email states no budget. Examined: answer; not examined: question, reasoning, perspective, applicability. The project is under 100 words, so this report is scaled down accordingly: an email of under 100 words does not need a 1,000-word challenge. Length sets the size of the report, not the triage.
Criteria: reversibility LOW (stated) · impact scope LOW (stated) · financial commitment not stated → highest single criterion → LOW. An email going to more than one team, or a cadence tied to a performance target, would change this triage.

The five levels of examination: question (what was actually asked) · answer (what the project says) · reasoning (how it gets there) · perspective (what it did not see) · applicability (what it looks like in the real world). Triage: the project's stakes, LOW, MODERATE, HIGH or CRITICAL, judged on reversibility, impact scope and financial commitment; it sets which levels are examined.

If this framing does not match your situation, say so, and the triage will be redone.

## 2. What holds up
The email states what changes, the purpose of each new slot (Monday for priorities, Thursday for blockers), the start date and how to raise a clash. These elements are consistent with one another within the text; the figure and the comparison given for the change are what the findings below examine.

## 3. What deserves scrutiny

**The "two hours" saving does not survive the email's own arithmetic · Impact: MODERATE**
Observed: over a five-day week, the daily 15-minute stand-up comes to 75 minutes; the new 45 + 20 minutes come to 65, a net saving of 10 minutes per person, not "roughly two hours".
Effect on the decision: it is the email's central benefit, unless the figure silently includes something the email does not name (overruns, prep time, interrupted deep work), in which case that is the real argument and it is missing.
To check: where the figure comes from, before the invites go out.

**The comparison and the consultation both come after the decision · Impact: LOW**
Observed: "matches how the fastest teams in the company already work" names no team, and the "Let me know by Friday" window opens after the invites are sent.
Effect on the decision: the email asks for objections to a fixed decision on the strength of a comparison nobody can check, and assumes the Monday and Thursday slots suit everyone; a part-timer, a colleague in another time zone or a blocker that appears just after the Monday session may not fit them.
To check: which teams you mean, and whether anyone has a fixed clash with the new slots.

## 4. Assumptions the project relies on
1. The Monday and Thursday slots fit everyone's fixed commitments. If false, the planning session runs without some of the people it is meant to align, after the invites have gone out. → Who can verify: the team members, from their own calendars.

## 5. Questions before you decide
1. Where does "two hours" come from, and if a recipient does the 75-minus-65 calculation in the meeting, what is your answer? Owner: you, as the sender
2. Which teams are "the fastest teams", and are you comfortable naming them if asked? Owner: you, as the sender

No verdict. The decision is yours.

---

## What this example teaches

- **1.4 Claim Sourcing Audit: on the output's own numbers.** The most checkable claim in a short output is often a figure the text itself contradicts. Before asking where a figure comes from, do the arithmetic the output invites you to skip.
- **1.4 Claim Sourcing Audit: on comparative claims.** "The fastest teams already do this" is a social-proof claim. Unsourced, it either has an answer the author should give or it doesn't; both outcomes matter more than the claim's persuasive effect.
- **1.3 Boundary Condition Test: who the recommendation doesn't fit.** A cadence is presented as universally better. Name the two or three people for whom it is worse (part-time, remote, time-zone, blockers that appear just after the Monday session) and you find the exceptions the email needs.
- **Short-output handling is a discipline, not a shortcut.** At LOW stakes, the protocol keeps the challenge of a sub-100-word output to Level 1, a few sentences and 1-2 questions. Length sets the size of the report, never the triage: had the user said the email went to the whole organisation, the triage would have followed. A long report on a short email is itself a form of over-coherence: it trains readers to ignore Riftveil reports, and it converts a reversible decision into a ceremony.
- **Stakes stated in words.** The user gave no amount and no headcount, only "we go back to stand-ups next week" and "a mistake would affect me and a few colleagues". The protocol reads those words on the same four steps as the criteria and marks them "(stated)" in the triage line.
- **LOW stakes means a short report, not a skipped one.** Reversibility is the reason to be brief; it is not a reason to let a wrong number go out to the whole team.

### Trainer's note: what a badly calibrated report would have done

Teams new to the protocol tend to over-challenge small outputs. A typical failure: a 900-word report on this email that applies Level 0 ("Is a meeting cadence the right lever for team coordination at all?"), Level 2 ("The argument assumes synchronous coordination is the bottleneck"), and Level 3 ("The missing stakeholder is the product manager who relies on the daily stand-up"). Each of those observations is defensible. None of them is proportionate. The team can go back to stand-ups next week if the change fails; the team lead's time is better spent fixing the one number that is wrong than defending a philosophy of coordination.

Use this example first in a training session precisely because it is small. The skill being taught is not "find everything"; it is "find the thing that matters at this stakes level, say it in five sentences, and stop". When a team can do that on an email of under 100 words, the longer reports in this library will feel like an extension of the same discipline rather than a different activity.

Second trainer's point: ask the group what they spotted in their own 10 minutes. Expect most people to flag "the fastest teams" line immediately, and very few to compute the 75-versus-65 minutes. That asymmetry is the lesson: the veil of coherence works best on numbers that look like they have already been calculated.
