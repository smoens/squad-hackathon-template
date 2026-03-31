# Work Routing

How to decide who handles what in the hackathon squad.

## Routing Table

| Work Type | Route To | Examples |
|-----------|----------|----------|
| Engagement kickoff | Jared | "Set up a hackathon for [Company]", company research, BRIEF.md filling, hypothesis generation |
| Use case capture | Jared | Brainstorm facilitation, "let's brainstorm", use case prioritization, scope gates |
| Technical feasibility | Gilfoyle | Architecture sketch, build/no-build evaluation, tech stack decisions |
| PoC building | Richard | Notebook execution, pipeline development, integration code |
| Data work | Dinesh | Data sourcing, cleaning, simulators, schema design, sample generation |
| Demo / pitch | Erlich | Pitch deck, demo narrative, storytelling, presentation coaching, dry-runs |
| Session logging | Scribe | Automatic — never needs routing |
| Work monitoring | Ralph | Continuous — monitors queue, triage, dispatch |
| Customer meeting prep | Jared → Gilfoyle + Erlich | Jared coordinates, Gilfoyle provides tech depth, Erlich prepares narrative |

## Issue Routing

| Label | Action | Who |
|-------|--------|-----|
| `squad` | Triage: analyze issue, assign `squad:{member}` label | Jared |
| `squad:jared` | Facilitation, scoping, use case capture | Jared |
| `squad:gilfoyle` | Architecture, feasibility, tech decisions | Gilfoyle |
| `squad:richard` | PoC code, notebooks, pipelines, integrations | Richard |
| `squad:dinesh` | Data sourcing, cleaning, simulators, unblocking | Dinesh |
| `squad:erlich` | Demo, pitch, narrative, presentation | Erlich |
| `squad:copilot` | Single-file fixes, boilerplate, tests, docs | @copilot |

### How Issue Assignment Works

1. When a GitHub issue gets the `squad` label, **Jared** triages it — analyzing content, assigning the right `squad:{member}` label.
2. When a `squad:{member}` label is applied, that member picks up the issue.
3. Members can reassign by removing their label and adding another member's label.
4. The `squad` label is the "inbox" — untriaged issues waiting for Jared's review.

## Multi-Agent Routing Patterns

### Stage-Specific Patterns

| Stage | Agents | Pattern |
|-------|--------|---------|
| **Formation** | Jared + Gilfoyle + Dinesh | Jared scopes, Gilfoyle assesses feasibility, Dinesh stages data |
| **Ideation** | Jared + Gilfoyle | Jared facilitates brainstorm, Gilfoyle scores feasibility per use case |
| **Build** | Richard + Dinesh + Gilfoyle | Richard builds, Dinesh unblocks data, Gilfoyle reviews architecture |
| **Demo Prep** | Erlich + Richard | Erlich crafts narrative, Richard ensures demo stability |
| **Wind-Down** | Jared + Scribe | Jared facilitates retro, Scribe compiles summary for HQ |

### Cross-Cutting Patterns

| Scenario | Agents | Pattern |
|----------|--------|---------|
| Use case → PoC handoff | Jared → Gilfoyle → Richard | Jared captures scope, Gilfoyle sketches arch, Richard builds |
| Data blocker during build | Richard → Dinesh | Richard flags blocker, Dinesh unblocks with simulator or alternative source |
| Architecture pivot | Gilfoyle → Richard + Dinesh | Gilfoyle calls pivot, Richard adjusts code, Dinesh adjusts data |
| Demo narrative from PoC | Richard → Erlich | Richard provides PoC walkthrough, Erlich frames story |
| Knowledge extraction | Scribe + Jared | Scribe captures, Jared validates for HQ sync |

## Rules

1. **Eager by default** — spawn agents who could usefully start work, including anticipatory downstream.
2. **Scribe always runs** after substantial work, always as `mode: "background"`. Never blocks.
3. **Quick facts → coordinator answers directly.** Don't spawn an agent for status checks.
4. **Time-boxing is law** — Jared's time-box decisions override all other routing. When time is called, current stage wraps.
5. **Build and Data are a pair** — Richard and Dinesh work in tight loops. Route data blockers to Dinesh immediately.
6. **Demo prep starts early** — Erlich should be briefed on PoC direction by midday of the build phase.
7. **Issue-labeled work** — when a `squad:{member}` label is applied, route to that member.
8. **Escalation rules apply.** Check team.md escalation rules before any autonomous action.
