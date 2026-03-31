<div align="center">

<br>

# Hackathon Squad

**From blank canvas to live demo — a battle-tested framework for business hackathons.**

<br>

<p>
<a href="#-lifecycle"><img src="https://img.shields.io/badge/IDEATE-4F46E5?style=for-the-badge" alt="ideate" /></a>&nbsp;
<a href="#-lifecycle"><img src="https://img.shields.io/badge/BUILD-0D9488?style=for-the-badge" alt="build" /></a>&nbsp;
<a href="#-lifecycle"><img src="https://img.shields.io/badge/DEMO-F97066?style=for-the-badge" alt="demo" /></a>
</p>
<p>
<img src="https://img.shields.io/badge/stack_agnostic-374151?style=flat-square" alt="stack agnostic" />
<img src="https://img.shields.io/badge/template_repo-374151?style=flat-square" alt="template repo" />
<img src="https://img.shields.io/badge/AI_powered-374151?style=flat-square" alt="AI powered" />
</p>

<sub>Stamp a repo, drop in an <a href="accelerators/README.md">accelerator pack</a>, and let your AI squad run.</sub>

<br>

</div>

---

## 🚀 Getting Started

This isn't just a folder structure — it's a _team in a box_. When you stamp this template, you get five AI agents, two encoded skills, five ready-to-run Copilot prompts, and a full process framework. Everything is pre-wired so you can focus on building, not organizing.

### 1. Stamp a new repo

Use GitHub's **Use this template** button. You'll get the entire squad, all docs, and all config — ready to go.

### 2. Drop in an accelerator

Browse [`accelerators/`](accelerators/README.md) or [build your own](docs/guides/accelerator-development.md). An accelerator is a plug-in pattern pack (notebooks, sample data, scripts) tailored to a specific industry or scenario. It jumpstarts the build so your squad isn't starting from zero.

### 3. Configure your hackathon

Fill in two files:
- **[`BRIEF.md`](BRIEF.md)** — customer context, pain points, initial use case hypotheses
- **[`.hackathon/config.json`](.hackathon/config.json)** — dates, industry, team composition, Azure settings

### 4. Run

