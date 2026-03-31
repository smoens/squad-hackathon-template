<div align="center">

# ⚡ Hackathon Squad

> **Two days. One squad. Real customer problems. Live demos that actually work.**  

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
| **1** | Kick off | Tell Jared your company name: *"Jared, let's set up a hackathon for Contoso"* — he'll research the customer, fill your brief, and generate conversation starters |
| **2** | Ideate | *"Jared, let's brainstorm"* — he'll facilitate use case ideation, score feasibility, and help you pick what to build |
| **3** | Build + Demo | The squad takes it from here — Gilfoyle architects, Richard builds, Dinesh wrangles data, Erlich crafts the demo |
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

> **Just talk to them.** Say *"Jared, let's kick off ideation for Contoso"* and he'll facilitate the session — researching the customer, brainstorming use cases, scoring feasibility, and walking you through the process conversationally. No prompt files needed. The squad works best when you talk to them like teammates.

---

## 🧠 Skills

The squad carries learned knowledge as **skills** — reusable patterns that make every hackathon sharper than the last.

| Skill | What it teaches the squad |
|-------|--------------------------|
| [Hackathon Facilitation](.squad/skills/hackathon-facilitation/SKILL.md) | Phase gates, time-boxing, scope management, handoff structure |
| [Industry Tailoring](.squad/skills/industry-tailoring/SKILL.md) | Per-industry pain points, data patterns, accelerator matching |
| [Engagement Kickstart](.squad/skills/engagement-kickstart/SKILL.md) | Auto-setup from company name — research, BRIEF.md fill, hypothesis generation |
| [Energy & Atmosphere](.squad/skills/energy-and-atmosphere/SKILL.md) | Energy arc design, walk-on music, awards ceremony, designed moments |
| [Demo Storytelling](.squad/skills/demo-storytelling/SKILL.md) | 5-beat narrative arc, audience psychology, rehearsal protocols |
| [Data Simulation](.squad/skills/data-simulation/SKILL.md) | Per-industry synthetic data patterns, generation tools, volume guidelines |
| [Ideation Techniques](.squad/skills/ideation-techniques/SKILL.md) | What-If card deck, facilitation patterns, prioritization methods |

Skills are read automatically by agents when relevant — you don't need to invoke them manually.

---

## 💬 How to Work With The Squad

> **Talk to agents directly.** The best way to run a hackathon is to have a conversation — not run prompts. Tell Jared your company name and he'll take it from there.

### Conversational (recommended)

| What you want | Say this |
|---------------|----------|
| Kick off a new engagement | *"Jared, let's set up a hackathon for Contoso — they're in manufacturing"* |
| Brainstorm use cases | *"Jared, let's brainstorm — what could we build for them?"* |
| Score a use case | *"Gilfoyle, is predictive maintenance feasible in a 2-day hackathon?"* |
| Get data flowing | *"Dinesh, we need synthetic sensor data — 10K rows, time-series"* |
| Write a demo script | *"Erlich, draft a demo for the anomaly detection PoC"* |
| Build a PoC | *"Richard, build a notebook that ingests from CSV and writes to Lakehouse"* |

### Prompts (shortcuts)

For specific structured outputs, prompts in `.github/prompts/` give you a one-shot result:

| Prompt | Agent | What it does |
|--------|-------|-------------|
| [kickstart](.github/prompts/kickstart.prompt.md) | Jared | Research a customer, auto-fill BRIEF.md, generate "What if..." starters |
| [ideation](.github/prompts/ideation.prompt.md) | Jared | Generate use case canvases + feasibility scores from a brief |
| [use-case-brief](.github/prompts/use-case-brief.prompt.md) | Jared | Turn a raw problem into a structured brief |
| [feasibility](.github/prompts/feasibility.prompt.md) | Gilfoyle | Score a use case across 6 dimensions |
| [data-readiness](.github/prompts/data-readiness.prompt.md) | Dinesh | Assess data landscape, identify gaps, suggest simulators |
| [demo-script](.github/prompts/demo-script.prompt.md) | Erlich | Generate a 5-section demo script from a working PoC |

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

