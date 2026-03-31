# Build Artifacts

Everything your hackathon produces goes here — code, data, decisions, infrastructure.

## Structure

| Directory | What goes here |
|-----------|---------------|
| `decisions/` | Architecture Decision Records — one per significant technical choice |
| `data/` | Sample datasets, synthetic data, customer data (gitignored) |
| `notebooks/` | Jupyter/Fabric notebooks for your PoCs |
| `scripts/` | Utility scripts, data pipelines, automation |

## Getting Started

This directory starts empty. During the **Build** phase:

1. **Richard** creates PoC code in `notebooks/` and `scripts/`
2. **Dinesh** stages data in `data/`
3. **Gilfoyle** records architecture decisions in `decisions/`

> 💡 If you loaded an accelerator pack, its starter code is in `accelerators/{pack-name}/`.

## Data Guidelines

- **Customer data** is gitignored by default — never commit real customer data
- **Synthetic data** goes in `data/` with a note explaining how it was generated