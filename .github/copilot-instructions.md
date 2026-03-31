# Copilot Instructions — Hackathon Squad Template

## What This Repo Is

This is a **battle-tested framework for business hackathons**. You stamp a new repo from this template for each customer engagement, drop in accelerator packs for the tech stack, and run the hackathon lifecycle. The output is working PoC demos and a customer handoff document.

**Stack:** Tech-stack agnostic at the template level. Accelerator packs plug in specific technologies (Azure Fabric, Databricks, Azure AI, etc.).

---

## Engagement Context

**Always read `BRIEF.md` first** for customer context (who, what industry, dates, format). Then read `.hackathon/config.json` for squad configuration and Azure resources:

```json
{
  "squad": { "hq_repo": "..." },
  "accelerator_packs": ["..."],
  "azure_resources": { "resource_group": "...", "subscription": "..." },
  "hq_repo": "..."
}
```

If `BRIEF.md` still has `[FILL]` markers, this repo hasn't been configured for an engagement yet — you're working on the template itself.

---

## Directory Structure

```
.
├── BRIEF.md                          # Customer engagement brief (goals, scope, attendees, constraints)
├── HANDOFF.md                        # Customer deliverable (completed post-hackathon)
├── RETRO.md                          # Retrospective (completed post-hackathon)
├── README.md                         # Repo overview
├── .hackathon/
│   ├── config.json                   # ⭐ Squad config & Azure resources
│   └── README.md                     # Hackathon config docs
├── playbook/
│   ├── start-here.md                 # Orientation — read this on Day 1
│   ├── ideation-cheat-sheet.md       # Quick brainstorm techniques
│   ├── demo-crafting.md              # How to build compelling demos
│   ├── checklists.md                 # Formation, wind-down & knowledge-extract checklists
│   ├── atmosphere-and-energy.md      # Tips for energy, music, breaks
│   ├── what-if-cards.md              # Scenario prompts for creativity
│   ├── use-case-canvas.md            # Quick ideation card (one per candidate use case)
│   ├── feasibility-scorecard.md      # 6-dimension scoring framework
│   └── demo-script-template.md       # 5-section demo narrative structure
├── build/
│   ├── README.md                     # Build-phase guidance
│   ├── decisions/
│   │   └── _template.md              # Architecture Decision Card (ADC) template
│   ├── data/.gitkeep                 # Sample/synthetic datasets per use case
│   ├── notebooks/.gitkeep            # Notebooks created during build
│   └── scripts/.gitkeep              # Utility scripts created during build
├── use-cases/
│   ├── _template.md                  # Full use case document template
│   └── {uc-name}.md                  # One file per selected use case
├── accelerators/
│   ├── README.md                     # How accelerator packs work
│   ├── _template/                    # Template for creating new packs
│   └── {pack-name}/                  # Tech-specific accelerator packs
├── log/                              # Engagement session logs
├── .squad/                           # Squad AI team configuration
│   ├── team.md                       # Roster: who does what
│   ├── routing.md                    # Work assignment rules
│   ├── ceremonies.md                 # Ceremony configuration
│   ├── agents/{name}/                # Agent charters and history
│   └── skills/                       # Reusable knowledge captured during engagements
└── .github/
    ├── copilot-instructions.md       # THIS FILE
    └── prompts/                      # Reusable Copilot prompts
```

### What Lives Where

| You want to... | Go to... |
|----------------|----------|
| Get started | `playbook/start-here.md` |
| Understand the customer | `BRIEF.md` |
| See engagement config | `.hackathon/config.json` |
| Run formation | `playbook/checklists.md` |
| Brainstorm use cases | `playbook/use-case-canvas.md` |
| Score feasibility | `playbook/feasibility-scorecard.md` |
| Write a use case doc | `use-cases/_template.md` → copy to `use-cases/{name}.md` |
| Record architecture decisions | `build/decisions/_template.md` |
| Build a PoC | `use-cases/{name}/` + `accelerators/{pack}/` |
| Prepare a demo | `playbook/demo-script-template.md` |
| Write the customer deliverable | `HANDOFF.md` |
| Run a retrospective | `RETRO.md` |
| Add tech-specific patterns | `accelerators/` |
| Provision Azure resources | `build/` |
| Store sample data | `build/data/` |

---

## The Squad

