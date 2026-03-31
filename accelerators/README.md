← [README](../README.md) | 🔧 Accelerator System

# Accelerator Packs

Accelerator packs are **pluggable, tech-specific modules** that get loaded per engagement. They contain reference architectures, starter notebooks, provisioning scripts, and sample data for common hackathon patterns.

## How It Works

Each accelerator pack lives in its own directory under `accelerators/`. Packs are **not loaded by default** — the squad selects which packs to activate based on the customer's use cases and tech landscape.

## How to Load a Pack for an Engagement

1. Review available packs below
2. Add pack names to `.hackathon/config.json` → `accelerator_packs[]`
3. Copy relevant notebooks/scripts into `use-cases/{name}/` or reference them directly
4. Follow the pack's `README.md` for setup instructions

## How to Create a New Pack

1. Copy `accelerators/_template/` to `accelerators/{pack-name}/`
2. Fill in the `README.md` with pack details
3. Add reference architectures, notebooks, scripts, and sample data
4. Test the pack in at least one engagement before promoting

## Available Packs

| Pack | Description | Status |
|------|-------------|--------|
| `_template` | Template for creating new packs | 📐 Template |

*Add new packs to this table as they're created.*

---

## 📎 Related

| Document | Purpose |
|----------|--------|
| [Brief](../BRIEF.md) | Customer tech landscape drives pack selection |
| [Formation Checklist](../.hackathon/checklist-formation.md) | Select packs during formation |
| [Knowledge Extraction](../.hackathon/checklist-knowledge-extract.md) | Promote new packs post-hackathon |
