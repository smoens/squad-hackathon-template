# Hackathon Facilitation

Knowledge for running business hackathons — phase transitions, time-boxing, scope management, and delivery patterns.

## When to Use This Skill

- Facilitating any hackathon phase transition
- Time-boxing decisions during build or ideation
- Scope gate evaluations (go / scope-cut / redirect)
- Ideation facilitation patterns
- Pivot vs. push-through decisions
- Demo prep timing and sequencing
- Post-hackathon knowledge handoff

---

## Phase Transition Rules

### Formation → Ideation

**Gate criteria (ALL must be true):**
- `BRIEF.md` is filled — no `[FILL]` markers in Engagement Details or Business Context
- `.hackathon/config.json` has customer, industry, dates populated
- At least 3 use case hypotheses documented in the Brief
- Azure environment provisioned and tested (if applicable)
- Sample data staged or simulators confirmed
- Squad briefed on customer context

**If not ready:** Do NOT start ideation. Fix the blocker. A 30-minute delay in formation saves 2 hours of confused ideation.

### Ideation → Build

**Gate criteria (ALL must be true):**
- All candidate use cases scored with feasibility scorecard
- 2-3 use cases selected (never more than 3 for a 2-day, never more than 2 for a 1-day)
- Each selected use case has a defined "demo-able slice"
- Architecture direction confirmed by Gilfoyle (even if rough)
- Data readiness confirmed by Dinesh (real data or simulator plan)
- No selected use case scored 🔴 Redirect

**If a tie:** Pick the use case with the lowest feasibility score AND a clear demo moment. Customer energy is the tiebreaker.

### Build → Demo

**Gate criteria (at least one must be true per use case):**
- PoC is demo-ready: runs end-to-end on sample data
- PoC is partially working: can demo the key insight even if edges are rough
- PoC failed: pivot to static walkthrough with screenshots + architecture diagram

**Trigger timing:**
- 2-day hackathon: demo prep starts morning of Day 2 (not end of Day 2)
- 1-day hackathon: demo prep starts after lunch

**Hard rule:** Demo prep NEVER starts less than 2 hours before demo time. If it does, you've lost.

### Demo → Wind-Down

**Automatic transition** — no gate. After demos are presented:
1. Capture audience reactions and questions immediately
2. Start `HANDOFF.md` while memory is fresh
3. `playbook/checklists.md` becomes the driver

### Wind-Down → Knowledge Capture

**Trigger:** Within 24 hours of hackathon end.
**Deadline:** 5 business days (`playbook/checklists.md` — Knowledge Extraction section).
**Critical:** If knowledge capture doesn't happen in 5 days, it won't happen at all.

---

## Time-Boxing Rules

### General Principles

1. **Time-boxing is law.** When the facilitator calls time, wrap current activity and move. No extensions.
2. **5-minute warning** before every time-box expires.
3. **Parking lot** for ideas that don't fit the current time-box — capture, don't debate.
4. **Stand-ups are standing.** 10 minutes max. Three questions: What did you do? What's next? What's blocked?

### Standard Time-Boxes

| Activity | Duration | Phase |
|----------|----------|-------|
| Ideation brainstorm (per round) | 20-30 min | Ideation |
| Use case canvas fill | 10 min per canvas | Ideation |
| Feasibility scoring (all use cases) | 30-45 min | Ideation |
| Priority vote and selection | 15 min | Ideation |
| Architecture sketch (per use case) | 20 min | Build |
| Build sprint | 90-120 min blocks | Build |
| Data debugging / unblocking | 30 min then escalate | Build |
| Demo script writing | 30 min per use case | Demo |
| Dry-run rehearsal | 15 min per use case | Demo |
| Retrospective | 30 min | Wind-Down |

### Time-Box Escalation

If an activity threatens to overrun:
1. Facilitator gives 5-minute warning
2. At expiry: "We have 3 options — extend by 10 min and cut something else, park it, or decide now with available information."
3. The default is always "decide now." Extensions require explicitly cutting something else.

---

## Scope Gate Decisions

### When to Scope-Cut

Trigger: A use case is taking longer than expected during Build phase.

