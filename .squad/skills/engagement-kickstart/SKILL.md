# Engagement Kickstart

Auto-setup assistance for new hackathon engagements — company research, brief pre-fill, use case hypothesis generation, and accelerator matching.

## When to Use This Skill

- User stamps the hackathon template for a new engagement
- User mentions a customer or company name
- Quick-starting a hackathon with minimal input
- Pre-populating `BRIEF.md` engagement details and `.hackathon/config.json`
- Generating initial use case hypotheses for a customer conversation
- Selecting relevant accelerator packs

---

## The Kickstart Flow

### Minimum Input Required

| Input | Required | Notes |
|-------|----------|-------|
| Company name | **Yes** | Exact legal or trade name |
| Industry | Preferred | Auto-detected if omitted, but confirm with user |
| Engagement date(s) | Optional | Can be filled later |
| Customer contacts | Optional | Can be filled later |
| Specific pain points mentioned | Optional | Dramatically improves hypothesis quality |

### Step 1: Intake

User provides company name (+ optional industry, pain points, context). Even a Slack message like "We have a hackathon with Contoso next month, they're in manufacturing" is enough to trigger.

### Step 2: Company Research

Research the company systematically. Gather enough to pre-fill the brief and generate informed hypotheses.

**Research checklist:**

| Research Area | Sources | What to Capture |
|---------------|---------|-----------------|
| Company overview | Website, Wikipedia, LinkedIn | Size, HQ, revenue range, employee count, public/private |
| Industry segment | Company website, analyst reports | Primary industry, sub-segment, positioning |
| Key challenges | Press releases, earnings calls, industry reports | Top 3-5 business challenges relevant to data/AI |
| Data landscape | Job postings, tech blogs, case studies | Known tech stack, data platforms, cloud footprint |
| Competitors | Industry publications | Top 3 competitors (helps frame differentiation use cases) |
| Recent initiatives | Press releases, news | Digital transformation programs, recent tech investments |
| Regulatory context | Industry knowledge | Compliance requirements that constrain solutions (GDPR, HIPAA, etc.) |

**Research confidence levels:**

| Level | Meaning | Action |
|-------|---------|--------|
| 🟢 Confirmed | Found in official sources | Use directly |
| 🟡 Inferred | Reasonable assumption from indirect evidence | Mark as assumption in brief |
| 🔴 Unknown | No data found | Flag for customer validation |

### Step 3: Auto-Fill Brief and Config

Pre-populate these sections of `BRIEF.md`:

```
## Engagement Details
- Customer: [company name]
- Industry: [detected industry]
- Dates: [if known, else [FILL]]
- Duration: [if known, else [FILL]]

## Business Context
- Company overview: [2-3 sentence summary]
- Industry position: [market position, key differentiators]
- Key business challenges: [bulleted list, confidence-tagged]
- Known technology landscape: [platforms, tools, cloud providers]
- Regulatory considerations: [relevant compliance frameworks]
```

Pre-populate `.hackathon/config.json`:

```json
{
  "customer": "[company name]",
  "industry": "[industry]",
  "dates": "[if known]",
  "duration": "[if known]"
}
```

### Step 4: Generate Use Case Hypotheses

Generate 3-5 "conversation starter" use case hypotheses. These are NOT final use cases — they are provocative starting points designed to spark discussion with the customer.

**Hypothesis format — "What If" cards:**

Each hypothesis is a 1-paragraph scenario written as a provocative "what if" question, followed by structured details:

```
### 💡 [Hypothesis Title]

**What if** [company name] could [transformative capability]? [1-2 sentences painting a 
concrete scenario — name a role, a task, a pain point relieved]. [1 sentence on the 
business impact].

- **Pain point addressed:** [specific challenge from research]
- **Data likely needed:** [data sources this would require]
- **Azure services likely involved:** [2-4 key services]
- **Feasibility gut-check:** 🟢 Likely buildable / 🟡 Needs validation / 🔴 Stretch
- **Confidence:** [how confident are we this resonates, based on research]
```

