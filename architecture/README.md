← [README](../README.md)

# Architecture Decision Records

This directory holds **Architecture Decision Records (ADRs)** — decisions made about technology, patterns, and system design during the hackathon engagement.

---

## Contents

| Path | Purpose |
|------|---------|
| [`decisions/`](decisions/) | Individual ADR documents |
| [`decisions/_template.md`](decisions/_template.md) | ADR template — copy this to create new records |

## How ADRs Work

Each ADR captures:

| Field | What it records |
|-------|----------------|
| **Short title** | What decision was made? |
| **Use case** | Which use case triggered this? |
| **Decision** | What did we choose and why? |
| **Trade-off** | What did we give up? |
| **Revisit flag** | Should this be reconsidered post-hackathon? |

ADRs are **living documents** — they document the thinking at the time, not gospel. Update them if circumstances change during the hackathon.

## During the Hackathon

Create a new ADR whenever the team faces a significant design choice:

- Technology selection (e.g., "Use Azure Synapse vs. Fabric")
- Architecture pattern (e.g., "Streaming vs. batch processing")
- Scope boundary (e.g., "Real-time vs. daily updates")

Reference the [`_template.md`](decisions/_template.md) — copy, fill in, commit.

## After the Hackathon

All ADRs are **summarized in [`HANDOFF.md`](../HANDOFF.md)** for the customer. This ensures decisions are visible and defensible.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [HANDOFF.md](../HANDOFF.md) | Architecture decisions summary for customer |
| [log/decisions.md](../log/decisions.md) | Running decision log |
| [docs/guides/](../docs/guides/) | Implementation guides |
