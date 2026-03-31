← [Playbook](README.md) | ← [README](../README.md)

# Checklists

Three phases, one file. Print this. Tape it to the wall. Check items off with a marker.

---

## Pre-Hackathon (Formation) — 1-2 Weeks Before

*Facilitator owns this list. Start with the long-lead items.*

### 🔴 Do FIRST — Longest Lead Time

- [ ] **Azure environments provisioned and tested** — subscriptions, resource groups, service principals, Fabric workspaces. This takes days, not hours.
- [ ] **Data access confirmed and tested** — schema obtained, credentials tested by Data Wrangler, sample rows flowing. If restricted: synthetic data plan in place.
- [ ] **Infrastructure verified** — notebooks run, accelerator packs staged, code executes end-to-end

### Stakeholder & Logistics

- [ ] Customer attendees confirmed with sponsor:
  - [ ] Technical decision-maker (architect, platform lead)
  - [ ] Business decision-maker (director, VP, budget owner)
  - [ ] Domain expert (someone who does the job daily)
  - [ ] IT / Security (if data access requires approval)
- [ ] Attendee expectations document sent
- [ ] Preparation email sent: date, time, location/link, what to bring
- [ ] 30-min pre-hackathon call scheduled with sponsor

### Content & Configuration

- [ ] `BRIEF.md` completed and customer-reviewed
- [ ] `.hackathon/config.json` configured (customer, industry, dates, packs)
- [ ] Accelerator packs selected and loaded
- [ ] 3-5 use case hypotheses documented (seed ideas for ideation)
- [ ] Agenda and time-boxing plan confirmed

### Venue / Virtual Setup

- [ ] (Physical) Room booked, climate-controlled, projector working, WiFi tested for 10+ laptops
- [ ] (Physical) Whiteboards + markers + sticky notes + printed canvases and scorecards
- [ ] (Virtual) Meeting link shared, breakout rooms configured, Miro board pre-loaded
- [ ] (Virtual) Recording permission plan: *"We'll record for retro only"*
- [ ] Timer visible to all participants (any format)

### Team Readiness

- [ ] Squad briefed — every member knows their role
- [ ] Sample / synthetic datasets prepared
- [ ] Formation checklist passed (this list ✓)

---

## Post-Hackathon (Wind-Down) — Last Day + 1 Week

*Complete within 24 hours of hackathon end. Facilitator owns this list.*

### Immediate — End of Day 2

- [ ] Thank customer face-to-face
- [ ] Explain next steps: *"We'll send a handoff document by tomorrow"*
- [ ] Capture retro feedback for `RETRO.md` — 15-min session: *"What worked? What would we change?"*
- [ ] Customer satisfaction signal captured (verbal or written)

### T+1 to T+2

- [ ] All PoC code committed and documented
- [ ] Architecture diagrams finalized per use case
- [ ] `HANDOFF.md` completed:
  - What we built (per use case)
  - How to run the code
  - What we learned
  - Three options for next phase
  - Estimated effort + cost per option
- [ ] Follow-up email sent to customer sponsor

### T+2 to T+5

- [ ] `RETRO.md` finalized
- [ ] Clean code committed (no dead code, secrets, or temp files)
- [ ] Azure resources dispositioned (keep / archive / destroy)
- [ ] Follow-up actions captured with owners and deadlines
- [ ] Follow-up proposal sent to customer (T+5)

---

## Knowledge Extraction — 1 Week After

*Complete within 5 business days. Squad collectively owns this.*

- [ ] Retrospective completed and documented (`RETRO.md`)
- [ ] Architecture patterns identified for HQ promotion
- [ ] Reusable code / notebooks flagged for template library
- [ ] Customer insight brief written (sanitized — no customer data)
- [ ] Engagement record submitted to HQ cockpit
- [ ] Template improvements identified and PR'd to the template repo
- [ ] Knowledge extracted → accelerator packs updated
- [ ] Engagement formally closed

---

## Quick Reference: What Goes Wrong

| Risk | When it hits | Prevention |
|------|-------------|-----------|
| Azure provisioning takes 2 days | Day 1 morning | Do it FIRST — 2 weeks out |
| Data access blocked | Day 1 build phase | Have synthetic backup ready |
| Ideation runs 30 min over | Day 1 lunch | Facilitator hard-stops at time box |
| Demo crashes live | Day 2 demo | Backup screenshots captured in wind-down prep |
| Knowledge evaporates | Week 2 | 5-day extraction window is a hard deadline |
