← [README](../README.md)

# Logs

Runtime logs and decision history captured during the hackathon.

---

## Contents

| Path | Purpose |
|------|---------|
| [`daily-sitrep/`](daily-sitrep/) | Daily status reports — one per day of engagement |
| [`scribe-notes/`](scribe-notes/) | Session-by-session scribe notes — detailed decisions and discussions |
| [`decisions.md`](decisions.md) | Running log of all architecture and scope decisions |

## Daily Status Reports (SITREPs)

Each day, a brief status report is created in `daily-sitrep/`:

- What was accomplished
- What's planned for tomorrow
- Blockers and risks
- Key decisions made

These feed directly into [`RETRO.md`](../RETRO.md) for the retrospective.

## Scribe Notes

During each work session, detailed notes are captured in `scribe-notes/`:

- Attendees and topics discussed
- Decisions made (linked to architecture ADRs)
- Action items with owners
- Questions deferred to next sync

Scribe notes preserve the **reasoning** behind decisions — why we chose A over B, what trade-offs we accepted.

## Running Decision Log

[`decisions.md`](decisions.md) is a **chronological list** of all decisions made during the engagement. Quick reference during the hackathon; summarized in [`HANDOFF.md`](../HANDOFF.md) afterward.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [RETRO.md](../RETRO.md) | Post-engagement retrospective (fed by these logs) |
| [architecture/](../architecture/) | Formal architecture decision records |
| [.hackathon/](../.hackathon/) | Configuration and phase checklists |
