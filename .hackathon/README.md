← [README](../README.md)

# Hackathon Configuration & Checklists

Engagement configuration and phase-based checklists for the hackathon lifecycle.

---

## Contents

| File | Purpose |
|------|---------|
| [`config.json`](config.json) | Engagement configuration — customer, dates, squad, accelerator packs, Azure resources |
| [`checklist-formation.md`](checklist-formation.md) | Pre-hackathon formation checklist |
| [`checklist-winddown.md`](checklist-winddown.md) | Post-hackathon wind-down checklist |
| [`checklist-knowledge-extract.md`](checklist-knowledge-extract.md) | Knowledge extraction checklist |

## config.json

The central source of truth for the engagement. Referenced by infrastructure provisioning scripts, architecture decisions, and knowledge extraction.

Key fields:

| Field | Purpose |
|-------|---------|
| `customer` | Customer name |
| `industry` | Industry vertical |
| `dates` | Start and end dates |
| `squad` | Agent assignments |
| `accelerator_packs` | Which packs are loaded |
| `azure_resources` | Resource group, subscription |

## Phase Checklists

### Pre-Hackathon (Formation)

Use [`checklist-formation.md`](checklist-formation.md) — 1-2 weeks before kickoff:

- Confirm squad membership and roles
- Validate customer brief and data availability
- Provision Azure resources
- Set up accelerator environments

### Post-Hackathon (Wind-Down)

Use [`checklist-winddown.md`](checklist-winddown.md) — last day + 1 week:

- Finalize demo and handoff materials
- Decommission temporary Azure resources
- Archive logs and decision records
- Conduct retrospective

### Knowledge Extraction

Use [`checklist-knowledge-extract.md`](checklist-knowledge-extract.md) — final week + 1 week:

- Extract reusable patterns from code
- Update accelerators with lessons learned
- Validate HANDOFF.md completeness

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [BRIEF.md](../BRIEF.md) | Customer engagement brief |
| [HANDOFF.md](../HANDOFF.md) | Deliverables for customer |
| [RETRO.md](../RETRO.md) | Post-engagement retrospective |
| [Getting Started](../docs/guides/getting-started.md) | Full setup walkthrough |
