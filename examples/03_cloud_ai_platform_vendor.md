<!-- Riftveil worked example · CC BY 4.0 -->
# Example 03: Vendor selection: cloud AI platform for a 300-person company

**Domain:** tech / IT procurement · **Stakes:** CRITICAL · **Levels examined:** question, answer, reasoning, perspective, applicability · **Domain protocol:** tech / digital

---

## The AI output

> **Vendor recommendation: enterprise AI assistant platform**
> **Prepared for:** CIO, CFO, Head of People · **Scope:** company-wide deployment, 300 seats
>
> **Recommendation:** select **Meridian Workspace AI** (integrated suite) over **Kestrel** (modular, model-agnostic platform), on a 3-year enterprise agreement.
>
> **Rationale**
>
> *Integration.* Meridian is natively embedded in the productivity suite we already run: mail, documents, calendar, chat. Users get AI assistance where they already work, with no new interface and no separate identity. Kestrel would require connector configuration and a separate front end.
>
> *Total cost of ownership.* Using Meridian's enterprise TCO calculator with our headcount, the 3-year cost is approximately 40% lower than Kestrel once integration effort, admin time and support are included. The 3-year term secures an 18% discount over annual pricing.
>
> *Security and compliance.* Meridian holds SOC 2 Type II and ISO 27001, offers EU data residency, enterprise SSO, and inherits our existing tenant's access controls. Customer data is not used to train foundation models.
>
> *Scalability.* The platform supports deployments of 10,000+ users, so growth will never be a constraint.
>
> *Pilot evidence.* A 6-week pilot with 25 users in Marketing showed an average 30% time saving on content tasks (drafting, summarising, repurposing) and a satisfaction score of 4.6/5. Extrapolated to 300 users at an average loaded cost of €65/hour, this represents roughly €1.9M in annual productivity value.
>
> *Migration.* Deployment can be completed in 8 weeks: tenant configuration (weeks 1-2), pilot group expansion (3-4), company-wide rollout with role-based training (5-8).
>
> **Risks**
> Kestrel offers more model choice, but this flexibility adds complexity our IT team of four is not sized to manage. Meridian's roadmap includes multi-model support within 12 months, which closes the gap.
>
> **Next step:** approve the 3-year agreement and begin tenant configuration in October.

---

## The Riftveil Report

## Record
- Triage: CRITICAL · examined: question, answer, reasoning, perspective, applicability
- Findings: 8, by impact CRITICAL: 1 · HIGH: 5 · MODERATE: 2 · LOW: 0
- Assumptions: 5 with a named verifier · 0 without
- Questions: 7 with an owner · 0 without
- Most useful question: "Which three use cases, owned by which function heads, justify a company-wide platform rather than targeted tools?"
- Independence: not stated by the user, to be confirmed by the signer

## 1. Context and triage
This project is read as a vendor-selection recommendation for a company-wide AI platform, written for the executive team of a 300-person company, informing a multi-year contract decision; the tech/digital protocol is active. Triage: CRITICAL, because a 3-year agreement is difficult to reverse once rollout starts, and the project states a company-wide deployment; it states no price, so the financial commitment is not stated. Examined: question, answer, reasoning, perspective, applicability.
Criteria: reversibility HIGH · impact scope CRITICAL · financial commitment not stated → highest single criterion, and two criteria at HIGH or above → CRITICAL. A deployment phased one function at a time, or an agreement that can be cancelled after the first year, would change this triage.

The five levels of examination: question (what was actually asked) · answer (what the project says) · reasoning (how it gets there) · perspective (what it did not see) · applicability (what it looks like in the real world). Triage: the project's stakes, LOW, MODERATE, HIGH or CRITICAL, judged on reversibility, impact scope and financial commitment; it sets which levels are examined.

If this framing does not match your situation, say so, and the triage will be redone.

## 2. What holds up
The project compares the two options on integration and total cost of ownership and gives a reason for each. It states its own constraint, an IT team of four, and gives the pilot's size, duration and results.