**Decision framework:**
1. Can we cut a feature and still have a demo moment? → **Scope-cut.** Define the reduced slice.
2. Is the core insight still demonstrable? → **Scope-cut to insight-only demo** (show the data flow, not the full output).
3. Is the blocker data-related? → **Simulator.** Dinesh builds a synthetic version. Time-box to 1 hour.
4. Is the architecture fundamentally wrong? → **Pivot or redirect.** Gilfoyle proposes an alternative or we kill the use case.

### When to Kill a Use Case

Kill immediately if:
- Data is permanently blocked (no workaround, no simulator)
- The core insight can't be demonstrated in remaining time
- The customer has explicitly deprioritized it mid-hackathon
- Architecture requires a service/tool we can't provision

**Killing is not failure.** Spending 3 hours on a dead use case instead of 30 minutes recognizing it — that's failure.

---

## Ideation Facilitation Patterns

### Structured Brainstorm (recommended for most hackathons)

1. **Silent ideation (5 min):** Everyone writes use case ideas on sticky notes / doc. No discussion.
2. **Round-robin share (10 min):** Each person presents their ideas. No critiquing yet.
3. **Affinity grouping (5 min):** Cluster similar ideas. Name the clusters.
4. **Dot voting (5 min):** Each person gets 3 votes. Vote for most promising clusters.
5. **Canvas fill (10 min/canvas):** Top 5-6 ideas get a quick canvas.
6. **Feasibility scoring (30 min):** Gilfoyle scores all canvases.
7. **Selection (15 min):** Pick 2-3 based on score + customer energy.

### Customer-Led Pattern (when customer has strong opinions)

1. Customer presents their top priorities (15 min)
2. Squad asks clarifying questions (10 min)
3. Quick feasibility gut-check by Gilfoyle (10 min)
4. Select top 2-3 and validate with canvas + scorecard (30 min)

### Diverge-Converge Pattern (when the problem space is broad)

1. **Diverge:** Brainstorm WITHOUT constraints (20 min). "What if you could do anything?"
2. **Constraint filter:** Apply hackathon constraints — time, data, tech (10 min). Eliminate non-starters.
3. **Converge:** Score and select from remaining candidates (30 min).

---

## Pivot vs. Push-Through Decision

During Build phase, when things aren't working:

| Signal | Decision | Action |
|--------|----------|--------|
| Data issue, workaround exists | Push through | Dinesh builds simulator, team continues |
| Architecture doesn't scale but works for demo | Push through | Document in ADC, proceed with PoC |
| Core approach is fundamentally flawed | Pivot | Gilfoyle proposes alternative architecture |
| Feature is nice-to-have but time is short | Scope-cut | Cut to demo-able slice |
| Customer shows low enthusiasm for this use case | Redirect | Switch effort to higher-energy use case |
| Everything works but demo isn't compelling | Demo pivot | Erlich reframes the narrative, not the tech |

**Rule of thumb:** If Richard has been stuck for 30+ minutes with no progress, escalate to Gilfoyle for an architecture decision.

---

## Demo Prep Timing

### 2-Day Hackathon

| Time | Activity |
|------|----------|
| Day 1 End | Erlich briefed on PoC direction for each use case |
| Day 2 Morning | Demo scripts drafted (even for incomplete PoCs) |
| Day 2 Midday | Code freeze for demo path. Bug fixes only. |
| Day 2 -3 hours | Dry-run #1 with team |
| Day 2 -1.5 hours | Final fixes from dry-run |
| Day 2 -45 min | Dry-run #2 (final) |
| Day 2 -15 min | Environment check, backup screenshots confirmed |

### 1-Day Hackathon

| Time | Activity |
|------|----------|
| After lunch | Erlich starts demo scripts |
| -2 hours | Code freeze. Demo path only. |
| -1 hour | Single dry-run |
| -15 min | Environment check |

---

## Handoff Structure

### During Hackathon

- Every completed PoC → update `HANDOFF.md` immediately (don't wait for wind-down)
- Architecture decisions → `build/decisions/` as ADCs
- Scribe captures continuously

### Post-Hackathon

1. `HANDOFF.md` — Executive summary, use case details, architecture, next steps. **This goes to the customer.**
2. `RETRO.md` — What worked, what didn't, what to improve.
3. `playbook/checklists.md` — Tactical wrap-up (code committed, resources dispositioned) and strategic knowledge capture.
