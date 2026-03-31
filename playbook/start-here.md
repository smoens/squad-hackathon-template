← [Playbook](README.md) | ← [README](../README.md)

# Start Here

You just stamped a new repo from the hackathon template. Welcome to the squad. This guide gets you from "blank repo" to "ready for Day 1" — and then walks you through the hackathon itself.

You've got this.

---

## What You Just Stamped

In 30 seconds: this repo is a **complete hackathon-in-a-box**. It contains:

| Folder | What's inside |
|--------|---------------|
| `BRIEF.md` | The single source of truth for your customer engagement |
| `.hackathon/` | Config, checklists, and operational scaffolding |
| `accelerators/` | Pre-built code packs for common use cases |
| `playbook/` | Facilitation guides, canvases, scorecards, scripts — fill-in-the-blank tools |
| `use-cases/` | Where your hackathon use cases live |
| `playbook/` | Facilitation guides (you're reading one now) |
| `build/` | Architecture decisions, data, notebooks, scripts |
| `.github/prompts/` | AI-powered prompts — Copilot does the heavy lifting |

Every file has a purpose. Nothing is filler.

---

## Quick Start — 10 Minutes

The minimum viable setup to be hackathon-ready.

### 1. Tell Jared your company name (2 min)

Say: *"Jared, let's set up a hackathon for [Company] — they're in [industry]"*

Jared will research the customer, fill `BRIEF.md`, generate "What if..." conversation starters, and suggest accelerator packs. Review what he produces, verify the ⚠️ assumptions, and you're halfway there.

> **Manual alternative:** Open [`BRIEF.md`](../BRIEF.md) and fill the 5 key fields yourself (customer, industry, date, format, business context).

### 2. Review config.json (2 min)

Open [`.hackathon/config.json`](../.hackathon/config.json) and verify `accelerator_packs` and `azure_resources` are set.

### 3. Kick off ideation (6 min)

Say: *"Jared, let's brainstorm — what could we build for them?"*

Jared will facilitate a conversation: brainstorming use cases, scoring feasibility, and helping you pick 2-3 to build. He'll ask you questions along the way — it's a conversation, not a report.

**You're now ready for ideation.** Everything else is better preparation, not blockers.

---

## Full Setup — 45 Minutes

For facilitators who want to walk in fully prepared.

### 1. Complete BRIEF.md (15 min)

Fill every `[FILL]` field — especially:

| Section | Why it matters | Common mistake |
|---------|---------------|----------------|
| **Business Context** | Frames every conversation on Day 1 | Too vague — "they want AI" isn't context |
| **Goals** | Defines what success looks like | Too many — aim for 2-3, not 8 |
| **Attendees** | Drives squad pairing and room dynamics | Forgetting customer decision-makers |
| **Technical Landscape** | Prevents Day 1 data access surprises | Assuming you'll figure it out live |

Send the Brief to the customer sponsor for review. Alignment here prevents Day 1 surprises.

### 2. Select accelerator packs (5 min)

Browse [`accelerators/`](../accelerators/README.md) for pre-built patterns that match likely use cases. Add selections to `.hackathon/config.json` → `accelerator_packs[]`.

No matching pack? That's fine — the template works without them.

### 3. Prepare 5 seed use cases (10 min)

Write each as: *"What if [persona] could [outcome] by [approach]?"*

Base them on customer pain points from the Brief. If you can't articulate their pain, you're not ready for ideation.

### 4. Run the formation checklist (10 min)

Open the [formation checklist](checklists.md) and work through every item. The big ones:

- [ ] **Azure environments provisioned and tested** ← longest lead time, do this FIRST
- [ ] Brief completed and customer-reviewed
- [ ] Sample / synthetic datasets prepared
- [ ] Squad briefed — every member knows their role

### 5. Set the agenda (5 min)

| Format | Ideation | Build | Demo Prep | Demo |
|--------|----------|-------|-----------|------|
| **1-day** | 1.5 hrs | 3.5 hrs | 1 hr | 1 hr |
| **2-day** | 2.5 hrs | 7 hrs | 1.5 hrs | 1 hr |

Print the agenda. Even in a digital-first world, a physical time-box schedule on the wall keeps everyone honest.

---

## Your First Hackathon — Day by Day

### Day 0: Final Prep

- [ ] Visit the room (or test virtual setup) — projector, WiFi, whiteboard markers
- [ ] Data loaded in notebooks (test one cell)
- [ ] Squad arrives 30 min early on Day 1
- [ ] Everyone has read BRIEF.md

### Day 1 Morning: Kickoff + Ideation

| Time | What | Your role |
|------|------|-----------|
| 9:00–9:30 | **Kickoff** — welcome, intros, brief recap, ask sponsor: *"What makes this successful for you?"* | MC |
| 9:30–11:00 | **Ideation** — silent write → round-robin → cluster → vote (see [Ideation Cheat Sheet](ideation-cheat-sheet.md)) | Facilitator |
| 11:00–12:00 | **Feasibility scoring** — score top 4-6 use cases, pick 1-3 to build | Timekeeper |

> The customer should talk more than you in ideation. Your job is to *extract*, not to *present*.

### Day 1 Afternoon: Build

| Time | What | Watch for |
|------|------|-----------|
| 1:00–3:00 | **Build start** — set up notebooks, load accelerators, sketch data pipeline | |
| 3:00 | **25% checkpoint** — data flowing? Core logic working? If not: pivot or cut | Kill struggling use cases early |
| 3:00–5:00 | **Build continues** | Scope creep ("What if we also...") — say no |
| 5:00–5:30 | **Squad debrief** — blockers, plan for Day 2 | |

### Day 2 Morning: Build (Final Push)

| Time | What | Watch for |
|------|------|-----------|
| 9:00–12:00 | **Build** — final implementation | |
| ~10:00 | **75% checkpoint** — is this demo-able? Polish or cut. No new features. | This is the hard call |

### Day 2 Afternoon: Demo + Close

| Time | What | Your role |
|------|------|-----------|
| 1:00–2:30 | **Demo prep** — write scripts, capture backup screenshots, rehearse (see [Demo Crafting](demo-crafting.md)) | Coach |
| 2:30–3:30 | **Live demo** — 5 min per use case, hard stop. You hold the clock. | MC + Timekeeper |
| 3:30–4:00 | **Retro + close** — what worked, what would we change, thank the customer | Facilitator |

### Post-Hackathon (T+1 to T+7)

| Task | Owner | Deadline |
|------|-------|----------|
| Write `HANDOFF.md` | Builder + Architect | T+1 |
| Finalize `RETRO.md` | Facilitator | T+2 |
| Clean code + commit | Builder | T+3 |
| Extract knowledge → accelerator packs | Data Wrangler | T+5 |
| Follow-up proposal to customer | Facilitator | T+5 |

See [Checklists](checklists.md) for the complete wind-down and knowledge extraction lists.

---

## Common Questions

**Q: What if we only have 1 day?**
Compress ideation to 60 min, scoring to 45 min. Build one or two use cases only. Skip the squad debrief — go straight to build.

**Q: What if the customer changes scope on Day 1?**
The Brief locked the scope. New ideas go to the parking lot. Be kind but firm.

**Q: What if a use case fails during build?**
Cut it at the 75% checkpoint. Redirect the team to strengthen remaining demos. One great demo beats two broken ones.

**Q: What if we don't have real customer data?**
Use synthetic data. 100 rows that work beats 1M rows you can't access. See the [Data Simulation Skill](../.squad/skills/data-simulation/SKILL.md).

**Q: Can I skip the formation checklist?**
You can, but you'll pay for it on Day 1 morning. Azure provisioning alone can burn 2 hours if you didn't do it ahead.

**Q: What's the most common first-timer mistake?**
Over-preparing solutions, under-preparing the Brief. The hackathon should *discover* solutions, not confirm pre-built ones.

---

## What's Next?

| Guide | When to read it |
|-------|----------------|
| [Ideation Cheat Sheet](ideation-cheat-sheet.md) | Before Day 1 ideation |
| [Demo Crafting](demo-crafting.md) | Before Day 2 demo prep |
| [Checklists](checklists.md) | During formation and wind-down |
| [Atmosphere & Energy](atmosphere-and-energy.md) | If you want to run a *great* hackathon, not just a good one |
| [What-If Cards](what-if-cards.md) | Grab a deck before ideation |
