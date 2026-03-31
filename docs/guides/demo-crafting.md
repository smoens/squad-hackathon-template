← [Docs](../index.md) | [Guides](./)

# Demo Crafting

A great PoC with a bad demo is a wasted hackathon. The demo is where value lands — it's the customer's takeaway, the thing they show their boss on Monday. This guide covers how to turn working code into a compelling story.

**Who this is for:** Demo Crafters (Erlich role), but every squad member should read this.

---

## The Demo Narrative Structure

Every hackathon demo follows the same five-beat arc. Don't reinvent it — refine it.

| Beat | Duration | Purpose | What the audience should feel |
|------|----------|---------|-------------------------------|
| **1. The Problem** | 30 sec | Frame the pain in the customer's language | *"Yes, that's exactly our problem"* |
| **2. The Solution** | 60 sec | Explain what you built and why it works | *"That's a clever approach"* |
| **3. The Live Demo** | 2–3 min | Show it working with real(ish) data | *"Wow, it actually works"* |
| **4. The Impact** | 30 sec | Quantify the value — time, money, risk | *"This could really help us"* |
| **5. The Ask** | 30 sec | Propose the next step — specific and concrete | *"Let's talk about making this happen"* |

> **Tip:** The Problem beat is the most important. If the customer doesn't recognize their pain in your framing, nothing that follows matters.

### Using the Demo Script Template

The [Demo Script Template](../../templates/demo-script-template.md) provides a fill-in-the-blank structure for each beat. Start there — don't write freestyle.

1. Copy the template into your use case directory
2. Fill in the problem statement first — get a customer nod before writing anything else
3. Map your demo steps to the table in beat 3
4. Write your impact numbers last (they often change as the PoC evolves)

---

## Writing a Compelling Demo Script

### The Problem Beat

- Use the customer's **own words** from ideation — quote them if you can
- Quantify the pain: hours, dollars, error rates
- Name a real persona: *"Maria, a plant floor supervisor, spends 8 hours a week on..."*

**Bad:** *"Manufacturing companies face quality control challenges."*
**Good:** *"Maria reviews 200 inspection photos a day by hand. She catches 85% of defects — the other 15% ship to customers."*

### The Solution Beat

- One sentence: what you built
- One diagram: how data flows (use the Mermaid template in the script)
- One insight: the key idea that makes this approach work

Keep it simple. If you can't explain the architecture in 60 seconds, you've over-built.

### The Live Demo Beat

Show, don't tell. Plan every click.

| Do | Don't |
|----|-------|
| Use realistic data (customer data or good synthetic data) | Use lorem ipsum or obviously fake data |
| Pre-load anything that takes >5 seconds | Make the audience watch a loading spinner |
| Narrate what's happening as you click | Click silently and hope people follow |
| Have a backup plan for every step | Assume the demo gods will be kind |

### The Impact Beat

- Use the metrics from the Use Case Canvas
- Compare before vs. after: *"8 hours → 20 minutes"*
- Translate to business language: *"That's $250K/year in recovered analyst time"*

### The Ask Beat

Be **specific**. Not *"we should continue this work"* but *"we need access to the production dataset and a 4-week pilot with Maria's team."*

---

## Technical Readiness Checklist

Complete this before any demo rehearsal:

- [ ] Demo environment is running and accessible
- [ ] Sample/test data is loaded and produces expected results
- [ ] All API keys, connections, and auth tokens are valid
- [ ] The demo path works end-to-end (tested within the last 2 hours)
- [ ] Backup screenshots or screen recording exists
- [ ] Internet/VPN connectivity confirmed at the demo location
- [ ] Screen resolution and font size are readable from the back of the room
- [ ] No personal data, credentials, or embarrassing browser tabs visible
- [ ] Presenter has walked through the full script at least once

> **Tip:** Test your demo on the actual machine you'll present from, connected to the actual network. *"It worked on my laptop"* is not a recovery plan.

---

## Presentation Tips

### For Customer-Facing Demos

1. **Open with their language, not yours.** If they say "predictive maintenance," don't say "ML-driven anomaly detection" until they do.
2. **Make eye contact during the Problem beat.** Look at the customer decision-makers when you describe their pain.
3. **Narrate the demo like a sports announcer.** *"I'm clicking 'Analyze' now... and in about 3 seconds you'll see the predictions load..."*
4. **Pause after the Impact beat.** Let the numbers land. Silence is powerful.
5. **End with a question, not a statement.** *"Does this direction feel right for your team?"* invites conversation.

### Timing

| Format | Demo time per use case | Total demo session |
|--------|----------------------|-------------------|
| **1-day** | 5 min + 3 min Q&A | 45–60 min |
| **2-day** | 5 min + 5 min Q&A | 60–90 min |

Rehearse to hit 4.5 minutes. You'll always run slightly over.

---

## Common Demo Failures and Recovery

| Failure | Impact | Prevention | Recovery |
|---------|--------|-----------|----------|
| **Demo environment crashes** | High — audience loses confidence | Test within 2 hours of demo; have a warm standby | Switch to backup screenshots with narration: *"Let me show you what this looks like..."* |
| **Data doesn't load** | Medium — breaks the flow | Pre-load data; cache results for the demo path | Show cached/static version: *"Here's the output from our test run this morning"* |
| **Network dies** | High — live demo impossible | Test connectivity; have offline backup | Use screen recording: *"I recorded a walkthrough earlier — let me show you"* |
| **Wrong data appears** | Medium — confuses the audience | Rehearse with production-like data | Acknowledge honestly: *"That's our test data — let me show you the actual output"* and switch to screenshots |
| **Presenter forgets the script** | Low — happens to everyone | Print the script; rehearse 3x | Pause, glance at notes, continue. The audience won't notice a 3-second pause |
| **Customer asks a hard question mid-demo** | Low — actually a good sign | Anticipate top 5 questions beforehand | *"Great question — let me finish this section and I'll come back to that in 60 seconds"* |

> **Tip:** The best recovery from any demo failure is **honesty + a backup**. Never pretend something works when it doesn't — customers see through it instantly and you lose trust.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Demo Script Template](../../templates/demo-script-template.md) | Fill-in-the-blank demo script |
| [Customer First](../principles/customer-first.md) | Why their story drives the demo |
| [Scope Management](../principles/scope-management.md) | How to cut scope and still demo well |
| [HANDOFF.md](../../HANDOFF.md) | Post-demo handoff document |
| [Wind-Down Checklist](../../.hackathon/checklist-winddown.md) | Post-hackathon wrap-up |
