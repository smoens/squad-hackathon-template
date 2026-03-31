# Demo Storytelling

Narrative patterns for hackathon demos that move audiences — from script structure to presenter coaching, audience psychology, and backup strategies.

## When to Use This Skill

- Crafting demo scripts for hackathon presentations
- Coaching presenters on narrative structure
- Designing demo flow and transitions
- Preparing backup strategies for flaky demos
- Rehearsing and refining demo delivery

---

## The 5-Beat Arc

Every hackathon demo follows this arc. No exceptions. Each beat has a purpose and an emotional target.

### Beat Structure

| Beat | Duration | Purpose | Emotional Target | Audience Thinking |
|------|----------|---------|------------------|-------------------|
| 1. The Problem | 60-90 sec | Make the audience FEEL the pain | Frustration, recognition | "Yes, that's exactly our problem" |
| 2. The Solution | 45-60 sec | Show the idea that changes everything | Curiosity, hope | "Wait, you can do that?" |
| 3. The Live Demo | 2-3 min | Prove it works — with their data, their world | Awe, excitement | "Holy sh*t, it actually works" |
| 4. The Impact | 45-60 sec | Translate to business value they care about | Confidence, ambition | "This could save us millions / change everything" |
| 5. The Ask | 30-45 sec | Tell them what happens next | Commitment, action | "I want to make this happen" |

### Total: 5-7 minutes per use case

**The rule:** If you can't fit it in 7 minutes, you're showing too much. Cut features, not the arc.

---

## Beat-by-Beat Playbook

### Beat 1: The Problem (60-90 seconds)

**Goal:** Make the audience recognize their own pain.

**Techniques:**
- **Name a real person.** "Maria, your plant supervisor in Munich, starts every Monday by..."
- **Use their language.** Quote words from customer discovery conversations.
- **Show the messy reality.** Screenshot of the actual spreadsheet, the email chain, the manual process.
- **Quantify the cost.** "This process takes 47 people 3 full days every month."
- **Ask a rhetorical question.** "What if Maria never had to do this again?"

**Template:**

> "Right now, [named role] at [company] spends [time/effort] doing [painful process]. 
> They're using [current approach — make it sound painful]. Last year, this cost 
> [department] [quantified impact]. And here's the thing — [why it's getting worse, 
> not better]."

**Anti-pattern:** Don't start with technology. "We built a machine learning model that..." — NO. Start with the human.

### Beat 2: The Solution (45-60 seconds)

**Goal:** Bridge from pain to possibility — but don't show it yet.

**Techniques:**
- **One sentence that flips the script.** "What if [role] could [transformed capability] in [dramatically less time]?"
- **Architecture in one breath.** "We connected [data source] to [AI/analytics], and now [outcome]." Show one simple diagram if needed — 3-4 boxes max.
- **No feature lists.** This is the concept, not the spec.
- **Create anticipation.** "Let me show you what this looks like."

**Template:**

> "We built [solution name — make it sound real, not academic]. It takes [data input], 
> runs it through [simple description of the magic], and gives [role] [transformed output] 
> in [impressively short time]. Let me show you."

### Beat 3: The Live Demo (2-3 minutes)

**Goal:** Show it working. For real. With data that looks like theirs.

**Techniques:**
- **Start from the user's perspective.** Open the interface THEY would see. Not Azure Portal.
- **Narrate every click.** "Maria opens her dashboard Monday morning and sees..."
- **Pause on the magic moment.** When the AI prediction appears, when the insight surfaces — PAUSE. Let it land.
- **Use realistic data.** Simulated data should have their column names, their product SKUs, their geography.
- **Show, don't tell.** If it predicts a failure, SHOW the prediction. If it generates a report, SHOW the report.

**Demo flow:**

```
1. Start at the user's entry point (dashboard, app, notification)
2. Show the trigger (new data arrives, user asks a question, alert fires)
3. Show the processing (briefly — "behind the scenes, Azure is...")
4. Reveal the output (THE moment — dwell here)
5. Show the action enabled ("and now Maria can [do the thing]")
```

**The "silence trick":** After the key output appears on screen, stop talking for 3 seconds. Let the audience read it and react. Silence is louder than narration at the peak.

### Beat 4: The Impact (45-60 seconds)

**Goal:** Connect the demo to money, time, risk, or competitive advantage.

**Techniques:**
- **Concrete numbers.** "This reduces [process] from 3 days to 15 minutes."
- **Annual projection.** "Across your 12 plants, that's [X hours / $Y / Z incidents] per year."
- **Comparison.** "Today this takes a team of 5. With this, it takes one person checking a dashboard."
- **Risk reduction.** "You catch the quality issue BEFORE it ships, not after the recall."
- **Understated confidence.** Don't oversell. "These are conservative estimates based on the sample data. With your real data, the impact is likely higher."

**Template:**

> "In our simulation with [X records of your data], this caught [Y outcomes] that 
> your current process misses. Across [scale of their operation], that translates 
> to [quantified impact]. And this was built in [hours in hackathon] — imagine 
> what a production version could do."

### Beat 5: The Ask (30-45 seconds)

**Goal:** Convert excitement into a concrete next step.

**Concrete asks (GOOD):**

| Ask Type | Example |
|----------|---------|
| Proof of Concept | "We'd like 4 weeks with your real data to build a production-ready PoC." |
| Architecture Review | "Let's schedule a deep-dive with your data engineering team next week." |
| Data Access | "To prove this at scale, we need access to [specific data source]. Can we set that up?" |
| Executive Brief | "Can we present this to [VP/CTO] with a business case?" |
| Pilot Commitment | "We propose a 90-day pilot in your [specific plant/region/team]." |

**Vague asks (BAD):**

