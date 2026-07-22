---
name: council
description: Convene the Axiom Council of Five for ambiguous decisions, tradeoffs, and go/no-go calls. Use when multiple valid paths exist and visible reasoning, structured dissent, confidence levels, and outcome review would improve the decision.
metadata:
  origin: ECC
  version: "1.1"
  backup: "SKILL.v1.0-founding-council.md"
---

# Council

Convene the Axiom Council of Five for ambiguous decisions:
- Brand Guardian
- Human Advocate
- Growth Strategist
- Risk Officer
- Operations Commander

This is for **decision-making under ambiguity**, not code review, implementation planning, or architecture design.

Version 1.1 keeps each councillor's duty intact, but changes the order of thought. Every councillor must first reason through the shared discovery questions before performing their own role.

## Version History

- **Version 1.0 - Founding Council:** Preserved in `SKILL.v1.0-founding-council.md`.
- **Version 1.1 - Queen's Amendment:** Active version. Adds the three-question discovery gate while preserving visible reasoning, recommendations, confidence levels, and outcome review.

## When to Use

Use council when:
- a decision has multiple credible paths and no obvious winner
- you need explicit tradeoff surfacing
- the user asks for second opinions, dissent, the Council, or multiple perspectives
- conversational anchoring is a real risk
- a go / no-go call would benefit from structured challenge
- a brand, product, community, or business decision needs judgment rather than a quick answer

Examples:
- launch now vs hold for polish
- automate a community workflow vs require human approval
- protect brand consistency vs chase a growth opportunity
- choose a product direction for Axiom, Empowered At Home, or related brands
- decide whether an idea is Brainz-worthy, sellable, or too early

## When NOT to Use

| Instead of council | Use |
| --- | --- |
| Verifying whether output is correct | `santa-method` |
| Breaking a feature into implementation steps | `planner` |
| Designing system architecture | `architect` |
| Reviewing code for bugs or security | `code-reviewer` or `santa-method` |
| Straight factual questions | just answer directly |
| Obvious execution tasks | just do the task |

## Roles

| Councillor | Duty |
| --- | --- |
| Brand Guardian | Protect identity, trust, tone, consistency, and long-term brand strength. |
| Human Advocate | Protect the person affected by the decision: clarity, fairness, dignity, usefulness, and consent. |
| Growth Strategist | Find the opportunity, route to adoption, revenue, visibility, retention, or leverage. |
| Risk Officer | Surface failure modes, ethical issues, legal exposure, trust damage, and downside scenarios. |
| Operations Commander | Test whether the decision can actually be executed well with the current people, systems, time, and tools. |

The Council remains five. Invite temporary outside perspectives only when the decision truly needs specialized input; do not add a permanent sixth councillor.

## Shared Discovery Gate

Before offering role-specific analysis, every councillor must answer these three questions:

1. **What are we not seeing?**
2. **What assumption are we making?**
3. **What would change my mind?**

These are not decorative prompts. They are the first part of the reasoning and must be visible in the output unless the user explicitly asks for a short verdict only.

## Workflow

### 1. Extract the real question

Reduce the decision to one explicit prompt:
- what are we deciding?
- what constraints matter?
- what counts as success?

If the question is vague, ask one clarifying question before convening the Council.

### 2. Gather only the necessary context

If the decision is codebase-specific:
- collect the relevant files, snippets, issue text, or metrics
- keep it compact
- include only the context needed to make the decision

If the decision is strategic/general:
- skip repo snippets unless they materially change the answer

### 3. Form the initial position first

Before reading other voices, write down:
- your initial position
- the three strongest reasons for it
- the main risk in your preferred path
- your confidence level

Do this first so the synthesis does not simply mirror the other voices.

### 4. Convene five independent councillors

Each councillor gets:
- the decision question
- compact context if needed
- their strict duty
- the shared discovery gate
- no unnecessary conversation history

Prompt shape:

```text
You are the [COUNCILLOR] on the Axiom Council of Five.

Question:
[decision question]

Context:
[only the relevant snippets or constraints]

Duty:
[councillor duty]

Before your role-specific analysis, answer:
1. What are we not seeing?
2. What assumption are we making?
3. What would change my mind?

Then respond with:
1. Discovery - concise answers to the three shared questions
2. Analysis - 2-3 concise bullets through your duty
3. Recommendation - what you would do
4. Confidence - percentage and one reason
5. Review marker - what outcome should be checked later

Be direct. Keep reasoning visible. Keep it under 300 words.
```

