← [Docs](../index.md) | [Principles](./)

# Scope Management

Scope creep is the number one hackathon killer. Not bad data, not broken environments, not weak ideas — scope. A team that tries to build too much ends up demoing nothing well.

---

## Philosophy

**A hackathon demo is not a product. It's a proof of possibility.**

You're not building something that ships on Monday. You're building something that makes a customer say: *"If you can do this in a day, imagine what we could do in a quarter."*

That reframe changes everything about scope. You don't need error handling. You don't need authentication. You don't need to handle edge cases. You need one golden path that tells a clear story.

---

## The "Demo-able Slice" Principle

Every use case has a **demo-able slice** — the smallest thing you can build that proves the value proposition. Finding it is the most important architectural decision in a hackathon.

### How to Find It

Ask three questions:

1. **What's the one thing this needs to do to be convincing?**
   Not everything. The one thing.

2. **What data do we need to show that one thing?**
   Not all the data. The minimum viable dataset.

3. **Can we get from input to output in under 4 hours of build time?**
   If no, you haven't sliced thin enough.

### Examples

| Use case | Full vision | Demo-able slice |
|----------|------------|----------------|
| Predictive maintenance | End-to-end ML pipeline with real-time alerting | One model, one machine type, show the prediction vs. actual on a chart |
| Document processing | Auto-classify, extract, validate across 50 document types | Classify 3 document types, extract key fields from one, show accuracy |
| Demand forecasting | Multi-SKU, multi-store, with promotion effects | One product category, one store, 30-day forecast vs. actuals |

> **Tip:** The Use Case Canvas has a "Demo-able Slice" section for a reason. Fill it out during ideation, not during build.

---

## Scope Gates

Scope decisions happen at three checkpoints during a hackathon:

### Gate 1: End of Ideation

**Who decides:** Facilitator + Architect + Customer
**Based on:** Feasibility scores
**Decision:** Which use cases to build, and what the demo-able slice is for each

| Feasibility score | Scope decision |
|:-----------------:|---------------|
| 🟢 6–8 | Build the full demo-able slice |
| 🟡 9–12 | Narrow to the thinnest slice; acknowledge limitations upfront |
| 🟠 13–15 | Only build if customer insists and you can define a 2-hour version |
| 🔴 16–18 | Redirect to a different approach — don't build |

### Gate 2: Build Checkpoint (25% mark)

**Who decides:** Architect + Builder
**Based on:** What's actually working
**Decision:** Continue, pivot, or cut

| Signal | Response |
|--------|----------|
| Data is flowing, core logic works | Continue — you're on track |
| Data is available but the approach isn't working | Pivot — simplify the approach, keep the use case |
| Data isn't available or accessible | Cut — redirect the team to another use case |

### Gate 3: Build Checkpoint (75% mark)

**Who decides:** Facilitator (with Architect input)
**Based on:** Is this demo-able?
**Decision:** Polish or cut

| Signal | Response |
|--------|----------|
| Core demo path works end-to-end | Stop building features, start demo prep |
| It mostly works but has gaps | Use static data or screenshots to bridge the gaps |
| It doesn't work | Cut the use case — better to demo 2 things than fumble 3 |

---

## How to Cut Scope Without Losing Customer Confidence

Cutting scope feels uncomfortable, especially in front of a customer. Here's how to do it well:

### Frame it as prioritization, not failure

**Bad:** *"We couldn't get this one to work, so we're dropping it."*
**Good:** *"We're focusing our remaining time on the two use cases with the strongest results so far. We'll document what we learned on the third one for the follow-up."*

### Show your work

- Document what you attempted in the use case folder
- Include a "what we'd need to continue" section
- This shows professionalism, not failure

### Redirect, don't just cut

- If a use case gets cut, reassign the team members to strengthen the remaining demos
- The customer sees a stronger outcome, not a gap

### Use the Feasibility Scorecard as your evidence

Point to the scores: *"When we scored this at 14, we flagged it as a stretch. After building for 3 hours, we've confirmed that assessment — the data integration complexity is higher than expected. Here's what we'd recommend for a follow-up engagement."*

---

## The Feasibility Scorecard as Scope Management Tool

The [Feasibility Scorecard](../../templates/feasibility-scorecard.md) isn't just for ideation — it's your scope management reference throughout the hackathon.

| When | How to use it |
|------|--------------|
| **Ideation** | Score each use case to decide what to build |
| **Build checkpoint (25%)** | Re-score the dimensions where reality is different from the estimate |
| **Build checkpoint (75%)** | Check whether the original assessment bands still hold |
| **Demo prep** | Use the scores to frame the narrative — *"Despite a yellow on data quality, we achieved..."* |

> **Tip:** A use case that starts 🟢 and slides to 🟡 during build is normal. A use case that starts 🟡 and slides to 🔴 should be cut immediately — don't spend good hours chasing bad scores.

---

## Scope Anti-Patterns

| Anti-pattern | What it looks like | Why it kills demos |
|-------------|-------------------|-------------------|
| **Feature creep** | *"What if we also add..."* during build | New features don't get tested; core path gets fragile |
| **Perfectionism** | Polishing code instead of building the demo path | Nobody sees your clean code in the demo — they see the output |
| **Integration obsession** | Trying to connect all the real systems | One flaky API call can block an entire demo |
| **Data completeness** | Waiting for "all" the data before building | Use a sample. 100 rows that work beats 1M rows you can't access |
| **Scope-by-committee** | Everyone adds their favorite feature | The facilitator owns scope — not a vote |

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Feasibility Scorecard](../../templates/feasibility-scorecard.md) | Scoring framework that drives scope decisions |
| [Use Case Canvas](../../templates/use-case-canvas.md) | Where the demo-able slice gets defined |
| [Time-Boxing](time-boxing.md) | Time constraints enforce scope discipline |
| [Customer First](customer-first.md) | Scope decisions should serve the customer's goals |
| [Running Ideation](../guides/running-ideation.md) | Where initial scope gets set |