This repo is operated by an AI squad inspired by Silicon Valley characters. Each agent has a distinct role. **Talk to them conversationally** — they work best as teammates, not tools.

| Agent | Role | Talk to them about... |
|-------|------|----------------------|
| **Jared** | Facilitator | *"Let's set up a hackathon for Contoso"*, *"Let's brainstorm"*, time-boxing, scope gates, prioritization |
| **Gilfoyle** | Architect | *"Is this feasible?"*, architecture decisions, build/no-build calls, tech stack |
| **Richard** | Builder | PoC implementation — notebooks, pipelines, integrations, code |
| **Dinesh** | Data Wrangler | Data sourcing, cleaning, simulators, schema design, sample generation |
| **Erlich** | Demo Crafter | *"Draft a demo for this PoC"*, storytelling, pitch structure, presentation coaching |
| **Scribe** | Session Logger | Automatic — captures decisions, session notes, engagement log |

### How to Work With Agents

**Just talk to them.** Mention agents by name when your work is in their domain:

- "Jared, let's set up a hackathon for Contoso — they're in manufacturing."
- "Jared, let's brainstorm — what could we build for them?"
- "Gilfoyle, is this architecture feasible in a 1-day hackathon?"
- "Richard, build a notebook that ingests from this CSV and writes to Lakehouse."
- "Dinesh, we need a synthetic dataset for 10K customer records with these columns."
- "Erlich, draft a demo script for the anomaly detection PoC."

### When to Use @copilot vs. Squad Agents

| Task | Route |
|------|-------|
| Write code, fix bugs, scaffold notebooks | @copilot or Richard |
| Data processing scripts | @copilot or Dinesh |
| Architecture decisions, trade-offs | Gilfoyle (never @copilot) |
| Demo narrative, customer-facing content | Erlich (never @copilot) |
| Scope decisions, prioritization | Jared (never @copilot) |
| Tests, docs, single-file fixes, boilerplate | @copilot |

---

## Lifecycle Awareness

The hackathon runs in 5 stages. The current phase determines what artifacts you should be producing.

### 1. Formation (Pre-Hackathon)

**Goal:** Prepare everything before Day 1.
**Produce:** Completed `BRIEF.md`, configured `.hackathon/config.json`, selected accelerator packs, staged data.
**Checklist:** `playbook/checklists.md`

### 2. Ideation (Day 1 Morning)

**Goal:** Brainstorm use cases and select which to build.
**Produce:** Filled use case canvases (`playbook/use-case-canvas.md`), feasibility scorecards, ranked priorities.
**Key rule:** Score ALL candidate use cases before committing to any. Use the 6-dimension scoring in `playbook/feasibility-scorecard.md`.

### 3. Build (Day 1 Afternoon – Day 2)

**Goal:** Build working PoCs for selected use cases.
**Produce:** Code in `use-cases/{name}/`, architecture decisions in `build/decisions/`, data pipelines.
**Key rule:** Time-box aggressively. If data is blocked, Dinesh creates simulators. If architecture is unclear, Gilfoyle decides immediately.

### 4. Demo (Final Session)

**Goal:** Present working demos to customer stakeholders.
**Produce:** Demo scripts (`playbook/demo-script-template.md`), completed `HANDOFF.md`.
**Key rule:** Follow the 5-section structure: Problem (30s) → Solution (60s) → Live Demo (2-3min) → Impact (30s) → The Ask (30s).

### 5. Wind-Down (Post-Hackathon)

**Goal:** Capture knowledge and close the engagement.
**Produce:** `RETRO.md`, knowledge extraction, template improvements.
**Checklists:** `playbook/checklists.md`

---

## Template Conventions

### Fill Patterns

All templates use consistent markers:

| Marker | Meaning |
|--------|---------|
| `[FILL]` | Replace with actual content |
| `[FILL — e.g., "..."]` | Replace, with example guidance |
| `[1/2/3]` | Pick one value |
| `⬜ / 🔨 / ✅` | Status progression |
| `- [ ]` | Checklist item — check when done |

### Creating Use Cases

1. Copy `use-cases/_template.md` to `use-cases/{short-name}.md`
2. Assign an ID: `UC-001`, `UC-002`, etc.
3. Fill the Use Case Canvas first (quick brainstorm)
4. Score with the Feasibility Scorecard
5. Only if scored 🟢 or 🟡: fill the full use case document

