<div align="center">

# ⚡ Hackathon Squad

**Two days. One squad. Real customer problems. Live demos that actually work.**

> You just stamped yourself a hackathon. By the end of this, you'll have working PoCs,
> a rehearsed demo, and a handoff doc your boss will actually read.
>
> Let's build something real.

<p>
<a href="#-lifecycle"><img src="https://img.shields.io/badge/IDEATE-4F46E5?style=for-the-badge" alt="ideate" /></a>&nbsp;
<a href="#-lifecycle"><img src="https://img.shields.io/badge/BUILD-0D9488?style=for-the-badge" alt="build" /></a>&nbsp;
<a href="#-lifecycle"><img src="https://img.shields.io/badge/DEMO-F97066?style=for-the-badge" alt="demo" /></a>
</p>
<p>
<img src="https://img.shields.io/badge/AI_squad-374151?style=flat-square" alt="AI squad" />
<img src="https://img.shields.io/badge/template_repo-374151?style=flat-square" alt="template repo" />
<img src="https://img.shields.io/badge/battle_tested-374151?style=flat-square" alt="battle tested" />
</p>

**Initialized by the Arcane Universe Squad**

📦 Mel · 🔬 Caitlyn · 🏗️ Jayce · 🎨 Jinx · ⚙️ Silco

<sub>Crafted with creative energy and a touch of hextech.</sub>

<br>

</div>

---

## 🚀 Quick Start

| Step | What | How |
|:----:|------|-----|
| **1** | Fill your brief | Edit [`BRIEF.md`](BRIEF.md) — or use the **ideation** prompt to auto-generate a draft |
| **2** | Run formation | Walk through the [formation checklist](playbook/checklists.md) |
| **3** | Follow the lifecycle | Ideate → Build → Demo → Ship (see below) |
| **4** | Hand it off | Fill [`HANDOFF.md`](HANDOFF.md) and send it to the customer's boss |

> 💡 **First time?** Start with the [Start Here guide](playbook/start-here.md) — it walks you through everything.

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

### Energy Arc

| Stage | Energy | What happens |
|-------|--------|-------------|
| **Formation** | 🧠 Focused | Prep, scope, data staging — get the room ready |
| **Ideation** | 🔥 High | Brainstorm, score, commit — the ideas are flying |
| **Build** | 🧠→⚡ Focused→Spike | Deep work + mid-build celebrations when things click |
| **Demo** | 🏆 Crescendo | The show — walk-on music, awards, applause |
| **Wind-Down** | 🌟 Warm | Celebrate, capture, hand off — nothing evaporates |

---

## 🤖 Your Squad

Five AI agents, each with a personality and a job. They don't freelance — they follow a strict handoff chain.

| Name | Role | What they actually do |
|------|------|-----------------------|
| **Jared** | Facilitator | Keeps the room on track. Shapes messy brainstorms into crisp use cases. Holds the clock like his life depends on it. |
| **Gilfoyle** | Architect | Scores every idea across 6 brutal feasibility dimensions. If it can't be built, he'll tell you before you waste 4 hours. |
| **Richard** | Builder | Turns architecture sketches into running code. Builds the demo-able slice, nothing more. |
| **Dinesh** | Data Wrangler | Gets data flowing before the build starts. If customer data isn't available, he'll simulate it. No one waits on Dinesh. |
| **Erlich** | Demo Crafter | Takes your working PoC and turns it into a 5-minute story that makes customers lean forward. |

Plus **Scribe** (captures everything) and **@copilot** (general assist) in supporting roles. Agent charters live in [`.squad/agents/`](.squad/agents/).

---

## 💬 Copilot Prompts

> 💡 **New here?** Start with the **ideation** prompt — just tell it your customer's name and pain points and watch the magic happen.

| Prompt | Agent | What it does |
|--------|-------|-------------|
| [ideation](.github/prompts/ideation.prompt.md) | Jared | Brainstorm use cases from a customer brief, generate canvases, score feasibility |
| [use-case-brief](.github/prompts/use-case-brief.prompt.md) | Jared | Turn a raw problem into a structured brief with pain, process, outcome, stakeholders, value |
| [feasibility](.github/prompts/feasibility.prompt.md) | Gilfoyle | Score a use case across 6 dimensions, produce a filled feasibility scorecard |
| [data-readiness](.github/prompts/data-readiness.prompt.md) | Dinesh | Assess data landscape, identify gaps, suggest simulator patterns, flag blockers |
| [demo-script](.github/prompts/demo-script.prompt.md) | Erlich | Generate a 5-section demo script from a working PoC description |

---

## 📚 Docs & Guides

| Section | What's inside |
|---------|---------------|
| [Playbook](playbook/) | Facilitation guides, ideation cheat sheet, demo crafting, checklists, atmosphere & energy |
| [Build](build/) | Architecture decisions, data, notebooks, scripts |

---

## 🎯 What You'll Walk Out With

- **Working PoCs** — not slides, code that runs
- **A rehearsed, timed demo** your customer will remember
- **A handoff doc** ([HANDOFF.md](HANDOFF.md)) with concrete next steps their boss will actually read
- **Extracted patterns** ([RETRO.md](RETRO.md)) that feed the next hackathon