**Hypothesis generation rules:**
1. At least 1 hypothesis should be "safe" — clearly aligned with known challenges
2. At least 1 hypothesis should be "provocative" — pushing beyond what they've likely considered
3. Each hypothesis must reference something specific about the company (not generic industry boilerplate)
4. Hypotheses should span different parts of the business if possible (operations, customer-facing, back-office)
5. Never generate more than 5 — choice overload kills energy

### Step 5: Suggest Accelerators and Logistics

Based on industry and hypotheses, recommend:

| Suggestion Area | Output |
|-----------------|--------|
| Accelerator packs | Which `.hackathon/accelerators/` packs are relevant |
| Key personas to invite | Roles from the customer side who should attend |
| Data sources to request | Specific datasets to ask for in advance |
| Azure services to pre-provision | Environment prep list |
| Industry-specific considerations | Regulatory, cultural, or domain quirks |

---

## Research Patterns by Company Type

### Public Companies
- Annual report / 10-K (strategy section, risk factors, technology investments)
- Earnings call transcripts (CEO/CFO language about digital priorities)
- Investor presentations (strategy slides)
- LinkedIn job postings (reveals tech stack and hiring priorities)

### Private Companies
- Company website (About, Careers, News/Blog sections)
- LinkedIn company page (size, growth signals)
- Industry association memberships
- Press releases and trade publication mentions
- Crunchbase / similar databases (funding, investors, growth stage)

### Government / Public Sector
- Published strategic plans
- Budget documents (technology line items)
- RFP history (reveals current systems and pain points)
- Audit reports (reveals operational challenges)

### Startups / Scale-ups
- Investor pitch decks (if shared)
- Product documentation
- Founder interviews / podcast appearances
- Job postings (reveals current tech and growth areas)

---

## Quality Gates

### Before Presenting to User

| Check | Action if Failed |
|-------|-----------------|
| All 🔴 Unknown items flagged | Add explicit "[NEEDS CUSTOMER VALIDATION]" markers |
| Assumptions clearly marked | Prefix with "⚠️ Assumed:" |
| No hallucinated specifics | Remove any revenue figures, employee counts, or tech details not confirmed by sources |
| Hypotheses reference company specifics | Rewrite any that read as generic industry templates |
| Config.json parseable | Validate JSON syntax |
| BRIEF.md has no orphaned `[FILL]` markers in auto-filled sections | Complete or explicitly mark "[NOT FOUND — ASK CUSTOMER]" |

### Confidence Disclaimer

Always include at the top of generated content:

```
> ⚠️ This kickstart was auto-generated from public research. Sections marked 
> with [ASSUMED] or [NEEDS CUSTOMER VALIDATION] require confirmation. Review 
> all content before sharing with the customer.
```

---

## Integration Points

| Skill | Integration |
|-------|-------------|
| `industry-tailoring` | Pass detected industry → receive Azure service mapping and industry-specific patterns |
| `hackathon-facilitation` | Kickstart feeds into Formation phase gate criteria |
| `data-simulation` | If data sources are flagged as unavailable, trigger synthetic data planning |
| `ideation-techniques` | Use case hypotheses seed the ideation phase |

---

## Anti-Patterns

| Anti-Pattern | Why It Fails | Instead |
|--------------|-------------|---------|
| Generic industry boilerplate | Customer feels like a template, not a partner | Reference THEIR specific challenges, products, press releases |
| Over-researching (>45 min) | Diminishing returns; delays kickstart delivery | Time-box research to 30 min. Good enough > perfect |
| Too many hypotheses (>5) | Choice paralysis, dilutes energy | Curate to 3-5 strongest |
| Presenting research as fact | Erodes trust when wrong | Always tag confidence levels |
| Skipping competitor context | Misses "how are you different?" framing | Include top 3 competitors even if briefly |