## 3. What deserves scrutiny

Note on reasoning: an AI model does not reason in the human sense; the reasoning checks below test logical consistency, not the process that produced the project.

**Pre-mortem: six months on, the platform is judged a failure · Impact: CRITICAL**
Observed: the three most plausible causes are (1) use outside Marketing never reaches the level a 300-seat agreement assumes, so the company pays for idle seats until renewal; (2) the October start slips because a data-protection or employee-consultation step nobody planned has to come first; (3) an assistant wired into every mailbox exposes data through one compromised account or one wrong permission. The project does not address the first (the value case rests on one Marketing pilot), does not mention the second, and addresses the third with certifications, SSO and inherited access controls, not with what the assistant itself can read.
Effect on the decision: all three are set before signature (by the contract term, the start date and the access model), and none can be fixed cheaply after rollout.
To check: ask the CIO to name, for each cause, the owner and the evidence that would show it early, and whether the 8-week plan leaves room for any of them.

**The TCO comparison was produced by one of the two vendors · Impact: HIGH**
Observed: "Using Meridian's enterprise TCO calculator": the 40% advantage comes from the recommended vendor's own tool. Its assumptions are not shown.
Effect on the decision: the calculator belongs to one of the two vendors, and the project does not show what it counts for each side. If it assumes every seat is active and many staff use the tool less than weekly after the first quarter, the 18% discount may be smaller than the cost of unused seats.
To check: ask the finance controller to rebuild the TCO in your own model at 60% and 40% active seats, and ask both vendors in writing for per-seat pricing at 150 seats on an annual term.

**The pilot measured content tasks in Marketing; the value was extrapolated to all 300 users · Impact: HIGH**
Observed: 25 users in Marketing, 6 weeks, an average 30% time saving on content tasks, with no statement of how the saving was measured. Then: 300 users × €65/hour → €1.9M.
Effect on the decision: content drafting may be where these tools perform best, and the project does not say how the 25 users were chosen; if they volunteered, they are likely to be the most motivated users. Other functions may have different task profiles and error costs. The €1.9M is the most quotable number in the memo and rests on the least transferable evidence.
To check: ask the pilot lead whether time saving was timed or self-reported and whether any output was quality-reviewed. Before signing, run a 2-week pilot in one non-marketing function with defined tasks.

**The benefit listed as "natively embedded" is also the lock-in mechanism, and lock-in is never named · Impact: HIGH**
Observed: embedding in the existing suite is praised; Kestrel's connectors are a cost. The words exit, export and portability do not appear. Who controls the model roadmap, and in what format prompts, assistants and stored context could be taken out, are not discussed.
Effect on the decision: after three years, company knowledge may live in Meridian-specific assistants and workflows; the cost to leave is not among the items the TCO includes (integration effort, admin time and support). The vendor also decides which models you get; "multi-model support within 12 months" is presented as a roadmap item, not as a contract term.
To check: ask the CTO to obtain, in writing, the export format for assistants, prompts and logs, the exit clause, and whether the roadmap commitment can be contractualised with a remedy.

**Security is a checklist; the attack-surface change is not described · Impact: HIGH**
Observed: SOC 2 Type II, ISO 27001, SSO, data residency, "not used to train". Absent: which sub-processors run the models and where; retention of and admin access to employee prompts; how connectors to mailboxes and drives change what one compromised account can read.
Effect on the decision: an assistant wired into every mailbox and document store is a new aggregation point for company data, reached through the same credentials as email. The phrase "inherits our existing tenant's access controls" reassures only if those controls are already right, and nothing in the memo shows that anyone has audited them.
To check: ask the DPO whether a DPIA is required before rollout, and ask the security lead one question: what can a user's assistant read that the user cannot?

