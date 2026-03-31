← [Docs](../index.md) | [Guides](./)

# Getting Started

You just stamped a new repo from the hackathon template. This guide walks you from blank repo to "ready for Day 1" — covering configuration, accelerator selection, and the formation checklist.

**Who this is for:** First-time facilitators, or anyone spinning up a new engagement.

---

## Prerequisites

Before you begin, make sure you have:

| Category | What you need | Why |
|----------|--------------|-----|
| **Access** | GitHub account with repo creation rights | To stamp the template into a new repo |
| **Access** | Azure subscription (or target cloud env) | To provision hackathon infrastructure |
| **Tools** | Git CLI or GitHub Desktop | To clone and work locally |
| **Tools** | VS Code (recommended) | Templates render well, Mermaid previews work |
| **Knowledge** | Read the [README](../../README.md) | Understand the lifecycle and roles |
| **Knowledge** | Customer context | You should know who you're building for before starting |
| **Document** | Customer brief info gathered | Business context, goals, attendees, tech landscape |

---

## Step-by-Step Setup

### 1. Stamp the Template

Click **"Use this template"** on the template repo, or use the CLI:

```bash
gh repo create <org>/<customer-engagement-name> \
  --template <org>/hackathon-squad \
  --private
```

Clone it locally:

```bash
git clone https://github.com/<org>/<customer-engagement-name>.git
cd <customer-engagement-name>
```

> **Tip:** Name the repo after the engagement, not the customer alone. Something like `hackathon-contoso-predictive-maintenance` is more findable later than `contoso-hack`.

### 2. Configure BRIEF.md

Open [`BRIEF.md`](../../BRIEF.md) and fill in every `[FILL]` field. This is the single source of truth for the engagement.

Key sections to nail:

| Section | What to capture | Common mistake |
|---------|----------------|----------------|
| **Business Context** | What the customer does, market position, engagement driver | Too vague — "they want AI" isn't a context |
| **Goals** | Concrete, measurable outcomes for the hackathon | Too many goals — aim for 2-3, not 8 |
| **Attendees** | Names, roles, focus areas for both sides | Forgetting to list customer decision-makers |
| **Technical Landscape** | Current stack, data sources, access methods | Assuming you'll figure it out on Day 1 |

> **Tip:** Send the Brief to the customer sponsor for review before Day 1. Alignment here prevents surprises later.

### 3. Select an Accelerator Pack

Browse [`accelerators/`](../../accelerators/README.md) for pre-built patterns that match the customer's use cases.

1. Review available packs in the [Accelerator README](../../accelerators/README.md)
2. Add your selections to [`.hackathon/config.json`](../../.hackathon/config.json) → `accelerator_packs[]`
3. Follow the pack's own README for setup steps

No matching pack? That's fine — the template works without accelerators. You can also [create a new pack](../../accelerators/README.md#how-to-create-a-new-pack) as you go.

### 4. Prepare Use Case Hypotheses

Before ideation, document 3-5 use case hypotheses based on your customer conversations. Use the [Use Case Canvas](../../templates/use-case-canvas.md) format — even rough drafts help seed the brainstorming.

These aren't commitments. They're conversation starters.

### 5. Run the Formation Checklist

Open [`.hackathon/checklist-formation.md`](../../.hackathon/checklist-formation.md) and work through every item:

- [ ] Brief completed and reviewed
- [ ] Repo scaffolded
- [ ] Environments provisioned and tested
- [ ] Use case hypotheses documented (minimum 3)
- [ ] Accelerator packs selected and loaded
- [ ] Sample / synthetic datasets prepared
- [ ] Agenda and time-boxing plan confirmed
- [ ] Squad briefed — every member knows their role

**Don't skip "Squad briefed."** Five minutes of role clarity prevents two hours of Day 1 confusion.

### 6. Set the Agenda

Plan your time-boxes before Day 1. See [Time-Boxing](../principles/time-boxing.md) for philosophy and example schedules.

| Format | Ideation | Build | Demo Prep | Demo |
|--------|----------|-------|-----------|------|
| **1-day** | 1.5 hrs | 3.5 hrs | 1 hr | 1 hr |
| **2-day** | 2.5 hrs | 7 hrs | 1.5 hrs | 1 hr |

---

## Tips for First-Time Facilitators

1. **Over-prepare the Brief, under-prepare the solutions.** The hackathon should discover solutions, not confirm pre-built ones.
2. **Visit the room (or test the virtual setup) before Day 1.** Projector cables, whiteboard markers, Wi-Fi passwords — the mundane stuff derails mornings.
3. **Print the agenda.** Even in a digital-first world, a physical time-box schedule on the wall keeps everyone honest.
4. **Know your cut lines.** Before you start, decide what you'll drop if time runs short. See [Scope Management](../principles/scope-management.md).
5. **The customer should talk more than you in ideation.** Your job is to *extract*, not to *present*.

---

## What's Next?

| Next step | When |
|-----------|------|
| [Running Ideation](running-ideation.md) | Day 1 morning |
| [Demo Crafting](demo-crafting.md) | After build phase |
| [Industry Customization](industry-customization.md) | During formation, if needed |

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [BRIEF.md](../../BRIEF.md) | Customer engagement brief |
| [Formation Checklist](../../.hackathon/checklist-formation.md) | Pre-hackathon readiness checklist |
| [Accelerator Packs](../../accelerators/README.md) | Tech-specific modules |
| [Time-Boxing](../principles/time-boxing.md) | How to plan your schedule |