### Architecture Decision Cards (ADCs)

Used during the Build phase. Lightweight — not full ADRs.

| Field | Purpose |
|-------|---------|
| Use Case | Which UC this applies to (or "Cross-cutting") |
| Pattern | Which accelerator pack pattern, if any |
| Decision | What was chosen |
| Why | One sentence rationale |
| Trade-off | What was sacrificed |
| Revisit for production | Yes/No + what changes |

---

## Accelerator Packs

Accelerator packs are pluggable technology modules in `accelerators/`. They contain:
- Reference architectures
- Starter notebooks
- Provisioning scripts (Terraform/Bicep)
- Sample data

### Loading a Pack

1. Select based on customer tech landscape and use cases
2. Add pack names to `.hackathon/config.json` → `accelerator_packs[]`
3. Copy relevant assets into `use-cases/{name}/` or reference directly
4. Follow the pack's `README.md` for setup

### Creating a New Pack

Copy `accelerators/_template/` and fill it in. Structure:

```
accelerators/{pack-name}/
├── README.md               # Description, scenarios, prerequisites, setup
├── architecture/            # Reference architecture diagrams
├── notebooks/               # Starter notebooks
├── scripts/                 # Provisioning or utility scripts
└── data/                    # Sample datasets
```

---

## Code Conventions

### Notebooks

- Use descriptive names: `01-data-ingestion.ipynb`, `02-transform.ipynb`, `03-model.ipynb`
- First cell: description of what the notebook does, inputs, outputs
- Keep notebooks focused — one pipeline stage per notebook
- Use markdown cells to explain each section
- Pin library versions in requirements when practical

### Scripts

- Infrastructure provisioning goes in `build/`
- Utility scripts go in the accelerator pack's `scripts/` directory
- Use `#!/usr/bin/env python3` or equivalent shebang
- Include a docstring at the top explaining purpose and usage

### Terraform / Bicep

- Place in `build/` at repo root or within accelerator packs
- Use variables for resource group, subscription, and location — pull from `.hackathon/config.json`
- Tag all resources with `hackathon: true`, `customer: {name}`, `engagement-date: {date}`
- Default to the cheapest SKU that works for PoC purposes

### config.json Usage

When generating code that references Azure resources, read from `.hackathon/config.json`:

```python
import json
with open('.hackathon/config.json') as f:
    config = json.load(f)
resource_group = config['azure_resources']['resource_group']
```

---

## Content Style

All content in this repo may end up in front of customers. Follow these rules:

1. **Structured and scannable** — use headers, tables, bullet points. No walls of text.
2. **Quantify where possible** — "saves 40 hours/month" not "saves significant time."
3. **Customer-facing awareness** — `HANDOFF.md` and demo scripts go directly to the customer. No internal jargon.
4. **Templates are self-documenting** — every template has `📎 Related` sections linking to relevant docs.
5. **Mermaid for architecture** — use Mermaid diagrams in markdown, not external tools.

---

## Key Documents Quick Reference

| Phase | Key Documents |
|-------|--------------|
| Formation | [BRIEF.md](../BRIEF.md), [config.json](../.hackathon/config.json), [checklists](../playbook/checklists.md) |
| Ideation | [use-case-canvas](../playbook/use-case-canvas.md), [feasibility-scorecard](../playbook/feasibility-scorecard.md) |
| Build | [use-case template](../use-cases/_template.md), [ADC template](../build/decisions/_template.md), [accelerators](../accelerators/README.md) |
| Demo | [demo-script-template](../playbook/demo-script-template.md), [HANDOFF.md](../HANDOFF.md) |
| Wind-Down | [RETRO.md](../RETRO.md), [checklists](../playbook/checklists.md) |

---

## Prompts

Reusable prompts are available in `.github/prompts/`:

| Prompt | Use when... |
|--------|-------------|
| `kickstart.prompt.md` | Auto-setup: research a customer, fill BRIEF.md, generate conversation starters |
| `ideation.prompt.md` | Brainstorming use cases from a customer brief |
| `feasibility.prompt.md` | Scoring a use case across the 6 dimensions |
| `demo-script.prompt.md` | Writing a demo script from a working PoC |
| `use-case-brief.prompt.md` | Turning a raw problem statement into a structured brief |
| `data-readiness.prompt.md` | Assessing data landscape and readiness |
