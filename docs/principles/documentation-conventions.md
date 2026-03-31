← [Docs](../index.md) | [Principles](./)

# Documentation Conventions

Our docs are our knowledge memory. They need to be findable, scannable, and trustworthy. This guide covers **how we write, structure, and format** so every document in `/docs` follows the same patterns.

**Scope:** Applies to concept, guide, and principle documents in `/docs`.

---

## The Three Doc Types

Every document in `/docs` serves one purpose:

| Type | Purpose | Answers | Tone | Length |
|------|---------|---------|------|--------|
| **Concept** | Mental models and principles | *"Why do we do it this way?"* | Educational, conversational | 50–150 lines |
| **Guide** | Step-by-step instructions | *"How do I do this?"* | Practical, direct, task-focused | 80–200 lines |
| **Principle** | Agreements and ground rules | *"What's the rule here?"* | Authoritative, clear | 50–150 lines |

### When to write each type

- **Concept:** You've done something 3 times and realized there's a principle behind it
- **Guide:** Someone asked you how to do something; you wrote it out; now write it down
- **Principle:** The squad has agreed on something and it needs to be binding

---

## File Naming

Use **kebab-case, descriptive, no dates, no versions.**

| Pattern | Good | Bad |
|---------|------|-----|
| kebab-case | `running-ideation.md` | `runningIdeation.md`, `Running_Ideation.md` |
| Descriptive | `customer-engagement-checklist.md` | `checklist.md` |
| No dates | `running-your-first-hackathon.md` | `hackathon-2025-03-31.md` |
| No versions | `facilitator-guide.md` | `facilitator-guide-v2.md` |

The filename should work 2 years from now without feeling stale.

---

## Breadcrumb Navigation

**Every document starts with a breadcrumb line.**

| Section | Format |
|---------|--------|
| Concepts | `← [Concepts](./) \| ← [README](../../README.md)` |
| Guides | `← [Docs](../index.md) \| [Guides](./)` |
| Principles | `← [Docs](../index.md) \| [Principles](./)` |

This lets readers navigate back without using the browser back button.

---

## Title & Intro

After breadcrumb, leave a blank line, then:

```markdown
# Title

One-paragraph intro: what is this about? 2–3 sentences.
Include the question this doc answers and who it's for.

**Who this is for:** [audience]
**Assumes:** [prerequisites]
```

---

## Sections & Formatting

### Headers

- `# Title` — one per document
- `## Main sections` — the primary structure
- `### Subsections` — break long sections
- `####` — use sparingly

### Separators

Use `---` between major sections for visual breaks.

### Tables

Use tables for comparisons, matrices, checklists, and reference data. Align columns for readability. Use emoji sparingly but helpfully (🟢 Go, 🟡 Caution, 🔴 Stop).

### Code blocks

Always include language tag:

````markdown
```python
import pandas as pd
```
````

---

## Mermaid Diagrams

Use Mermaid for flowcharts, architecture diagrams, and process flows.

**Use when:**
- Process diagram showing stages or workflow
- Architecture diagram showing system components
- Decision tree showing conditional logic

**Don't use for:**
- Simple lists (use markdown lists)
- Simple tables (use markdown tables)
- Large entity-relationship diagrams (too complex)

Common types: `flowchart TD`, `flowchart LR`, `graph LR`.

---

## The Related Section

Every doc ends with a **📎 Related** section:

```markdown
---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Link 1](path/doc1.md) | Describes X |
| [Link 2](path/doc2.md) | Explains why we do Y |
```

Include 3–5 related docs. Use relative paths. Brief 1-line purpose.

---

## Tone & Voice

Write for **hackathon practitioners**, not academics.

| Instead of | Write |
|-----------|-------|
| *"It is recommended that one engage in..."* | *"Do this."* |
| *"The aforementioned framework facilitates..."* | *"This helps you..."* |
| Formal passive voice | Active voice |

---

## Review Checklist

Before publishing:

- [ ] Breadcrumb navigation is correct
- [ ] Title is descriptive
- [ ] Intro explains audience and prerequisites
- [ ] Section headers tell the story
- [ ] All links are relative paths and work
- [ ] Tables are aligned and scannable
- [ ] Mermaid diagrams render correctly
- [ ] Tone is practical, direct, helpful
- [ ] 📎 Related section included

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Getting Started](../guides/getting-started.md) | Example of a well-structured guide |
| [Time-Boxing](time-boxing.md) | Example of a well-structured principle |
| [Use-Case-Driven Development](../concepts/use-case-driven-development.md) | Example of a well-structured concept |
