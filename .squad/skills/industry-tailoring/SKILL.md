# Industry Tailoring

Knowledge for customizing hackathon delivery per industry — data patterns, personas, Azure service mapping, accelerator selection, and feasibility benchmarks.

## When to Use This Skill

- Selecting accelerator packs based on customer industry
- Identifying common personas and data patterns per vertical
- Mapping use case categories to Azure services
- Estimating typical feasibility scores for common use case types
- Tailoring demo narratives to industry-specific language
- Pre-populating use case hypotheses for a given industry

---

## Industry Profiles

### Manufacturing

**Common Personas:** Plant floor supervisor, Quality engineer, Maintenance manager, Supply chain planner, Operations director

**Data Patterns:**
- Time-series sensor data (IoT / OPC-UA / historian)
- ERP/MES transactional data (SAP, Oracle, custom)
- Quality inspection images or logs
- Supply chain / logistics tracking
- Equipment maintenance records (CMMS)

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Predictive maintenance | 🟡 9-11 | IoT Hub, Stream Analytics, Azure ML, Fabric | Data availability is usually the swing factor |
| Quality anomaly detection | 🟡 10-12 | Azure AI Vision, Fabric, Power BI | Requires labeled image data or sensor thresholds |
| Production optimization | 🟠 12-14 | Fabric, Databricks, Azure OpenAI | Complex — scope-cut to single line or shift |
| Supply chain visibility | 🟡 9-11 | Fabric, Azure Maps, Power BI | Data integration count is the risk |
| Digital work instructions | 🟢 7-9 | Azure OpenAI, Azure AI Search, Power Apps | Good for 1-day hackathons |
| Energy/sustainability reporting | 🟢 7-8 | Fabric, Power BI | Often has clean smart meter data |

**Accelerator Pack Hints:** Look for IoT ingestion, time-series analysis, anomaly detection patterns.

---

### Financial Services

**Common Personas:** Risk analyst, Compliance officer, Portfolio manager, Claims adjuster, Branch manager, Customer service lead

**Data Patterns:**
- Transactional ledger data (high volume, structured)
- Customer profile and KYC data (PII-heavy)
- Market data feeds (real-time or batch)
- Regulatory filings and compliance documents
- Call center transcripts / chat logs

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Fraud detection / anomaly | 🟡 9-11 | Fabric, Azure ML, Databricks | Sensitive data — use synthetic for hackathon |
| Document intelligence | 🟢 7-9 | Azure AI Document Intelligence, OpenAI, AI Search | Pre-trained models available |
| Customer 360 / next best action | 🟡 10-12 | Fabric, Azure OpenAI, Cosmos DB | Integration count is the risk |
| Regulatory compliance automation | 🟠 12-14 | Azure OpenAI, AI Search, Fabric | Compliance team may need to approve approach |
| Claims processing acceleration | 🟢 8-10 | Document Intelligence, OpenAI, Power Automate | High demo impact, well-understood pattern |
| Risk reporting / dashboard | 🟢 7-8 | Fabric, Power BI | Clean data usually available |

**Accelerator Pack Hints:** Document extraction, RAG patterns, compliance document search.

**⚠️ Security:** Financial data is almost always PII. Default to synthetic data. Never store real customer financial data in a hackathon repo.

---

### Healthcare & Life Sciences

**Common Personas:** Clinician, Clinical researcher, Hospital administrator, Pharmacovigilance analyst, Lab technician, Patient care coordinator

