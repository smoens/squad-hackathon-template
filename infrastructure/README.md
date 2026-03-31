← [README](../README.md)

# Infrastructure

This directory holds provisioning scripts and Infrastructure as Code (IaC) for setting up hackathon environments.

---

## Contents

| Directory | Purpose |
|-----------|---------|
| [`scripts/`](scripts/) | Provisioning and setup scripts (Azure CLI, PowerShell, etc.) |

## Environment Setup

The engagement configuration [`.hackathon/config.json`](../.hackathon/config.json) defines required Azure resources:

- **Compute** — Azure VMs, Azure ML, etc.
- **Storage** — Blob, Data Lake, databases
- **Analytics** — Synapse, Fabric, etc.
- **AI services** — OpenAI, Document Intelligence, etc.

## Accelerators & Provisioning

Some **accelerator packs** (in [`accelerators/`](../accelerators/)) include their own provisioning scripts. Check each accelerator's README for setup instructions specific to that module.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [.hackathon/config.json](../.hackathon/config.json) | Azure resources + engagement config |
| [Accelerator Packs](../accelerators/README.md) | Pluggable tech modules with their own provisioning |
| [Getting Started](../docs/guides/getting-started.md) | Full setup walkthrough |