Follow the [lifecycle](#-lifecycle) below. Your AI squad knows the process — use the [Copilot prompts](#-copilot-prompts) to kick off each phase, and let the agents handle the structure while you handle the thinking.

<details>
<summary>📖 More on accelerators and the plug-in pattern</summary>

Accelerators are self-contained packs that slot into the `accelerators/` directory. Each pack can include notebooks, sample datasets, provisioning scripts, and architecture scaffolds. When a squad starts a hackathon, they pick the accelerator that matches the customer's industry — manufacturing, energy, financial services — and the build phase starts with running code instead of an empty notebook.

See [Accelerator Architecture](docs/concepts/accelerator-architecture.md) for the design, or the [`_template/`](accelerators/_template/) to build your own.

</details>

---

## 🤖 Your Squad

This is what makes Hackathon Squad different. You don't just get files — you get an **AI team** that knows how to run hackathons. Each agent has a [charter](.squad/agents/) that defines their role, boundaries, and working patterns. The whole squad is backed by [skills](#-skills) that encode reusable expertise and [Copilot prompts](#-copilot-prompts) that activate each workflow step.

### The Team

| | Name | Role | What they do | Charter |
|---|------|------|-------------|---------|
| 🎯 | **Jared** | Facilitator | Runs ideation, captures use cases as structured briefs, enforces time-boxes and scope gates | [charter](.squad/agents/jared/charter.md) |
| 🏗️ | **Gilfoyle** | Architect | Scores feasibility across 6 dimensions, sketches architecture (Mermaid), makes build/no-build calls | [charter](.squad/agents/gilfoyle/charter.md) |
| ⚡ | **Richard** | Builder | Executes the PoC — notebooks, pipelines, APIs. Builds within the scoped architecture, nothing more | [charter](.squad/agents/richard/charter.md) |
| 🔧 | **Dinesh** | Data Wrangler | Sources and shapes data _ahead_ of the build. Creates simulators when customer data isn't available | [charter](.squad/agents/dinesh/charter.md) |
| 🎤 | **Erlich** | Demo Crafter | Turns a working PoC into a 5-minute story: Problem → Solution → Live Demo → Impact → The Ask | [charter](.squad/agents/erlich/charter.md) |

Plus **Scribe** (session logging) and **@copilot** (general assist) in supporting roles.

<details>
<summary>How the agents work together</summary>

The squad follows a strict handoff chain — no one freelances outside their lane:

1. **Jared** captures raw customer problems and shapes them into structured Use Case Briefs
2. **Gilfoyle** takes each brief and scores it across 6 feasibility dimensions (data, quality, integration, complexity, visualization, security) — kill or build
3. **Dinesh** prepares the data landscape _before_ build starts — sourcing, cleaning, or simulating
4. **Richard** takes Gilfoyle's architecture + Dinesh's data and builds the PoC
5. **Erlich** takes the working PoC and crafts the demo narrative

Each agent's boundaries are explicit in their charter. The routing rules live in [`.squad/routing.md`](.squad/routing.md).

</details>

### 🧠 Skills

Skills are encoded knowledge that agents draw on. They're not just documentation — they contain decision rules, scoring frameworks, and patterns that make the squad's output consistent across hackathons.

| Skill | What it encodes |
|-------|----------------|
| [Hackathon Facilitation](.squad/skills/hackathon-facilitation/SKILL.md) | Phase transition gates, time-boxing rules, pivot-vs-push decisions, scope management patterns |
| [Industry Tailoring](.squad/skills/industry-tailoring/SKILL.md) | Per-industry data patterns, common personas, Azure service mappings, feasibility benchmarks |

### 💬 Copilot Prompts

Ready-to-run prompts that activate the right agent for each workflow step. Open any of these in VS Code and Copilot becomes your squad member:

| Prompt | Agent | What it does |
|--------|-------|-------------|
| [ideation.prompt.md](.github/prompts/ideation.prompt.md) | Jared | Brainstorm use cases from a customer brief, generate canvases, score feasibility |
| [use-case-brief.prompt.md](.github/prompts/use-case-brief.prompt.md) | Jared | Turn a raw problem statement into a structured brief with pain point, process, outcome, stakeholders, value |
| [feasibility.prompt.md](.github/prompts/feasibility.prompt.md) | Gilfoyle | Score a use case across 6 dimensions, produce a filled feasibility scorecard |
| [data-readiness.prompt.md](.github/prompts/data-readiness.prompt.md) | Dinesh | Assess data landscape, identify gaps, suggest simulator patterns, flag blockers |
| [demo-script.prompt.md](.github/prompts/demo-script.prompt.md) | Erlich | Generate a 5-section demo script from a working PoC description |

The whole squad also shares project-wide context via [`.github/copilot-instructions.md`](.github/copilot-instructions.md).

---

## 🔄 Lifecycle

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

<details>
<summary><strong>🟣 Formation</strong> — Pre-hackathon</summary>

Assemble the team, prep data, set scope. Nothing starts until the brief is solid.

**What happens:**
- Fill [`BRIEF.md`](BRIEF.md) with customer context, pain points, and initial use case hypotheses
- Configure [`.hackathon/config.json`](.hackathon/config.json) with dates, industry, and team settings
- Provision Azure environment (if applicable)
- Stage sample data or confirm simulators
- Run the [formation checklist](.hackathon/checklist-formation.md)

**Key documents:** [BRIEF.md](BRIEF.md) · [config.json](.hackathon/config.json) · [checklist-formation](.hackathon/checklist-formation.md) · [getting-started guide](docs/guides/getting-started.md)

</details>

<details>
<summary><strong>🔵 Ideation</strong> — Day 1 morning</summary>

Brainstorm use cases, score feasibility, select what to build. Jared facilitates; Gilfoyle gates.

**What happens:**
- Use case brainstorming with the [`ideation` prompt](.github/prompts/ideation.prompt.md)
- Structure each idea into a [Use Case Canvas](templates/use-case-canvas.md)
- Score with the [Feasibility Scorecard](templates/feasibility-scorecard.md) using the [`feasibility` prompt](.github/prompts/feasibility.prompt.md)
- Build/no-build decision

**Key documents:** [use-case-canvas](templates/use-case-canvas.md) · [feasibility-scorecard](templates/feasibility-scorecard.md) · [running-ideation guide](docs/guides/running-ideation.md) · [use-case prioritization](docs/concepts/use-case-prioritization.md)

</details>

<details>
<summary><strong>🟢 Build</strong> — Day 1 afternoon – Day 2</summary>

Heads-down PoC development. Dinesh wrangles data; Richard writes code; Gilfoyle reviews architecture.

**What happens:**
- Dinesh assesses data readiness with the [`data-readiness` prompt](.github/prompts/data-readiness.prompt.md)
- Richard builds within the scoped architecture — notebooks, pipelines, APIs
- Architecture decisions logged as [ADCs](architecture/decisions/_template.md)
- Use cases tracked in [`use-cases/`](use-cases/)

**Key documents:** [use-case template](use-cases/_template.md) · [decision template](architecture/decisions/_template.md) · [data-simulation playbook](docs/guides/data-simulation-playbook.md)

</details>

<details>
<summary><strong>🔴 Demo</strong> — Final session</summary>

Turn a working PoC into a story that sells. Erlich crafts the narrative; the team rehearses.

**What happens:**
- Generate a demo script with the [`demo-script` prompt](.github/prompts/demo-script.prompt.md)
- Follow the 5-section structure: Problem (30s) → Solution (60s) → Live Demo (2–3 min) → Impact (30s) → The Ask (30s)
- Rehearse, tighten, present

**Key documents:** [demo-script template](templates/demo-script-template.md) · [demo-crafting guide](docs/guides/demo-crafting.md)

</details>

<details>
<summary><strong>⚫ Wind-Down</strong> — Post-hackathon</summary>

Retrospective, knowledge capture, and handoff. Nothing evaporates.

**What happens:**
- Run the [wind-down checklist](.hackathon/checklist-winddown.md) and [knowledge extraction checklist](.hackathon/checklist-knowledge-extract.md)
- Fill the [RETRO.md](RETRO.md)
- Prepare [HANDOFF.md](HANDOFF.md) for follow-on teams

**Key documents:** [HANDOFF.md](HANDOFF.md) · [RETRO.md](RETRO.md) · [checklist-winddown](.hackathon/checklist-winddown.md) · [checklist-knowledge](.hackathon/checklist-knowledge-extract.md)

</details>

---

## 📚 Documentation

| Section | What's inside |
|---------|---------------|
| [Concepts](docs/concepts/) | Core ideas — [hackathon lifecycle](docs/concepts/hackathon-lifecycle.md), [accelerator architecture](docs/concepts/accelerator-architecture.md), [industry tailoring](docs/concepts/industry-tailoring.md), [use-case-driven development](docs/concepts/use-case-driven-development.md), [AI-augmented hackathons](docs/concepts/ai-augmented-hackathons.md) |
| [Guides](docs/guides/) | Step-by-step — [getting started](docs/guides/getting-started.md), [running ideation](docs/guides/running-ideation.md), [demo crafting](docs/guides/demo-crafting.md), [data simulation](docs/guides/data-simulation-playbook.md), [customer engagement](docs/guides/customer-engagement-checklist.md), [your first hackathon](docs/guides/running-your-first-hackathon.md) |
| [Principles](docs/principles/) | Foundational agreements — [time-boxing](docs/principles/time-boxing.md), [scope management](docs/principles/scope-management.md), [customer-first](docs/principles/customer-first.md), [squad operating principles](docs/principles/squad-operating-principles.md) |
| [Full Index](docs/index.md) | Every document in one searchable table |

---

## 🗂️ Repository Structure

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
| [`.squad/`](.squad/) | AI squad config — agent charters, skills, routing, ceremonies |
| [`.github/prompts/`](.github/prompts/) | Copilot prompts for each workflow step |
