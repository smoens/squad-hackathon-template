← [Docs](../index.md) | [Guides](./)

# Running Your First Hackathon

You've stamped the template. You've got a customer and a brief. Now what? This guide walks you end-to-end from Day 0 through handoff — every phase, every time-box, every decision point.

**Who this is for:** First-time facilitators, or anyone running their first engagement with the squad.

**Assumes:** You've read [Getting Started](getting-started.md) and have [BRIEF.md](../../BRIEF.md) completed.

---

## The 2-Day Schedule (Default Format)

```
Day 1                           Day 2
────────────────────────────────────────────
9:00–9:30   Kickoff             9:00–12:00  Build (final push)
9:30–11:00  Ideation            12:00–1:00  Lunch
11:00–12:00 Feasibility         1:00–2:30   Demo prep + rehearsal
12:00–1:00  Lunch               2:30–3:30   Live demo + Q&A
1:00–5:00   Build               3:30–4:00   Retro seeds
5:00–5:30   Squad debrief       → Post-hackathon tasks
```

---

## Phase-by-Phase Walkthrough

### Phase 1: Formation (T-7 to T-1)

| Task | Owner | Deadline |
|------|-------|----------|
| Fill [BRIEF.md](../../BRIEF.md) completely | Facilitator + Sponsor | T-7 |
| Select [accelerator packs](../../accelerators/README.md) | Architect | T-7 |
| Configure [config.json](../../.hackathon/config.json) | Facilitator | T-7 |
| Secure data access | Data Wrangler | T-5 |
| Provision infrastructure | Architect | T-5 |
| Prepare seed hypotheses (3–5 use case starters) | Architect + Facilitator | T-2 |
| [Formation checklist](../../.hackathon/checklist-formation.md) | Facilitator | T-1 |

**Deliverable:** Completed BRIEF.md + configured environments ready on Day 1 morning.

---

### Phase 2: Ideation (Day 1, 9:30–11:00)

**Time-box:** 90 minutes (can shrink to 60 in 1-day format)

1. Recap customer brief (5 min)
2. Silent write: each person sketches 2–3 use cases (8 min) — no talking
3. Round-robin share (10 min) — 30s pitch per idea
4. Cluster similar ideas (5 min)
5. Discuss top 4–6 (20 min) — customer input, refinement
6. Dot voting (5 min) — 3 votes per person, silent

See [Running Ideation](running-ideation.md) for detailed facilitation techniques.

**Deliverable:** Ranked list of 4–6 use case candidates ready for scoring.

---

### Phase 3: Feasibility Scoring (Day 1, 11:00–12:00)

**Time-box:** 60 minutes

Score each use case on the [Feasibility Scorecard](../../templates/feasibility-scorecard.md) — 8–10 minutes per use case.

| Score Range | Call | Action |
|:-----------:|------|--------|
| 6–8 | 🟢 Go | Build the full demo-able slice |
| 9–12 | 🟡 Go thin | Build core only; cut scope |
| 13–15 | 🟠 Stretch | Only if customer insists |
| 16–18 | 🔴 Defer | Redirect to another use case |

See [Use Case Prioritization](../concepts/use-case-prioritization.md) for the full framework.

**Deliverable:** Scored use cases + team assignments.

---

### Phase 4: Build (Day 1 afternoon + Day 2 morning)

**Time-box:** ~8 hours total

| Checkpoint | When | Who | Decision |
|-----------|------|-----|----------|
| **Start** | After scoring | Builder + Data Wrangler | Set up notebooks, load accelerator, sketch data pipeline |
| **25%** | T+2 hours | Architect + Builder | Data flowing? Core logic working? If not, pivot or cut |
| **75%** | T+6 hours | Facilitator + Architect | Is this demo-able? Polish or cut. No new features |
| **End** | T+8 hours | Builder | Code committed, data documented, ready for demo prep |

**Common pitfalls:**

| Pitfall | Warning sign | Fix |
|---------|--------------|-----|
| Scope creep | *"What if we also..."* at 2-hour mark | Facilitator kills the suggestion. Demo path only. |
| Data delays | Waiting for perfect data at 3-hour mark | Use sample. 100 rows that work beats 1M you can't access. |
| Unfamiliar tools | Struggling with SDK at 4-hour mark | Switch to familiar tools. Speed > elegance. |

**Deliverable:** Working PoC — code, data transformations, and one clear demo path.

---

### Phase 5: Demo Prep (Day 2, 1:00–2:30)

**Time-box:** 90 minutes

1. Draft [demo script](../../templates/demo-script-template.md) (30 min)
2. Assign presenters — max 2 per use case (10 min)
3. Capture backup screenshots (15 min)
4. Full rehearsal — timed (45 min)

See [Demo Crafting](demo-crafting.md) for narrative techniques.

**Deliverable:** Polished demo script + backup screenshots + rehearsed presenters.

---

### Phase 6: Live Demo (Day 2, 2:30–3:30)

**Time-box:** 5 minutes per use case (hard stop)

- One use case at a time: 5-min demo + 2-min Q&A
- If demo fails: switch to backup screenshots, keep storytelling going
- Facilitator holds the clock — visible to presenters

---

### Phase 7: Wind-Down (Day 2, 3:30–4:00)

1. Brief retro (15 min) — *"What worked? What would we change?"*
2. Thank the customer + explain next steps (10 min)
3. Capture feedback for [RETRO.md](../../RETRO.md) (5 min)

---

## Post-Hackathon Tasks (T+1 to T+7)

| Task | Owner | Deadline |
|------|-------|----------|
| Write [HANDOFF.md](../../HANDOFF.md) | Builder + Architect | T+1 |
| Finalize [RETRO.md](../../RETRO.md) | Facilitator | T+2 |
| Clean code + commit | Builder | T+3 |
| Extract knowledge → accelerator packs | Data Wrangler | T+7 |

---

## End-to-End Checklist

### Pre-Hackathon

- [ ] BRIEF.md complete and customer-reviewed
- [ ] Data access confirmed and tested
- [ ] Infrastructure provisioned
- [ ] Accelerator packs selected and staged
- [ ] Formation checklist passed

### Day 1

- [ ] Kickoff delivered
- [ ] Ideation facilitated
- [ ] Use cases scored
- [ ] 1–3 use cases selected and assigned
- [ ] Build started; 25% checkpoint completed

### Day 2

- [ ] Build 75% checkpoint completed
- [ ] Demo scripted and rehearsed
- [ ] Backup screenshots captured
- [ ] Live demo delivered
- [ ] Retro session completed

### Post-Hackathon

- [ ] HANDOFF.md written
- [ ] RETRO.md finalized
- [ ] Code cleaned and committed
- [ ] Knowledge extracted
- [ ] Follow-up proposal sent to customer (T+5)

---

## Common Questions

**Q: What if we only have 1 day?**
Compress ideation to 60 min, scoring to 45 min. Build one or two use cases only.

**Q: What if the customer adds a use case on Day 1 afternoon?**
Facilitator says no. The Brief locked the scope. New ideas go to the parking lot.

**Q: What if a use case fails during build?**
Cut it at the 75% checkpoint. Redirect the team to strengthen remaining demos.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Getting Started](getting-started.md) | Template setup and prerequisites |
| [Running Ideation](running-ideation.md) | Deep dive on facilitation techniques |
| [Demo Crafting](demo-crafting.md) | Deep dive on demo narrative |
| [Time-Boxing](../principles/time-boxing.md) | Philosophy behind the time constraints |
| [Scope Management](../principles/scope-management.md) | How to cut and defend scope |