**Data Patterns:**
- Electronic Health Records (FHIR, HL7)
- Clinical trial data (structured + unstructured)
- Medical imaging (DICOM)
- Lab results and diagnostic codes (ICD-10, SNOMED)
- Claims / billing data
- Genomic data (very large files)

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Clinical document summarization | 🟢 7-9 | Azure OpenAI, AI Search, Azure Health Data Services | Strong demo impact with synthetic clinical notes |
| Adverse event detection | 🟡 10-12 | Azure OpenAI, Fabric, Text Analytics for Health | Needs labeled examples or rules |
| Patient pathway optimization | 🟠 12-14 | Fabric, Databricks, Power BI | Complex data integration |
| Medical image triage | 🟠 13-15 | Azure AI Vision, Custom Vision, ML | Requires annotated images — hard in a hackathon |
| Lab result trending / alerting | 🟢 8-9 | Fabric, Power BI, Azure Functions | Clean structured data usually available |
| Operational efficiency (bed management, scheduling) | 🟡 9-11 | Fabric, Power BI, Power Apps | Good 1-day hackathon scope |

**Accelerator Pack Hints:** FHIR integration, clinical NLP, health data anonymization.

**⚠️ Compliance:** Healthcare data is heavily regulated (HIPAA, GDPR). Always use synthetic data. Azure Health Data Services has built-in anonymization tools.

---

### Retail & Consumer Goods

**Common Personas:** Category manager, Store manager, Supply chain planner, Marketing analyst, E-commerce manager, Customer experience lead

**Data Patterns:**
- Point-of-sale transaction data (high volume)
- Inventory / warehouse management data
- Customer behavior / loyalty program data
- Product catalog / pricing data
- Social media sentiment / reviews
- Supply chain / logistics tracking

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Demand forecasting | 🟡 9-11 | Fabric, Azure ML, Databricks | Time-series models, needs historical data |
| Product recommendation / personalization | 🟡 10-12 | Azure OpenAI, AI Search, Cosmos DB | Integration count is the risk |
| Inventory optimization | 🟡 9-11 | Fabric, Power BI, Azure Functions | Good if POS data is clean |
| Customer sentiment analysis | 🟢 7-9 | Azure OpenAI, Text Analytics, Fabric | Social/review data often accessible |
| Price optimization | 🟠 12-14 | Databricks, Azure ML | Complex modeling, hard to demo compellingly |
| Store performance dashboard | 🟢 7-8 | Fabric, Power BI | Standard BI pattern, strong demo |

**Accelerator Pack Hints:** Retail analytics, recommendation engine, sentiment analysis.

---

### Energy & Utilities

**Common Personas:** Grid operator, Asset manager, Field technician, Sustainability officer, Energy trader, Regulatory compliance analyst

**Data Patterns:**
- Smart meter data (time-series, high volume)
- SCADA / sensor data from infrastructure
- GIS / spatial data (network topology)
- Weather data (external, often free)
- Market/pricing data
- Asset lifecycle / maintenance records

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Asset health monitoring | 🟡 9-11 | IoT Hub, Fabric, Azure ML | Similar to manufacturing predictive maintenance |
| Energy consumption optimization | 🟢 8-10 | Fabric, Power BI, Azure Functions | Smart meter data is usually clean |
| Outage prediction / response | 🟡 10-12 | Fabric, Azure Maps, Azure ML | Weather + grid data integration |
| Sustainability / carbon reporting | 🟢 7-8 | Fabric, Power BI | Regulatory driver — high customer energy |
| Vegetation management (utilities) | 🟠 12-14 | Azure AI Vision, Azure Maps, ML | Requires satellite/drone imagery |
| Field workforce optimization | 🟡 9-11 | Power Apps, Power Automate, Fabric | Good for 1-day hackathons |

**Accelerator Pack Hints:** Time-series analysis, IoT ingestion, GIS visualization.

---

### Public Sector & Government

**Common Personas:** Policy analyst, Case worker, Program manager, Citizen services lead, Budget analyst, IT modernization lead

**Data Patterns:**
- Case management records
- Citizen service requests
- Budget / procurement data
- Geographic / census data (often public)
- Regulatory and legal documents
- Legacy system exports (CSV, mainframe dumps)

**High-Value Use Case Categories:**

