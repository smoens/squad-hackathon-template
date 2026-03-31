← [Docs](../index.md) | [Principles](./)

# Customer First

A hackathon is not a technology showcase. It's a conversation with a customer — in code, data, and demos — about their problems and their future. Every decision, from use case selection to demo narration, should start from their world, not ours.

---

## Their Problem, Their Data, Their Story

### Start from pain, not from tech

The strongest hackathon outcomes begin with something the customer said, not something you wanted to build.

| Approach | Sounds like | Outcome |
|----------|------------|---------|
| **Customer-first** | *"You mentioned 15% rework — what if we could predict which batches will fail?"* | Customer sees themselves in the solution |
| **Tech-first** | *"We've got this great anomaly detection model — let's try it on your data"* | Customer sees a demo, not their problem solved |

The difference is subtle but the impact is enormous. One builds trust. The other builds polite applause.

### Use their language

| Do | Don't |
|----|-------|
| Use the customer's terminology — even if it's not technically precise | Correct their terminology to match yours |
| Name their personas in the demo script: *"Maria, your plant supervisor..."* | Use generic labels: *"the end user"* |
| Reference their KPIs: *"OEE improvement"* | Reference your metrics: *"F1 score"* |

### Use their data

Whenever possible, use the customer's actual data in the hackathon. If that's not accessible, use synthetic data that **mirrors their data shapes** — same column names, same value ranges, same messiness.

| Data scenario | What to do |
|--------------|-----------|
| Customer data available | Use it. It's the most powerful demo prop you have |
| Customer data under NDA or compliance restrictions | Create synthetic data that matches the schema and patterns |
| No customer data at all | Use realistic industry data from public sources + customize field names to match their domain |

> **Tip:** The moment a customer sees their own data on screen, the demo stops being theoretical. That's the moment you want.

---

## Why Starting from Their Pain Points Beats Showcasing Technology

Technology demos impress engineers. Pain-point demos move decision-makers.

In a hackathon, your audience usually includes both — but the decision-maker is the one who funds the follow-up. They don't care about your model architecture. They care about:

- **Will this save us money?**
- **Will this reduce risk?**
- **Can my team actually use this?**

### The Pain-Point Test

Before building anything, every use case should pass this test:

1. **Can the customer articulate this problem without prompting?** If you have to explain why it's a problem, it might not be one.
2. **Does someone in the room feel this pain personally?** Abstract problems produce abstract solutions.
3. **Is there a number attached to the pain?** Hours, dollars, error rates, customer complaints — quantified pain is convincing pain.

If a use case doesn't pass all three, either sharpen it during ideation or deprioritize it.

---

## How to Validate You're Solving the Right Problem

Validation happens continuously, not just in ideation.

### During Ideation

- **After brainstorming:** Read back the top use cases and ask the customer: *"Which of these would make the biggest difference to your team this quarter?"*
- **During feasibility scoring:** Watch the customer's face, not just the scores. If they're disengaged during a high-scoring use case, something's off.

### During Build

- **At the 25% checkpoint:** Show the customer early progress: *"Here's what we're building — is this on the right track?"* A 2-minute hallway conversation can prevent a 4-hour wrong turn.
- **At the 75% checkpoint:** Run through the demo narrative (not the code) with the customer sponsor: *"Here's the story we're going to tell. Does it resonate?"*

### During Demo

- **After the Problem beat:** Pause and check: *"Does that capture the challenge you described this morning?"*
- **After the Impact beat:** Ask: *"Does this direction feel right for your team?"*

> **Tip:** Validation doesn't mean asking for permission at every step. It means keeping the customer close enough that you never end up surprised in the demo.

---

## The Handoff Matters as Much as the Hackathon

A hackathon that ends with applause but no next steps is a failure. The customer gave you their time — the minimum you owe them is a clear path forward.

### What a Good Handoff Includes

| Component | Where it lives | Who owns it |
|-----------|---------------|-------------|
| **What we built** | [HANDOFF.md](../../HANDOFF.md) | Builder + Architect |
| **What we learned** | [RETRO.md](../../RETRO.md) | Facilitator |
| **What's next** | The Ask (demo beat 5) + HANDOFF.md recommendations | Facilitator + Customer sponsor |
| **The code** | This repo — cleaned, documented, runnable | Builder + Data Wrangler |
| **Knowledge captured** | [checklist-knowledge-extract.md](../../.hackathon/checklist-knowledge-extract.md) | Facilitator |

### The Ask Must Be Concrete

| Bad Ask | Good Ask |
|---------|----------|
| *"Let's continue the conversation"* | *"We'd like to schedule a 2-week pilot with Maria's team, starting with the production dataset we identified"* |
| *"We should explore this further"* | *"The next step is access to your SAP system's maintenance logs — can you connect us with your IT team by Friday?"* |
| *"Reach out if you want to move forward"* | *"We'll send a follow-up proposal by next Wednesday with three options: quick win, full pilot, and production deployment"* |

---

## Building Trust Through Transparency

Hackathons are trust-building exercises. The customer is watching how you work as much as what you build.

### What Builds Trust

| Behavior | Why it works |
|----------|-------------|
| **Admitting what you don't know** | Shows honesty over salesmanship |
| **Cutting scope openly** | Shows judgment and professionalism (see [Scope Management](scope-management.md)) |
| **Showing messy intermediate results** | Shows real work, not theater |
| **Asking questions, not just presenting** | Shows you care about getting it right |
| **Documenting everything** | Shows you respect their investment in this time |

### What Destroys Trust

| Behavior | Why it hurts |
|----------|-------------|
| Pretending a broken demo works | Customers always notice — and they'll wonder what else you're hiding |
| Ignoring the customer's input after ideation | Signals that the brainstorming was performative |
| Over-promising in the Ask | Sets expectations you can't meet, souring the follow-up |
| Leaving without clear next steps | Customer feels like they wasted two days |

> **Tip:** The best hackathons end with the customer asking *"When can we start the pilot?"* — not because you pitched hard, but because you earned it.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [BRIEF.md](../../BRIEF.md) | Capture the customer's context before Day 1 |
| [Use Case Canvas](../../templates/use-case-canvas.md) | Frame use cases around customer pain |
| [Demo Crafting](../guides/demo-crafting.md) | Tell the customer's story in the demo |
| [HANDOFF.md](../../HANDOFF.md) | Post-hackathon handoff document |
| [Scope Management](scope-management.md) | Cut scope in a way that keeps trust |
| [Running Ideation](../guides/running-ideation.md) | Let the customer drive use case selection |
