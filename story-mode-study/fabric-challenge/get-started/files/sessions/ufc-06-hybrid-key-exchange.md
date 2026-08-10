# UFC-06 — Hybrid Key Exchange

**Week:** 2  
**Target duration:** 25–35 min  
**Mode:** Socratic + short teaching

## Source Scope

- Hybrid key exchange

## Learning Objectives

- Understand the high-level purpose of the listed hybrid key exchange task.
- Separate mechanism from verification.
- Recognise when a scenario is testing key exchange rather than SSL enforcement.

## Mental Model

**Configure the mechanism → prove the negotiated result**

## Cold-Start Question

> Why would the challenge award points separately for hybrid key exchange and hybrid key verification?

Ask this first. Do not explain before the learner attempts it.

## Socratic Path

Guide the learner through these stages, one question at a time:

1. **Identify** — What component, stage, or behaviour is the scenario testing?
2. **Explain** — Why does that component/stage exist?
3. **Connect** — What comes before and after it in the workflow?
4. **Verify** — What evidence would prove the intended result is actually occurring?
5. **Troubleshoot** — If the expected result fails, what broad category would you inspect first?

Do not ask all five questions at once.

## Hint Ladder

If the learner is wrong:

- **Hint 1:** Point toward the relevant stage of the workflow.
- **Hint 2:** Eliminate one incorrect category or contrast two similar concepts.
- **Hint 3:** Give the structure of the answer but leave the final conclusion to the learner.

Only then provide the short explanation.

## Short Teaching Guardrails

- Keep explanations brief.
- Stay within the supplied UFC objective scope.
- Do not invent exact GUI paths, CLI syntax, defaults, signatures, hidden answers, or product behaviour not supported by provided material.
- If exact Fortinet implementation detail is needed, clearly label it **Requires official Fortinet source verification**.
- Focus on the mental model and the reasoning the learner needs for UFC recognition.

## Apply It

Create a second scenario that changes one variable while testing the same mental model.

Do not reuse the same wording as the cold-start question.

## Break It

Introduce one failure.

Ask:

> What would you check first, and why?

Then ask what evidence would distinguish between at least two plausible failure categories.

## UFC Check

**Challenge style:** Concept recognition

Use one short challenge.

As the weeks progress:
- Weeks 1–2: untimed, hints available.
- Weeks 3–4: light timing, fewer hints.
- Weeks 5–6: incomplete evidence and investigation.
- Week 7: timed, mixed-domain pressure.

## Close

### Key Takeaways
Claude writes 2–4 concise bullets based on the learner's actual session.

### Mental Model
Restate the mental model in one sentence.

### Common UFC Trap
Write one confusion that is relevant to the learner's mistakes.

### Challenge Question
Ask one unanswered question.

Do not reveal the answer until the learner responds.

## Tracking Update

After the learner answers the final challenge:
- update `../tracking/KNOWLEDGE-REGISTER.md`,
- update `../tracking/REVIEW-QUEUE.md`,
- append to `../tracking/SESSION-LOG.md`.

Track:
- hints used,
- mistakes,
- mental model quality,
- recognition,
- troubleshooting,
- verification reasoning,
- speed.