| Category | Typical Feasibility | Azure Services | Notes |
|----------|:-------------------:|----------------|-------|
| Document classification / routing | 🟢 7-9 | Azure OpenAI, AI Search, Logic Apps | High volume of unstructured docs |
| Citizen request triage | 🟢 8-9 | Azure OpenAI, Power Automate, Cosmos DB | Good 1-day scope |
| Budget / spending analysis | 🟢 7-8 | Fabric, Power BI | Data is usually structured and clean |
| Policy impact simulation | 🟠 13-15 | Databricks, Azure ML | Complex modeling, hard to scope |
| Legacy data modernization | 🟡 9-11 | Fabric, Azure Data Factory, Databricks | Data conversion is the core value |
| Fraud / waste detection | 🟡 10-12 | Fabric, Azure ML, Power BI | Sensitive data — synthetic only |

**⚠️ Compliance:** Government data has sovereignty requirements. Verify Azure region and data residency constraints during Formation.

---

## Accelerator Pack Selection Heuristics

| Customer Signal | Suggested Pack Pattern |
|-----------------|----------------------|
| "We have IoT sensors / time-series data" | IoT ingestion + time-series analysis |
| "We want to search our documents" | RAG pattern (Azure OpenAI + AI Search) |
| "We have images to analyze" | Azure AI Vision + Custom Vision |
| "We need a dashboard" | Fabric + Power BI |
| "We want to modernize ETL / data pipelines" | Fabric + Data Factory |
| "We have unstructured PDFs / forms" | Azure AI Document Intelligence |
| "We want a chatbot / copilot" | Azure OpenAI + AI Search + prompt engineering |
| "We need real-time processing" | Event Hubs + Stream Analytics + Fabric |
| "We want to predict X" | Azure ML / Databricks + Fabric |

### Pack Selection Process

1. Read `BRIEF.md` → identify customer's tech landscape and use case hypotheses
2. Match to industry profile above → identify likely use case categories
3. Map categories to Azure service patterns
4. Check if a matching accelerator pack exists in `accelerators/`
5. If no pack exists → flag for creation OR build from scratch
6. Record selected packs in `.hackathon/config.json` → `accelerator_packs[]`

---

## Industry-Specific Demo Language

When crafting demos per industry, use these patterns:

| Industry | Demo Hook | Avoid |
|----------|-----------|-------|
| Manufacturing | "Reduce unplanned downtime by X%" | Abstract ROI without shop-floor context |
| Financial Services | "Process Y claims per hour instead of Z" | Anything that implies replacing compliance teams |
| Healthcare | "Give clinicians X minutes back per patient" | Anything suggesting autonomous clinical decisions |
| Retail | "Increase basket size / reduce stockouts by X%" | Generic "better customer experience" |
| Energy | "Detect X before it causes Y" / "Reduce carbon by Z" | Overpromising on prediction accuracy |
| Public Sector | "Reduce citizen wait time from X to Y" | Jargon — stakeholders are often non-technical |

---

## Typical Feasibility Score Reference

Quick reference for estimating scores before detailed assessment:

| Use Case Pattern | Typical Range | Key Risk Dimension |
|-----------------|:------------:|-------------------|
| Dashboard / BI reporting | 6-8 🟢 | Data quality |
| Document search / RAG | 7-9 🟢 | Data availability (corpus) |
| Anomaly detection (structured data) | 9-11 🟡 | Data quality + model complexity |
| Predictive model (time-series) | 9-12 🟡 | Data availability + model complexity |
| Multi-source data integration | 10-13 🟡/🟠 | Integration count |
| Image / video analysis | 12-15 🟠 | Data availability (labeled images) |
| Real-time streaming pipeline | 11-14 🟠 | Integration count + visualization |
| Custom ML model training | 13-16 🟠/🔴 | Model complexity + data quality |

These are starting estimates — adjust based on the specific customer's data readiness and available accelerator packs.