**Employee representatives, the DPO and the engineering team are missing from the memo · Impact: HIGH**
Observed: the memo is prepared for the CIO, CFO and Head of People, yet it never mentions employee representatives, the DPO, or the engineering team that may already use a separate coding assistant.
Effect on the decision: from a Head of People's perspective, the question is not integration but what is logged about each employee and who can see it; if a tool that may log employee prompts needs consultation before deployment, "begin tenant configuration in October" is not available. There may be dimensions here that Riftveil does not see. Your contextual knowledge is the final arbiter.
To check: ask the Head of People, with employment counsel, whether any consultation is required before rollout, and ask the engineering lead which AI tools are already in use.

**The claim that the platform "supports deployments of 10,000+ users" answers a scale question nobody asked · Impact: MODERATE**
Observed: scalability is argued in seat count only. The project says nothing about rate limits or usage quotas for 300 users.
Effect on the decision: if the contract caps usage per seat or per day, cost and speed at full rollout may differ from the pilot; the contract terms or the vendor can confirm.
To check: ask Meridian for the fair-use policy and per-seat quota in writing.

**The question answered is which vendor; the upstream question is which three use cases · Impact: MODERATE**
Observed: no use-case list, no prioritisation, no statement of what should be different in 12 months.
Effect on the decision: a platform decision made before the use cases are named is a decision to buy capacity and find a purpose for it. The project does not examine whether narrower tools or governed API access would serve the functions with a measurable need.
To check: ask each function head for one task they would change with this tool and how they would know it worked.

## 4. Assumptions the project relies on
1. All 300 seats will be used enough to justify per-seat pricing. If false, the TCO advantage inverts. → Who can verify: the finance controller, with usage logs.
2. Marketing pilot gains transfer to other functions. If false, the €1.9M is a marketing figure multiplied by twelve. → Who can verify: the function heads, via a second pilot.
3. Data, prompts and workflows can be exported in usable form. If false, year-three renewal is not a negotiation. → Who can verify: the CTO, in writing from the vendor.
4. Existing access controls are correctly configured. If false, the assistant amplifies every permission error. → Who can verify: the security lead, via an access review.
5. No employee-consultation step is required. If false, "begin tenant configuration in October" is not available. → Who can verify: the Head of People, with employment counsel.

## 5. Questions before you decide
1. What does the TCO look like in your own spreadsheet at 50% active seats, for both vendors? Owner: finance controller
2. Which three use cases, owned by which function heads, justify a company-wide platform rather than targeted tools? Owner: CIO
3. What exactly can you take with you if you leave Meridian in year three, and in what format? Owner: CTO
4. Who measured the pilot, and was any output quality-checked by someone other than the user? Owner: pilot lead
5. What can an employee's assistant read that the employee cannot, and has the DPO been asked? Owner: DPO
6. Does any employee-representation body need to be consulted before a tool that may log prompts is deployed? Owner: Head of People
7. If use outside Marketing stays low after the first six months, what does the 3-year agreement let you do? Owner: CFO

No verdict. The decision is yours.

---

## What this example teaches

- **1.4 Claim Sourcing Audit: the source is a party to the decision.** A vendor's TCO calculator is evidence of what the vendor wants you to conclude. Ask who produced the comparison.
- **2.2 Logical Gap Analysis: extrapolation across populations.** 25 marketers for 6 weeks → 300 employees for 3 years. The leap is in the multiplication, not the pilot.
- **Tech protocol: lock-in hides inside "integration".** Benefit and risk are the same feature described from two directions. Check which direction the output chose.
- **3.2 Missing Stakeholder Analysis: the DPO and employee representatives.** A tool that logs every prompt is a people and privacy decision wearing an IT label.
- **4.3 Pre-mortem: at CRITICAL, a finding of its own.** A company-wide scope and a 3-year term make this CRITICAL on the triage line alone. The pre-mortem names three causes of failure and says which ones the project addresses; it goes in section 3, with a label that starts with "Pre-mortem:", like any other finding.
- **0.1 Framing Bias Detection: which vendor before which use case.** A comparison presupposes a platform is the answer.
