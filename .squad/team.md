# Squad Team

> Hackathon Delivery Squad — Dispatched from squad-headquarters

## Coordinator

| Name | Role | Notes |
|------|------|-------|
| Squad | Coordinator | Routes work, enforces handoffs and time-boxes. |

## Members

| Name | Role | Charter | Status |
|------|------|---------|--------|
| Jared | Facilitator | [charter](agents/jared/charter.md) | 🎯 Active |
| Gilfoyle | Architect | [charter](agents/gilfoyle/charter.md) | 🧠 Active |
| Richard | Builder | [charter](agents/richard/charter.md) | 🔧 Active |
| Dinesh | Data Wrangler | [charter](agents/dinesh/charter.md) | 📊 Active |
| Erlich | Demo Crafter | [charter](agents/erlich/charter.md) | 🎤 Active |
| Scribe | Session Logger | [charter](agents/scribe/charter.md) | 📋 Active |
| Ralph | Work Monitor | — | 🔄 Monitor |
| @copilot | Coding Agent | [copilot-instructions](.github/copilot-instructions.md) | 🤖 Active |

<!-- copilot-auto-assign: true -->

### @copilot Capability Profile

| Category | Fit | Examples |
|----------|-----|---------|
| PoC code scaffolding | 🟢 Good | Create notebook stubs, pipeline boilerplate, integration code |
| Data processing scripts | 🟢 Good | Pandas transforms, Spark jobs, data cleaning scripts |
| Bug fixes in PoC code | 🟢 Good | Fix logic errors, handle edge cases, debug issues |
| Test writing | 🟢 Good | Unit tests, integration test stubs, validation scripts |
| Documentation | 🟢 Good | README updates, inline docs, API descriptions |
| Multi-file refactoring | 🟡 Caution | May miss cross-file dependencies in time-pressured hackathon |
| Architecture decisions | 🔴 Avoid | No trade-off judgment — escalate to Gilfoyle |
| Demo narrative | 🔴 Avoid | No audience awareness — escalate to Erlich |
| Customer-facing content | 🔴 Avoid | Always escalate to Sarah |

## Project Context

- **Owner:** Sarah Moens
- **Organization:** Dispatched from squad-headquarters
- **Principal/CEO:** Sarah Moens — Cloud Solution Architect at Microsoft Belgium
- **Nature:** Hackathon template — stamped per engagement
- **Cast Universe:** Silicon Valley
- **Tech Stack:** General-purpose (accelerator packs are pluggable per engagement)
- **Created:** 2026-03-31
- **Dispatched From:** squad-headquarters

## Operating Rhythm

### Hackathon Cadence

The squad follows a 4-phase operating rhythm aligned to hackathon delivery:

**1. Formation (pre-hackathon)**
- Jared sets scope boundaries and prepares use case templates
- Gilfoyle reviews available data and tech constraints
- Dinesh stages sample/customer data
- Erlich drafts initial narrative framing

**2. Delivery (hackathon days)**
- Morning Alignment → Midday Checkpoint → End-of-day sync
- Jared time-boxes all sessions
- Richard and Dinesh build in tight loops
- Gilfoyle provides go/no-go on technical approaches
- Scribe captures everything continuously

**3. Wind-Down (post-hackathon)**
- Erlich leads demo prep and dry-run
- Jared facilitates retrospective
- Scribe compiles engagement summary

**4. Knowledge Capture (post-wind-down)**
- Scribe pushes learnings to HQ
- Reusable patterns extracted to `.squad/skills/`
- Decision log archived

## Escalation Rules

### Always escalate to Sarah
1. **Customer scope change** — any shift in what was agreed for the hackathon
2. **Technical dead-end** — the PoC approach is fundamentally blocked
3. **Customer relationship signal** — tension, dissatisfaction, or unexpected stakeholder dynamics

### Handle autonomously (report in daily digest)
- PoC technical decisions within agreed scope
- Data sourcing and preparation choices
- Demo flow and narrative adjustments
- Internal documentation and logging
- Routine triage and task assignment
