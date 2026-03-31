# Demo Crafting

A great PoC with a bad demo is a wasted hackathon. The demo is where value lands — it's what the customer shows their boss on Monday.

---

## The 5-Beat Arc

Every hackathon demo follows this structure. Don't reinvent it — refine it.

| Beat | Time | Purpose | Audience should feel |
|------|------|---------|---------------------|
| **1. The Problem** | 30 sec | Frame the pain in the customer's language | *"Yes — that's exactly our problem"* |
| **2. The Solution** | 60 sec | Explain what you built and why it works | *"That's a clever approach"* |
| **3. The Live Demo** | 2-3 min | Show it working with real(ish) data | *"Wow, it actually works"* |
| **4. The Impact** | 30 sec | Quantify the value — time, money, risk | *"This could really help us"* |
| **5. The Ask** | 30 sec | Propose a specific next step | *"Let's talk about making this happen"* |

**The Problem beat is the most important.** If the customer doesn't recognize their pain in your framing, nothing that follows matters.

### Beat tips

- **Problem:** Use the customer's own words from ideation. Quote them. Name a real persona: *"Maria, a plant floor supervisor, spends 8 hours a week on..."*
- **Solution:** One sentence for what you built. One diagram for how data flows. If you can't explain the architecture in 60 seconds, you've over-built.
- **Live Demo:** Show, don't tell. Plan every click. Pre-load anything that takes >5 seconds. Narrate like a sports announcer: *"I'm clicking 'Analyze' now... in about 3 seconds you'll see the predictions load..."*
- **Impact:** Before vs. after: *"8 hours → 20 minutes. That's $250K/year in recovered analyst time."* Let the numbers land. Pause. Silence is powerful.
- **The Ask:** Be specific. Not *"we should continue this work"* but *"we need access to the production dataset and a 4-week pilot with Maria's team."*

---

## Demo Show Format

### MC Introduction
The facilitator introduces each demo: team name, one-sentence problem statement, and the presenters. Keep it to 15 seconds.

### Walk-On Energy
Presenters stand, make eye contact, own the room. Open with the customer's language, not yours. If they say "predictive maintenance," don't say "ML-driven anomaly detection" until they do.

### Audience Engagement
- Make eye contact during the Problem beat — look at the decision-makers
- End with a question, not a statement: *"Does this direction feel right for your team?"*
- Pause after Impact. Let the numbers breathe.

### Timing

| Format | Demo time per use case | Total demo session |
|--------|----------------------|-------------------|
| **1-day** | 5 min + 3 min Q&A | 45–60 min |
| **2-day** | 5 min + 5 min Q&A | 60–90 min |

Rehearse to hit **4.5 minutes**. You'll always run slightly over.

---

## Writing the Script

Use the [Demo Script Template](demo-script-template.md) — don't write freestyle.

1. Copy the template into your use case directory
2. Fill in the Problem statement first — get a customer nod before writing anything else
3. Map your demo steps to the live demo table (every click, every screen)
4. Write Impact numbers last (they change as the PoC evolves)
5. Draft The Ask with the facilitator — make it specific and actionable

---

## Rehearsal

**One full timed run is mandatory.** No exceptions.

### Rehearsal checklist
- [ ] Demo environment running and accessible
- [ ] Sample data loaded and producing expected results
- [ ] All API keys, connections, auth tokens valid
- [ ] Demo path works end-to-end (tested within last 2 hours)
- [ ] Backup screenshots or screen recording captured
- [ ] Internet/VPN connectivity confirmed at demo location
- [ ] Font size readable from the back of the room
- [ ] No personal data, credentials, or embarrassing browser tabs visible
- [ ] Full script walked through at least once, timed

> **Test on the actual machine you'll present from, on the actual network.** *"It worked on my laptop"* is not a recovery plan.

---

## Backup Plan

Every demo needs a fallback. Plan before you need it.

| Failure | Prevention | Recovery |
|---------|-----------|----------|
| **Environment crashes** | Test within 2 hours of demo; warm standby | Switch to backup screenshots: *"Let me show you what this looks like..."* |
| **Data doesn't load** | Pre-load and cache results for demo path | Show cached output: *"Here's the output from our test run this morning"* |
| **Network dies** | Test connectivity; have offline backup | Use pre-recorded screen capture |
| **Wrong data appears** | Rehearse with production-like data | Acknowledge honestly, switch to screenshots |
| **Presenter forgets script** | Print the script; rehearse 3x | Pause 3 seconds, glance at notes, continue. Nobody notices. |

**The best recovery from any failure:** honesty + a backup. Never pretend something works when it doesn't — customers see through it instantly.

---

## Anti-Patterns

### 🚫 The Feature Tour
*"And then you can also click here, and here, and here..."*
**Fix:** Tell a story, not a feature list. One user, one journey, one outcome.

### 🚫 The Apology Demo
*"This isn't quite working yet, but imagine..."*
**Fix:** Demo what works. Cut what doesn't. A smaller working demo beats a bigger broken one.

### 🚫 The No-Story Demo
*[Opens notebook, runs cells, shows output]*
**Fix:** Lead with the Problem beat. Without the customer's pain as context, raw output is meaningless.

### 🚫 The Overtime Demo
*"Just one more thing..."*
**Fix:** Rehearse to 4.5 minutes. The facilitator holds a hard 5-minute stop. Respect the clock — the audience's attention is a gift.

### 🚫 The Tech-First Demo
*"We used a transformer-based architecture with fine-tuned embeddings..."*
**Fix:** Lead with business outcomes. Tech details go in the Q&A.
