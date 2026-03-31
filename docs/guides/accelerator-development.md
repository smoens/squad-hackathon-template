← [Docs](../index.md) | [Guides](./)

# Accelerator Development

An accelerator pack is a reusable collection of code, notebooks, data patterns, and architecture templates for a specific industry or problem domain. Instead of building from scratch, future hackathons stamp the template, drop in an accelerator, and start with hours of work already scaffolded.

**Who this is for:** Architects and builders who've completed a successful hackathon and want to package what they learned.

---

## What Makes a Good Pack

A good pack:

1. **Solves a recognizable problem** — a pattern you'll see again, not a one-off
2. **Works across customers** — with minimal tweaks per engagement
3. **Scaffolds most of the work** — leaving only data and tuning to customize
4. **Includes realistic data** — sample datasets that demonstrate the pattern
5. **Documents assumptions clearly** — what it does, what it doesn't, what you customize

### Anti-Patterns

| Anti-pattern | Why it fails |
|-------------|-------------|
| **Generic everything** | "ML template" without domain knowledge — no customer recognizes themselves |
| **Overcompleted code** | Production-ready pipelines — too much context to cut for a hackathon |
| **No sample data** | "Just bring your data" — future users can't tell if the pack fits |
| **Tightly coupled** | Hardcoded column names, tool versions — breaks on first reuse |

---

## Pack Directory Structure

```
accelerators/{industry}-{problem}/
├── README.md              ← How to use this pack
├── requirements.txt        ← Python deps
├── architecture.md         ← Architecture diagram & decisions
├── config.yaml             ← Customization points
├── scripts/
│   ├── setup.sh           ← Install deps, provision resources
│   └── validate.sh        ← Verify the pack is working
├── notebooks/
│   ├── 01-eda.ipynb       ← Exploratory Data Analysis
│   ├── 02-feature-eng.ipynb
│   └── 03-model.ipynb
├── data/
│   ├── sample-input.csv   ← Realistic sample data
│   └── schema.yaml        ← Column definitions
└── src/
    └── pipeline.py        ← Reusable modules
```

---

## Step-by-Step: Creating a Pack

### Step 1: Name It

Use **descriptive, industry-wide names**:

| Bad | Good |
|-----|------|
| `contoso-predictive-maintenance` | `manufacturing-predictive-maintenance` |
| `the-hack-that-worked` | `retail-demand-forecasting` |

**Format:** `{industry}-{problem}` or `{problem}-{technique}`

### Step 2: Start from the Template

Copy `accelerators/_template/` to your new pack folder:

```bash
cp -r accelerators/_template/ accelerators/manufacturing-predictive-maintenance/
```

### Step 3: Write the README

Include: what it solves, what's included, what you customize, what you don't, and prerequisites.

### Step 4: Add Sample Data

Include **realistic sample data** — same schema as what customers will bring, but synthetic.

Add a `schema.yaml` documenting columns, types, distributions, and ranges. Include the generation script so data is reproducible.

See [Data Simulation Playbook](data-simulation-playbook.md) for generation techniques.

### Step 5: Create the Config

`config.yaml` should contain all customization points:

```yaml
data_path: "./data/sample-input.csv"
timestamp_column: "timestamp"
target_column: "failure"
lag_days: [1, 7, 30]
model_type: "random_forest"
```

Customers modify config, not code.

### Step 6: Add Setup & Validation Scripts

- `scripts/setup.sh` — installs deps, creates output dirs
- `scripts/validate.sh` — verifies data loads, imports work, pack is ready

### Step 7: Document Architecture

Include a `architecture.md` with a Mermaid diagram showing data flow and key decisions. Note known limitations and what to change for different data shapes.

---

## Testing a Pack

Before publishing, **run the pack in a real engagement:**

1. Stamp a new hackathon repo
2. Copy your pack into `accelerators/`
3. Have the squad use it in Build phase
4. Note what's missing or unclear
5. **Update the pack, not the customer code** — the pack absorbs all friction

---

## Publishing

1. Move to `accelerators/` root under the descriptive name
2. Update [`accelerators/README.md`](../../accelerators/README.md) with the new pack
3. Add to available packs table with a one-liner description

---

## Quality Checklist

- [ ] README explains purpose, contents, and customization
- [ ] Sample data included with schema documentation
- [ ] Config file centralizes all customization points
- [ ] Setup script works on a fresh environment
- [ ] Validation script confirms pack is functional
- [ ] Architecture documented with Mermaid diagram
- [ ] Tested in at least one engagement
- [ ] No hardcoded paths or customer-specific values

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Accelerator Packs](../../accelerators/README.md) | Catalog of all packs; how to use one |
| [Running Your First Hackathon](running-your-first-hackathon.md) | When packs get selected (Formation phase) |
| [Data Simulation Playbook](data-simulation-playbook.md) | How to create sample data for your pack |
| [Accelerator Architecture](../concepts/accelerator-architecture.md) | The design thinking behind accelerators |