| Vague Ask | Why It Fails |
|-----------|-------------|
| "Let us know if you're interested" | No commitment, easily forgotten |
| "We could do more with this" | Not actionable |
| "Next steps TBD" | Momentum dies |
| "We'll send you a follow-up" | Passive, no customer action required |

**Template:**

> "Here's what we recommend as a next step: [specific, time-bound ask with a named 
> deliverable]. We can have [concrete output] ready by [date]. The first thing we'd 
> need from you is [specific customer action]."

---

## Audience Psychology

### Two Audiences, One Demo

Every hackathon demo room has two audiences with different needs:

| Audience | They Care About | Convince Them With |
|----------|----------------|-------------------|
| Decision-makers (VP, Director, CxO) | Money saved, risk reduced, competitive advantage, speed to value | Impact numbers, ROI projections, "imagine at scale" framing |
| Technical staff (engineers, data scientists, architects) | How it works, will it scale, is it real, can they maintain it | Architecture clarity, honest limitations, "we used [service] because [reason]" |

**How to serve both:**
- Lead with the business narrative (Beats 1-2) — hooks decision-makers
- Demo serves both — visual for executives, technology for engineers
- Impact beat (4) — split a sentence: business impact + technical feasibility
- Q&A — let questions reveal which audience wants more

### Decision Psychology

| Principle | How to Use It |
|-----------|---------------|
| Loss aversion | Frame the cost of NOT acting: "Every month without this, you're losing..." |
| Social proof | "We've seen [similar company] get [result] with this approach" |
| Anchoring | State the big number first, then the achievable next step |
| Concreteness | Named people, specific data, real screenshots > abstract concepts |
| Urgency | "Your data is already generating these signals — you're just not seeing them yet" |

---

## Demo Anti-Patterns

| Anti-Pattern | What It Looks Like | Fix |
|--------------|-------------------|-----|
| **Feature tour** | "And then you can click here, and here's another feature, and over here..." | Pick ONE user journey. Show it end-to-end. |
| **Apology-driven demo** | "Sorry, this is just a prototype... ignore the UI... this part doesn't work yet..." | Own it: "We built this in 8 hours. Here's what it does." Confidence, not apology. |
| **Technology-first** | "We used Azure Machine Learning with a gradient-boosted model and..." | Start with the problem. Technology is mentioned in Beat 2, briefly. |
| **No-story demo** | Opens a dashboard, clicks around, no narrative thread | Write a script. Rehearse it. Every click has a sentence. |
| **Demo-ALL-the-things** | Shows 5 use cases in 10 minutes, none land | Pick 2-3 max. Depth beats breadth. |
| **Death by architecture slide** | 15-box architecture diagram before any demo | One diagram, 3-4 boxes max, 20 seconds. Then SHOW the thing. |
| **The never-ending demo** | Goes 15+ minutes, audience checks out | Hard cap: 7 min per use case. Rehearse with a timer. |

---

## The Walk-On Ritual

The 30 seconds before a demo starts are critical. They set the energy.

**Sequence:**
1. MC stands: "Next up — Team [Name]!" (Read the 1-line teaser from the progress wall)
2. Walk-on music plays (10-15 seconds)
3. Team takes position (standing, not sitting)
4. Music fades
5. Lead presenter: opening line of Beat 1 (the hook — rehearsed to be punchy)

**Walk-on music options:** Team choice, or assign if they don't choose. Upbeat, recognizable, 10-15 seconds. Fade out, don't cut abruptly.

**Why it matters:** The walk-on creates a micro-moment of excitement. It signals "this is a performance, not a status update." Audiences literally pay more attention after a walk-on.

---

## Backup Strategies

Demos fail. Plan for it.

### Backup Tier System

| Tier | When to Use | What to Prepare |
|------|------------|-----------------|
| **Tier 1: Live demo** | Everything works | Rehearsed live demo with real flow |
| **Tier 2: Guided screenshots** | Demo works but environment is flaky | Full screenshot walkthrough with annotations |
| **Tier 3: Recorded video** | Risk of live failure is high | Pre-recorded 2-min video of the demo working |
| **Tier 4: Architecture + narrative** | Demo completely broken | Architecture diagram + "here's what it would show" walkthrough |

**Rules:**
- ALWAYS prepare Tier 2 screenshots even if you expect Tier 1 to work
- Record a Tier 3 video during rehearsal as insurance
- Tier 4 is a last resort — but a confident Tier 4 beats a crashing Tier 1

### The Graceful Recovery Script

When a demo crashes mid-presentation:

> "[Pause — don't panic] So that's live software for you. [light laugh] 
> Let me show you what this produces — [switch to screenshots]. As you can 
> see, the output looks like this... [continue the narrative without apology]."

**The key:** Switch to backup WITHOUT extended apology. One sentence acknowledgment, then move on. The audience forgets the crash if the story is good.

---

## Rehearsal Protocol

### Minimum Rehearsal Schedule

| Timing | Activity | Focus |
|--------|----------|-------|
| Demo -3 hours | Script complete | Full narrative written and reviewed |
| Demo -2 hours | Dry-run #1 | Full run-through with timer. Identify breaks. |
| Demo -1 hour | Fix round | Fix issues found in dry-run #1 |
| Demo -45 min | Dry-run #2 | Final run-through. No changes after this. |
| Demo -15 min | Tech check | Screen sharing works, backup screenshots ready, audio works |

### Dry-Run Feedback Checklist

| Question | Desired Answer |
|----------|---------------|
| Can a non-technical person follow the story? | Yes |
| Is there a clear "wow" moment? | Yes — and we paused on it |
| Did we stay under time? | Yes — 30 sec buffer minimum |
| Do we have a concrete Ask? | Yes — specific and time-bound |
| Is the backup ready? | Screenshots captured, video recorded |