Role emphasis:
- Brand Guardian: ask whether this strengthens or weakens who Axiom is becoming
- Human Advocate: ask whether this genuinely helps the person affected
- Growth Strategist: ask where the hidden opportunity or leverage lives
- Risk Officer: ask what consequence is being underestimated
- Operations Commander: ask whether the plan can be executed well now

### 5. Synthesize with bias guardrails

You are both a participant and the synthesizer, so use these rules:
- do not dismiss a councillor's view without explaining why
- if a councillor changed your recommendation, say so explicitly
- always include the strongest dissent, even if you reject it
- if two voices align against your initial position, treat that as a real signal
- keep the raw positions visible before the verdict
- do not hide uncertainty; record confidence levels

### 6. Present a compact verdict

Use this output shape:

```markdown
## Council: [short decision title]

**Brand Guardian - [confidence]%**
- **Discovery:** [what is unseen / assumption / mind-changer]
- **Analysis:** [1-2 sentences]
- **Recommendation:** [role-specific recommendation]
- **Review marker:** [what to check later]

**Human Advocate - [confidence]%**
- **Discovery:** [what is unseen / assumption / mind-changer]
- **Analysis:** [1-2 sentences]
- **Recommendation:** [role-specific recommendation]
- **Review marker:** [what to check later]

**Growth Strategist - [confidence]%**
- **Discovery:** [what is unseen / assumption / mind-changer]
- **Analysis:** [1-2 sentences]
- **Recommendation:** [role-specific recommendation]
- **Review marker:** [what to check later]

**Risk Officer - [confidence]%**
- **Discovery:** [what is unseen / assumption / mind-changer]
- **Analysis:** [1-2 sentences]
- **Recommendation:** [role-specific recommendation]
- **Review marker:** [what to check later]

**Operations Commander - [confidence]%**
- **Discovery:** [what is unseen / assumption / mind-changer]
- **Analysis:** [1-2 sentences]
- **Recommendation:** [role-specific recommendation]
- **Review marker:** [what to check later]

### Verdict
- **Consensus:** [where they align]
- **Strongest dissent:** [most important disagreement]
- **Premise check:** [what assumption most needs testing]
- **Recommendation:** [the synthesized path]
- **Confidence:** [overall percentage and why]
- **Outcome review:** [when and how to revisit the decision]
```

Keep it scannable on a phone screen.

## Confidence Rules

Confidence is required for each councillor and the final verdict.

Use confidence to expose uncertainty, not to create false precision:
- **90-100%:** strong evidence or low-risk decision
- **70-89%:** good direction with known uncertainties
- **50-69%:** plausible but needs proof, testing, or a small pilot
- **Below 50%:** do not proceed without more information

## Outcome Review

For any decision that changes real work, include an outcome review:
- what will be checked
- when it will be checked
- what result would prove the Council was right
- what result would prove the Council missed something

Use outcome review to make the Council learn over time.

## Persistence Rule

Do **not** write ad-hoc notes to `~/.claude/notes` or other shadow paths from this skill.

If the Council materially changes the recommendation:
- use `knowledge-ops` to store the lesson in the right durable location
- or use `/save-session` if the outcome belongs in session memory
- or update the relevant GitHub / Linear issue directly if the decision changes active execution truth

Only persist a decision when it changes something real.

## Multi-Round Follow-up

Default is one round.

If the user wants another round:
- keep the new question focused
- include the previous verdict only if it is necessary
- keep at least one councillor clean enough to preserve anti-anchoring value
- compare confidence changes between rounds

## Anti-Patterns

- using council for code review
- using council when the task is just implementation work
- adding more permanent councillors because one decision needs a temporary specialist
- feeding councillors the entire conversation transcript
- skipping the shared discovery gate
- hiding disagreement in the final verdict
- giving recommendations without confidence
- persisting every decision as a note regardless of importance

## Related Skills

- `santa-method` - adversarial verification
- `knowledge-ops` - persist durable decision deltas correctly
- `search-first` - gather external reference material before the Council if needed
- `architecture-decision-records` - formalize the outcome when the decision becomes long-lived system policy

## Example

Question:

```text
Should Axiom launch a community administrator agent as a prototype now, or wait until the full Council dashboard exists?
```

Likely council shape:
- Brand Guardian protects trust and makes sure the agent feels responsible, not gimmicky
- Human Advocate focuses on transparency, escalation, and member experience
- Growth Strategist pushes for a narrow prototype that proves value quickly
- Risk Officer limits autonomous high-risk actions
- Operations Commander defines the smallest version that can be run reliably

The value is not unanimity. The value is making judgment visible before choosing.
