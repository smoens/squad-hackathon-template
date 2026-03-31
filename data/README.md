← [README](../README.md)

# Data

This directory holds all data used during the hackathon — both customer-provided datasets and synthetic samples.

---

## Contents

| Directory | Purpose |
|-----------|---------|
| [`customer-data/`](customer-data/) | **Real customer datasets** (gitignored for security) |
| [`sample-datasets/`](sample-datasets/) | Public or synthetic datasets for prototyping |

## Customer Data

> **Security:** Customer data is never committed to the repository. The `customer-data/` directory is in `.gitignore`.

During engagement:

1. Customer provides datasets (via secure link, email, OneDrive, etc.)
2. Download and place in `customer-data/`
3. Use for prototyping and demos **locally only**
4. Transform anonymized subsets into `sample-datasets/` if sharing is needed

**Never:**

- Commit real customer data to git
- Share customer data externally without permission
- Store personally identifiable information (PII) in version control

## Sample Datasets

Use synthetic or public datasets in `sample-datasets/` when:

- Customer data isn't yet available
- You need to prototype without waiting
- You want to share code examples with the wider team

These *are* safe to commit.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [BRIEF.md](../BRIEF.md) | Customer engagement brief (data sources section) |
| [Data Simulation Playbook](../docs/guides/data-simulation-playbook.md) | Patterns for generating synthetic data |
| [Accelerator Packs](../accelerators/README.md) | Packs may include their own sample data |
