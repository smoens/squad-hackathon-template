<div align="center">

<br>

# Hackathon Squad

**From blank canvas to live demo — a battle-tested framework for business hackathons.**

<br>

<p>
<a href="#lifecycle"><img src="https://img.shields.io/badge/IDEATE-4F46E5?style=for-the-badge" alt="ideate" /></a>&nbsp;
<a href="#lifecycle"><img src="https://img.shields.io/badge/BUILD-0D9488?style=for-the-badge" alt="build" /></a>&nbsp;
<a href="#lifecycle"><img src="https://img.shields.io/badge/DEMO-F97066?style=for-the-badge" alt="demo" /></a>
</p>
<p>
<img src="https://img.shields.io/badge/stack_agnostic-374151?style=flat-square" alt="stack agnostic" />
<img src="https://img.shields.io/badge/template_repo-374151?style=flat-square" alt="template repo" />
</p>

<sub>Stamp a repo, drop in an <a href="accelerators/README.md">accelerator pack</a>, and go.</sub>

<br>

</div>

---

## Getting Started

1. **Stamp** a new repo from this template
2. **Add an accelerator** — drop a pattern pack into [`accelerators/`](accelerators/README.md)
3. **Configure** — fill [`BRIEF.md`](BRIEF.md) and [`.hackathon/config.json`](.hackathon/config.json)
4. **Run** — follow the [lifecycle](#lifecycle--deliverables) below

---

## Lifecycle & Deliverables

```mermaid
---
config:
  theme: base
  themeVariables:
    primaryColor: "#4F46E5"
    lineColor: "#9CA3AF"
    primaryTextColor: "#fff"
---
graph LR
    A(["Formation"]):::prep --> B(["Ideation"]):::ideate --> C(["Build"]):::build --> D(["Demo"]):::demo --> E(["Wind-Down"]):::wrap

    classDef prep fill:#6366F1,stroke:#4F46E5,color:#fff,rx:20
    classDef ideate fill:#4F46E5,stroke:#3730A3,color:#fff,rx:20
    classDef build fill:#0D9488,stroke:#0F766E,color:#fff,rx:20
    classDef demo fill:#F97066,stroke:#DC2626,color:#fff,rx:20
    classDef wrap fill:#374151,stroke:#1F2937,color:#fff,rx:20

    linkStyle default stroke:#9CA3AF,stroke-width:2px
```

| Stage | When | What happens | Documents |
|-------|------|-------------|-----------|
| **Formation** | Pre-hackathon | Assemble team, prep data, set scope | [BRIEF.md](BRIEF.md), [config.json](.hackathon/config.json), [checklist-formation](.hackathon/checklist-formation.md) |
| **Ideation** | Day 1 morning | Use case brainstorming, feasibility scoring | [use-case-canvas](templates/use-case-canvas.md), [feasibility-scorecard](templates/feasibility-scorecard.md) |
| **Build** | Day 1 afternoon – Day 2 | PoC development, data wrangling | [use-case template](use-cases/_template.md), [decision template](architecture/decisions/_template.md) |
| **Demo** | Final session | Pitch narrative, live presentation | [demo-script](templates/demo-script-template.md) |
| **Wind-Down** | Post-hackathon | Retrospective, knowledge capture, handoff | [HANDOFF.md](HANDOFF.md), [RETRO.md](RETRO.md), [checklist-winddown](.hackathon/checklist-winddown.md), [checklist-knowledge](.hackathon/checklist-knowledge-extract.md) |

---

## Roles

| Name | Role | Focus |
|------|------|-------|
| Jared | Facilitator | Use case capture, time-boxing, scope gates |
| Gilfoyle | Architect | Feasibility, architecture sketch, build/no-build |
| Richard | Builder | PoC execution — notebooks, pipelines |
| Dinesh | Data Wrangler | Data sourcing, cleaning, simulators |
| Erlich | Demo Crafter | Demo narrative, storytelling, pitch coaching |

---

## Documentation

| Section | What's inside |
|---------|---------------|
| [Concepts](docs/concepts/) | Core ideas — industry tailoring, hackathon lifecycle, accelerator architecture, use-case-driven development |
| [Guides](docs/guides/) | Step-by-step instructions — getting started, running ideation, demo crafting, data simulation, customer engagement |
| [Principles](docs/principles/) | Foundational agreements — time-boxing, scope management, customer-first, squad operating principles |
| [Full Index](docs/index.md) | Every document in one searchable table |

---

## Repository Structure

| Directory | Purpose |
|-----------|---------|
| [`accelerators/`](accelerators/) | Reusable industry/pattern packs — drop one in to jumpstart a hackathon |
| [`architecture/`](architecture/) | Architecture Decision Records (ADRs) for technical choices |
| [`data/`](data/) | Sample datasets and customer data (gitignored) |
| [`docs/`](docs/) | All documentation — concepts, guides, principles |
| [`infrastructure/`](infrastructure/) | Provisioning scripts and IaC templates |
| [`log/`](log/) | Session logs, daily sitreps, scribe notes |
| [`templates/`](templates/) | Reusable templates — use case canvas, feasibility scorecard, demo script |
| [`use-cases/`](use-cases/) | One folder per use case explored during a hackathon |
| [`.hackathon/`](.hackathon/) | Runtime config and phase checklists |
