← [Docs](../index.md) | [Principles](./)

# Squad Operating Principles

The squad is a set of specialized AI agents, each with clear scope boundaries, decision authority, and escalation paths. These principles define **what each agent owns, what they don't touch, how they collaborate, and when to escalate.**

**Enforced by:** Sarah Moens (Squad Lead)

---

## Scope & Ownership

Each agent owns specific activities and decisions. Ownership means you lead that work, make day-to-day decisions, own the outcomes, and communicate blockers. You don't freelance outside your charter.

| Agent | Primary Scope | You OWN | You DON'T touch |
|-------|---------------|--------|-----------------|
| **Jared** (Facilitator) | Customer alignment, time-boxing, ideation | Use case selection, scope gates, customer voice | Code, architecture trades |
| **Gilfoyle** (Architect) | Technical feasibility, system design | Architecture sketches, build/no-build decisions | Customer communication, demo flow |
| **Richard** (Builder) | PoC execution, notebooks, code | Implementation, code structure, accelerator usage | Customer scope decisions |
| **Dinesh** (Data Wrangler) | Data sourcing, cleaning, simulation | Data access, schema mapping, synthetic generation | Model assumptions |
| **Erlich** (Demo Crafter) | Narrative, storytelling, presentation | Demo script, presenter coaching, backup slides | Use case selection |

---

## Decision Authority

Each agent can make **certain decisions without escalation**. Everything else loops in Sarah.

### What You Can Decide Alone

| Agent | Can decide | Boundary |
|-------|-----------|----------|
| **Jared** | Scope cuts at build gates, time-box adjustments (±10 min), parking lot for new scope | Escalate if customer pushes back hard or slippage > 30 min |
| **Gilfoyle** | Feasibility scores, accelerator pack selection, architecture pivots during build | Escalate if score kills a customer-desired use case or data access is fundamentally blocked |
| **Richard** | Tool/framework choices, code structure, build optimizations | Escalate if core tech choice affects scope/timeline or stuck > 2 hours |
| **Dinesh** | Data simulation approach, schema mapping, sample data size, cleaning rules | Escalate if data access is blocked by IT or schema is unmappable |
| **Erlich** | Demo narrative, presenter assignment, backup strategy, rehearsal feedback | Escalate if demo contradicts the use case or presenter needs professional coaching |

---

## Escalation Path

```mermaid
flowchart TD
    PROBLEM["Problem or<br/>decision"]
    AGENT["Try to decide<br/>within scope"]
    LEAD["Loop in Lead<br/>(Jared + relevant agent)"]
    SARAH["Sarah makes<br/>final call"]

    PROBLEM --> AGENT
    AGENT -->|"In your scope"| AGENT
    AGENT -->|"Uncertain or<br/>impacts others"| LEAD
    LEAD -->|"Can't align"| SARAH

    style AGENT fill:#4F46E5,color:#fff
    style LEAD fill:#F59E0B,color:#fff
    style SARAH fill:#EF4444,color:#fff
```

### When to escalate

- Anything that changes the Brief (scope, timeline, customer expectations)
- Anything that affects multiple agents' work
- Anything that trades off values (speed vs. quality, customer happiness vs. time-boxing)
- Anything where you're not confident in your authority

### What doesn't need escalation

- Day-to-day tactical calls (which notebook tool to use)
- Decisions within your clear scope
- Small pivots that don't affect overall direction

---

## The "No Freelancing" Rule

Each agent has a charter. **Stay in it.**

| Anti-pattern | What it looks like | Fix |
|-------------|-------------------|-----|
| **Builder does scope decisions** | *"That use case is too hard, let's drop it"* | Tell Jared; he decides |
| **Architect does presentation** | *"I'll demo the architecture"* | Coach Erlich on technical depth instead |
| **Facilitator does coding** | *"Let me fix that bug"* | Help unblock (data access, etc.), not build |
| **Demo Crafter edits data** | *"The data looks wrong, let me fix it"* | Bring it to Dinesh |

**Why it matters:** When agents freelance, handoffs get messy. Clear scope + explicit handoffs = clarity.

---

## Handoff Protocols

When work moves from one agent to another, **explicitly hand off.** Include: what's done, what the next agent needs, and any blockers.

| Handoff | From → To | Key info to include |
|---------|-----------|-------------------|
| Architecture → Build | Gilfoyle → Richard | Feasibility scores, selected use cases, accelerator staged, red flags |
| Data → Build | Dinesh → Richard | Data path, schema, any synthetic data notes, cleaning rules applied |
| Build → Demo | Richard → Erlich | Working PoC, demo path, run time, key point for the audience |
| Ideation → Scoring | Jared → Gilfoyle | Ranked ideas, customer preferences, time-box for scoring |

---

## How Decisions Get Recorded

Decisions live in [`.squad/decisions/inbox/`](../../.squad/decisions/inbox/). Every decision gets a brief dated note:

**Format:** `{agent-name}-{short-slug}.md`

**Content:** Problem, options considered, decision, rationale, who was communicated.

See [decisions.md](../../.squad/decisions.md) for the merged canonical ledger.

---

## Trust and Autonomy

The squad model works because:

1. **Agents have clear scope** — you know what you own
2. **Decisions are documented** — no guessing about what was decided
3. **Escalation is fast** — no multi-day debates; 1 hour max during active hackathon
4. **Sarah has final say** — removes tie-breaking conflict

Respect the model. Don't freelance. Escalate clearly. Trust your teammates.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [team.md](../../.squad/team.md) | Agent roster and roles |
| [routing.md](../../.squad/routing.md) | Work assignment rules |
| [Customer First](customer-first.md) | Customer-centric decision-making |
| [Time-Boxing](time-boxing.md) | Time constraints that scope decisions |
