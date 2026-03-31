← [Docs](../index.md) | [Guides](./)

# Industry Customization

The hackathon template is industry-agnostic by design. But customer engagements aren't. This guide covers when and how to tailor the template for a specific vertical — without over-engineering the formation phase.

**Who this is for:** Facilitators and Architects customizing for a specific engagement.

---

## When to Customize vs. Use As-Is

Not every engagement needs customization. Here's how to decide:

| Signal | Action |
|--------|--------|
| Customer is in a common industry and use cases are standard | Use as-is — accelerator packs cover it |
| Customer uses industry-specific terminology heavily | Light customization — adjust Brief language and seed use cases |
| Customer's domain has unique data patterns or compliance requirements | Moderate customization — tailor data sections and add domain guardrails |
| You're running repeated engagements in the same vertical | Full customization — create an industry-specific accelerator pack |

> **Tip:** When in doubt, start generic. You can always customize on Day 1 when you have the customer in the room. Over-customizing during formation risks solving the wrong problem.

---

## What to Customize

### 1. BRIEF.md Fields

Tailor the engagement brief to reflect industry-specific context:

| Section | How to customize | Example |
|---------|-----------------|---------|
| **Business Context** | Add industry-specific framing questions | Manufacturing: *"What's your OEE target? Current scrap rate?"* |
| **Goals** | Suggest industry-common outcomes | Retail: *"Reduce stockout rate by X%"* |
| **Technical Landscape** | Pre-fill common stack patterns | Healthcare: *"EHR system: Epic / Cerner / other?"* |
| **Data Sources** | List typical data sources for the vertical | Energy: *"SCADA, historian, weather API, grid telemetry"* |

### 2. Accelerator Pack Selection

Match accelerator packs to the customer's industry patterns:

| Industry | Common patterns | Likely accelerators |
|----------|----------------|-------------------|
| Manufacturing | Predictive maintenance, quality inspection, OEE dashboards | IoT ingestion, anomaly detection, time-series |
| Financial Services | Fraud detection, risk scoring, document processing | Document AI, classification, compliance pipelines |
| Retail | Demand forecasting, personalization, inventory optimization | Forecasting models, recommendation engines |
| Healthcare | Clinical decision support, patient flow, imaging analysis | NLP/NER, image classification, HL7/FHIR connectors |
| Energy | Asset monitoring, load forecasting, sustainability reporting | Time-series analysis, geospatial, IoT |

### 3. Use Case Hypotheses

Seed the ideation session with industry-relevant hypotheses:

- Study the customer's public reports, press releases, and industry benchmarks
- Identify 3–5 pain points common to their vertical
- Frame each as a *"What if..."* question using their terminology

**Generic:** *"What if you could predict equipment failures?"*
**Customized:** *"What if your maintenance team could see which CNC machines will fault in the next 48 hours, based on vibration and thermal sensor trends?"*

### 4. Data Sources

Map typical data sources for the industry and pre-populate the Brief:

| Source type | What to look for | Why it matters |
|-------------|-----------------|---------------|
| **Operational data** | ERP, MES, SCADA, POS systems | Core business process data |
| **Sensor / IoT** | Historian, time-series DBs, edge devices | Real-time signals for predictive use cases |
| **Documents** | Invoices, contracts, reports, manuals | Unstructured data for AI extraction |
| **External** | Weather, market data, regulatory feeds | Context signals that enrich models |

---

## Industry-Specific Pre-Flight Checklist

Use this checklist during formation to ensure your customization is solid:

- [ ] Industry terminology mapped — Brief uses the customer's language, not ours
- [ ] Seed use cases reflect real vertical pain points (not generic AI demos)
- [ ] Data source table in Brief is pre-populated with likely sources
- [ ] Relevant accelerator packs identified and loaded
- [ ] Compliance or regulatory constraints noted (HIPAA, SOX, GDPR, etc.)
- [ ] Industry benchmarks gathered for Impact beat in demos (e.g., "industry average OEE is 85%")
- [ ] At least one team member has domain familiarity or has done pre-reading

---

## Creating Industry-Specific Accelerator Packs

If you're running repeated engagements in the same vertical, invest in a reusable pack:

### When to Create a Pack

- You've run **2+ hackathons** in the same industry
- You keep re-building the same starter notebooks, data connectors, or reference architectures
- There are industry-specific data formats or compliance patterns that need boilerplate

### What Goes in a Pack

| Component | Example |
|-----------|---------|
| **README.md** | Setup instructions, prerequisites, scope |
| **Reference architecture** | Mermaid diagram + description of the typical pattern |
| **Starter notebooks** | Data ingestion, transformation, model template |
| **Sample data** | Synthetic dataset that mirrors real industry data shapes |
| **Provisioning scripts** | Infrastructure setup for common services |
| **Domain glossary** | Key terms the squad should know |

### How to Create One

1. Copy `accelerators/_template/` to `accelerators/{industry-pattern}/`
2. Fill the README with industry context and setup steps
3. Add the components listed above
4. Test in at least one engagement before promoting to the main template

See [Accelerator Packs](../../accelerators/README.md) for the full guide.

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [BRIEF.md](../../BRIEF.md) | Engagement brief — customize per industry |
| [Accelerator Packs](../../accelerators/README.md) | Tech-specific modules and how to create them |
| [Getting Started](getting-started.md) | Full setup walkthrough |
| [Running Ideation](running-ideation.md) | Seed use cases feed into ideation |
| [Customer First](../principles/customer-first.md) | Customization serves the customer, not the template |
