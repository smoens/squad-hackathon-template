← [Docs](../index.md) | [Guides](./)

# Customer Engagement Checklist

Running a hackathon with a customer involves logistics — room setup, data access, recording consent, timing discipline. This checklist covers **pre-flight, day-of, and post-hackathon** to keep customer relationships smooth and professional.

**Who this is for:** Facilitators and anyone coordinating customer-facing logistics.

---

## Pre-Flight (2+ Weeks Before)

### Stakeholder Alignment

- [ ] Confirmed attendees with customer sponsor (by role):
  - [ ] Technical decision-maker (architect, platform lead)
  - [ ] Business decision-maker (director, VP, budget owner)
  - [ ] Domain expert (someone who does the job daily)
  - [ ] IT / Security (if data access requires approval)
- [ ] Sent attendee expectations document
- [ ] Confirmed attendee count (impacts room size and squad pairing)

### Technical Prerequisites

- [ ] **Data access confirmed:**
  - [ ] Data type identified (CSV, database, cloud storage, real-time feed)
  - [ ] Schema obtained (column names, types, sample rows)
  - [ ] Access credentials tested by Data Wrangler
  - [ ] Privacy/compliance restrictions documented
  - [ ] If restricted: synthetic data plan in place (see [Data Simulation Playbook](data-simulation-playbook.md))
- [ ] **Infrastructure provisioned:**
  - [ ] Azure subscriptions / Fabric workspaces created
  - [ ] Service principals / credentials configured
  - [ ] Notebook environment verified (code runs)
  - [ ] Accelerator packs staged and tested
- [ ] **Network / connectivity:**
  - [ ] (Physical) venue WiFi tested for 10+ laptops
  - [ ] (Virtual) backup plan for connection issues

### Customer Preparation

- [ ] Sent [BRIEF.md](../../BRIEF.md) for review and sign-off
- [ ] Provided 3–5 use case hypotheses (seed ideas for ideation)
- [ ] Sent preparation email: date, time, location/link, what to bring
- [ ] Scheduled 30-min pre-hackathon call with sponsor

---

## Day-Of

### Morning Setup (1–2 hours before kickoff)

**Physical:**
- [ ] Room unlocked and climate-controlled
- [ ] Projector / screen working
- [ ] WiFi verified
- [ ] Whiteboards + markers + sticky notes visible
- [ ] Timer visible to all participants
- [ ] Printed [Use Case Canvas](../../templates/use-case-canvas.md) and [Feasibility Scorecard](../../templates/feasibility-scorecard.md) as backup

**Virtual:**
- [ ] Meeting link shared
- [ ] Recording permission requested: *"We'll record for retro only"*
- [ ] Breakout rooms configured (if >6 people)
- [ ] Backup slides ready

**Data & Infrastructure:**
- [ ] Data files loaded in notebooks (test one cell)
- [ ] Accelerator packs loaded and notebooks open

**Team:**
- [ ] Squad arrived 30 min early
- [ ] Everyone has reviewed BRIEF.md
- [ ] Time-keeper assigned

### Kickoff (5 minutes)

- [ ] Welcome and thank you
- [ ] Introduce roles
- [ ] Recap BRIEF.md context
- [ ] Walk through agenda
- [ ] Set expectations: *"This is a PoC, not a product"*
- [ ] Ask sponsor: *"What would make this hackathon successful for you?"*

### During the Day

- [ ] Ideation: timer visible, silent write strictly 8 min
- [ ] Build 25% checkpoint: data flowing? Core logic working?
- [ ] Build 75% checkpoint: demo-able? If not, cut scope
- [ ] Lunch break announced 15 min before

---

## Remote Considerations

### Recording & Consent

- [ ] State at kickoff: *"We'll record for our team's retro. Delete after 1 week. Everyone OK?"*
- [ ] Stop recording during sensitive discussions if needed

### Virtual Engagement

- [ ] Facilitator calls on each person by name in round-robin
- [ ] Shared Miro/FigJam board (not just talking)
- [ ] Customer sponsor stays in main room

### Demo Delivery (Virtual)

- [ ] Presenter screen-shares (not just talking)
- [ ] Backup screenshots ready
- [ ] Repeat questions aloud for remote audience

---

## Post-Hackathon (Within 48 Hours)

### Immediate (End of Day 2)

- [ ] Thank customer face-to-face
- [ ] Explain next steps: *"We'll send a handoff document by tomorrow"*

### Handoff (T+1 to T+2)

- [ ] Write [HANDOFF.md](../../HANDOFF.md):
  - What we built (per use case)
  - How to run the code
  - What we learned
  - Three options for next phase
  - Estimated effort + cost per option
- [ ] Send follow-up email to customer sponsor
- [ ] Include knowledge extraction checklist for their team

### Internal (T+1 to T+7)

- [ ] Debrief: what worked, what didn't
- [ ] Finalize [RETRO.md](../../RETRO.md)
- [ ] Extract patterns → accelerator packs
- [ ] Follow-up proposal sent (T+5)

---

## Common Day-Of Issues

| Issue | Fix |
|-------|-----|
| Data takes 2 hours to access | Have synthetic backup ready (pre-flight item) |
| Ideation runs long | Facilitator enforces 90-min cutoff; park overflow |
| Customer adds scope on Day 1 afternoon | Brief locked it. New ideas go to parking lot. |
| Demo crashes live | Switch to backup screenshots. Narrate what it does. |
| Customer dissatisfied at 75% mark | Facilitator checks in: adjust scope, don't ignore |

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Running Your First Hackathon](running-your-first-hackathon.md) | End-to-end timeline |
| [Time-Boxing](../principles/time-boxing.md) | Philosophy behind time constraints |
| [Customer First](../principles/customer-first.md) | Customer-centric design principles |
| [Formation Checklist](../../.hackathon/checklist-formation.md) | Operational pre-hackathon checklist |
