# Quickstart Examples — Talking to Your Hackathon Squad

← [Docs](../index.md) | [Guides](./)

> **Copy, paste, adapt.** Every example below is a real sentence you can drop into chat. Replace the `[bracketed]` parts with your specifics and go.

---

## 1. Getting Started — Your First Commands

### How to address the squad

| You want to reach… | Say… |
|---|---|
| One agent by name | `Jared, …` / `Gilfoyle, …` / `Richard, …` / `Dinesh, …` / `Erlich, …` |
| One agent by role | `Facilitator, …` / `Architect, …` / `Builder, …` / `Data Wrangler, …` / `Demo Crafter, …` |
| The whole team | `Team, …` |
| The board / status | `Ralph, status` |

### The very first thing to say after stamping

```
Jared, we're kicking off a new hackathon engagement.
Customer: [Company Name]
Industry: [e.g. manufacturing, retail, financial services]
Date(s): [e.g. April 15-16, 2026]
Platform focus: [e.g. Microsoft Fabric + Power BI]
Brief: [paste customer brief or 2-3 sentence summary]

Set up the engagement and walk me through what you need from me.
```

That single message gets Jared to scaffold the engagement config, create the timeline, and prompt you for anything missing.

---

## 2. Formation Phase Examples

> **When:** Days or weeks before the hackathon. You're scoping, prepping data, and loading context.

### Setting up a new engagement

```
Jared, we have a 2-day manufacturing hackathon for Contoso Steel on April 22-23.
Their brief: "We want to reduce unplanned downtime on our hot rolling mill line.
We have 18 months of sensor data in Azure SQL and shift logs in SharePoint."
Set up the engagement and propose a high-level agenda.
```

### Configuring the engagement

```
Team, update the config for this engagement:
- Duration: 2 days (Day 1 = ideation + build start, Day 2 = build + demo)
- Platform: Microsoft Fabric (Lakehouse, notebooks, Data Factory) + Power BI
- Industry: pharmaceutical
- Customer maturity: early cloud adoption, no existing lakehouse
- Demo audience: VP Manufacturing and IT Director
```

### Data readiness check

```
Dinesh, assess what data we'll need for predictive maintenance use cases.
The customer has:
- Historian data in Azure SQL (vibration, temperature, pressure — 2 years)
- Maintenance work orders in SAP PM (exported to CSV)
- Shift schedules in an Excel file
What's usable as-is, what needs cleaning, and what gaps should we flag before day 1?
```

### Pre-loading context

```
Gilfoyle, review this customer's tech landscape and suggest which accelerator
packs to pre-load:
- Azure SQL Database (production historian)
- Power BI Premium (existing dashboards)
- No Fabric yet — greenfield
- SAP ECC 6.0 on-prem
- They want to evaluate Fabric + Databricks side by side
Which accelerators fit? What should we have ready before the team walks in?
```

### Stakeholder prep

```
Erlich, we're presenting the hackathon pitch to the customer's CTO next Tuesday.
Draft a 1-page overview: what we'll do in 2 days, what they'll walk away with,
and what we need from them (data access, SMEs on-site, decision-maker at demo).
```

---

## 3. Ideation Phase Examples

> **When:** Day 1 morning. Brainstorming, prioritizing, reality-checking.

### Brainstorming use cases

```
Jared, facilitate a brainstorm for Contoso Steel.
Business context: They lose ~€2M/year to unplanned downtime on 3 rolling mill lines.
They also have quality variability on their cold-rolled coils and want to
reduce scrap rates. Generate 5-7 use case canvases with business value,
data requirements, and complexity rating.
```

### Feasibility scoring

```
Gilfoyle, score these 5 use cases for feasibility given a 1.5-day build window:

1. Predictive maintenance alerts on rolling mill bearings
2. Real-time quality prediction for coil thickness
3. Energy consumption optimization per production batch
4. Automated scrap classification from camera images
5. Shift performance dashboard comparing OEE across lines

Focus on what's realistically demo-able. Factor in: data availability (Azure SQL historian),
platform (Fabric Lakehouse + Power BI), and team size (3 builders).
```

### Industry-specific ideation

```
Team, what are the most compelling use cases for a retail company doing
demand forecasting with Power BI and Fabric? They have 200 stores,
3 years of POS data in Snowflake, and want to optimize markdown pricing.
Suggest 5 use cases ranked by demo impact and feasibility.
```

### Narrowing scope

```
Jared, we've got 7 ideas on the board but can only build 2-3 in the time we have.
Help the customer prioritize: which ones give the biggest "wow" in a demo while
being achievable? The customer's top pain point is unplanned downtime,
but the CTO is most excited about AI-driven quality prediction.
```

### Quick tech check

```
Gilfoyle, the customer wants to use Azure OpenAI to classify maintenance work
orders by failure type. Is that doable in a hackathon? What model, what prompt
pattern, and how do we connect it to their SAP work order export?
```

---

## 4. Build Phase Examples

> **When:** Day 1 afternoon through Day 2. Heads-down building.

### Architecture sketch

```
Gilfoyle, sketch the architecture for our predictive maintenance dashboard:
- Source: Azure SQL historian (vibration, temp, pressure at 1-min intervals)
- Ingestion: Fabric Data Factory pipeline into Bronze lakehouse table
- Transform: Notebook for Silver layer (cleaning, feature engineering)
- Model: Simple anomaly detection (Z-score or Isolation Forest)
- Serve: Gold table → Power BI dashboard with real-time alerts
Include a Mermaid diagram.
```

### Building a notebook

```
Richard, create a PySpark notebook that:
1. Reads CSV sensor data from the lakehouse Files/ folder
2. Writes it to a Bronze Delta table `bronze_sensor_readings`
3. Schema: timestamp (datetime), machine_id (string), temperature (double),
   vibration (double), pressure (double), machine_status (string)
4. Add basic data quality checks — null counts, value ranges, duplicate rows
Follow medallion architecture naming conventions.
```

### Data generation

```
Dinesh, generate a synthetic dataset of 10,000 manufacturing sensor readings.
Columns: timestamp (1-min intervals over 7 days), machine_id (M-001 to M-005),
temperature (normal ~75°C, anomaly spikes to 95-110°C), vibration (normal 0.2-0.8 mm/s,
anomaly 1.5-3.0), pressure (200-250 bar normal, drops to 150 during faults),
machine_status (running/idle/fault — 2% fault rate).
Output as CSV, ready to upload to the lakehouse.
```

### Silver layer transform

```
Richard, write the Silver layer notebook:
- Read from `bronze_sensor_readings`
- Remove duplicates and nulls
- Add rolling averages: 15-min and 1-hour windows for temperature and vibration
- Add a `shift` column (Day: 06-14, Evening: 14-22, Night: 22-06)
- Add `is_anomaly` flag where temperature > 90°C OR vibration > 1.5 mm/s
- Write to `silver_sensor_enriched` Delta table
```

### Power BI model

```
Richard, create a Power BI dataset from the Gold lakehouse tables:
- `gold_machine_health` (latest status per machine)
- `gold_anomaly_events` (flagged events with timestamps)
- `gold_shift_summary` (OEE, fault count, avg temp per shift)
Set up relationships and add DAX measures for: fault rate %,
mean time between failures, and rolling 7-day anomaly trend.
```

### Midday status check

```
Team, status check — where are we on each use case?
- Use case 1 (Predictive Maintenance): ?
- Use case 2 (Quality Prediction): ?
What's blocked? What needs to be cut to hit the demo deadline at 3pm tomorrow?
```

### Unblocking

```
Dinesh, the Bronze ingestion notebook is failing — it can't parse the timestamp
column from the SAP export. The format is "20260415-143022" instead of ISO 8601.
Fix the parsing and re-run the pipeline.
```

---

## 5. Demo Phase Examples

> **When:** Final session. Polishing, scripting, dry-running.

### Demo scripting

```
Erlich, write a 5-minute demo script for our predictive maintenance use case.
Audience: plant managers and IT leadership at Contoso Steel.
Structure: problem → data journey → live dashboard → anomaly alert scenario → business impact.
Make it punchy — these are factory floor people, not data scientists.
Include speaker notes and suggested click-through order.
```

### Dry run

```
Erlich, let's do a dry run. Walk me through the demo flow screen by screen
and flag any gaps — missing visuals, dead filters, data that doesn't tell the story.
I want to know exactly where the demo might stumble.
```

### Last-minute fixes

```
Richard, the dashboard date picker is filtering wrong — it shows 2024 data
but our synthetic dataset is all 2026. Fix the default filter range and
make sure the "last 7 days" preset works. Demo is at 3pm.
```

### Presentation deck

```
Erlich, draft a 6-slide executive summary deck:
1. Title + customer logo placeholder
2. Challenge — the business problem in their words
3. What we built — architecture diagram + screenshots
4. Live demo highlights — 2-3 key screenshots with callouts
5. Business impact — projected value (downtime reduction, scrap savings)
6. Next steps — what it takes to go from PoC to production
Keep the text minimal. These slides support the live demo, not replace it.
```

---

## 6. Wind-Down Phase Examples

> **When:** After the demo. Retro, packaging, handoff.

### Retrospective

```
Jared, facilitate the retro for the Contoso Steel hackathon.
Cover: what worked, what didn't, what patterns should we keep for next time.
Also capture: which accelerator packs were useful, which were missing,
and what the customer's reaction was to each use case.
```

### Knowledge extraction

```
Team, what reusable patterns did we discover in this engagement?
Specifically:
- Any notebooks or pipelines worth templatizing?
- Data generation scripts that could become accelerator packs?
- Architecture patterns we should standardize?
- Demo flow structures that landed well?
Write them up so the next hackathon team can reuse them.
```

### Handoff document

```
Erlich, draft the HANDOFF.md for Contoso Steel. Include:
- Executive summary (2 paragraphs)
- Architecture diagram (embed the Mermaid diagram from build phase)
- What was built (list of artifacts: notebooks, dashboards, datasets)
- What's working and what's stubbed out
- Recommended next steps to go to production
- Team contacts and engagement dates
```

### Capture decisions

```
Jared, log all the technical and scope decisions we made during the hackathon:
- Why we chose Isolation Forest over LSTM for anomaly detection
- Why we went Fabric-only instead of Fabric + Databricks
- Why we cut the image classification use case on day 2
Format them as lightweight ADRs for the decision log.
```

---

## 7. Cross-Cutting Examples

> **These work in any phase.**

### Multi-agent team requests

```
Team, brainstorm opportunities for a financial services client doing fraud detection.
They have 5 years of transaction data in Azure Synapse, a legacy rules engine,
and they want to modernize with Fabric and Azure AI.
Jared — generate use case canvases.
Gilfoyle — flag technical constraints.
Dinesh — estimate data prep effort.
```

### Quick architecture questions

```
Gilfoyle, will this architecture scale to 1M events/day?
Current design: Event Hub → Fabric Eventstream → Lakehouse Bronze → notebook Silver → Gold.
What's the bottleneck and what changes at scale?
```

### Scope management

```
Jared, we're running behind on use case 2 (quality prediction).
Cut scope to just the Power BI dashboard with historical analysis —
drop the real-time scoring notebook. Update the board and let the team know.
```

### Board status

```
Ralph, status
```

```
What's the board look like? Any blockers?
```

### Context injection mid-stream

```
Team, the customer just told us they also have IoT Hub streaming data from
200 PLCs on the shop floor. This changes our architecture options.
Gilfoyle — does this unlock real-time scoring?
Dinesh — can you pull a sample from IoT Hub into the lakehouse?
Richard — if yes, add a Eventstream → Bronze path to the ingestion notebook.
```

### Ad-hoc help

```
Gilfoyle, I'm getting a "DeltaTable not found" error in the Silver notebook.
The table name is silver_sensor_enriched and I'm referencing it as
spark.read.format("delta").table("silver_sensor_enriched"). What's wrong?
```

---

## 8. Industry-Specific Starters

### Manufacturing

```
Team, we have a 2-day hackathon with a steel manufacturer. They want to reduce
unplanned downtime and improve OEE. They have historian data, SAP PM work orders,
and MES shift logs. Platform: Fabric + Power BI. What use cases should we pitch?
```

```
Dinesh, generate synthetic CNC machine data: spindle speed, feed rate, tool wear index,
and vibration. 50 machines, 30 days, 1-minute intervals. Include 3% anomaly rate
with correlated failures (tool wear > 80% AND vibration spike).
```

```
Richard, build a Gold layer notebook that calculates OEE (availability × performance × quality)
per machine per shift, and flag any shift where OEE drops below 65%.
```

```
Erlich, this demo is for plant floor supervisors — no buzzwords.
Frame everything as "here's what your morning standup looks like with this dashboard."
```

### Financial Services

```
Team, a retail bank wants to modernize fraud detection. They have 5 years of
card transaction data in Synapse, a legacy rules engine flagging 12% false positives,
and they want to prove Fabric + Azure ML can do better in 2 days.
```

```
Dinesh, generate synthetic credit card transactions: 100,000 records,
normal spend patterns for 500 customers, with 1.5% fraud injection.
Include merchant category, amount, timestamp, geo-location, and device fingerprint.
```

```
Gilfoyle, compare two architecture options for real-time fraud scoring:
(A) Fabric Eventstream → notebook scoring → alert
(B) Azure Stream Analytics → ML model endpoint → Power BI push dataset
Which one can we build in a hackathon? Which one scales to production?
```

```
Richard, create a notebook that trains a simple fraud classifier (Random Forest)
on the synthetic data. Log the model to MLflow, show precision/recall,
and create a confusion matrix visual.
```

### Healthcare

```
Team, a hospital network wants to predict patient no-shows for outpatient clinics.
They have 2 years of appointment data in Epic (extracted to CSV),
weather data, and patient demographics. Platform: Fabric + Power BI.
```

```
Dinesh, generate synthetic patient appointment data: 50,000 appointments across
12 clinics, with no-show rate of ~18%. Include: appointment date, clinic, specialty,
lead time (days between scheduling and appointment), patient age bracket,
insurance type, distance from clinic, and weather conditions on appointment day.
```

```
Richard, build a logistic regression model predicting no-show probability.
Features: lead time, previous no-shows, distance, day of week, specialty.
Output a scored table with risk buckets (low/medium/high) for the dashboard.
```

```
Erlich, the audience is clinic operations managers. Focus the demo on:
"Here's your Monday morning view — which patients are high-risk for no-show,
and what can your front desk do about it (reminder calls, overbooking slots)."
```

### Retail

```
Team, a grocery chain with 300 stores wants to optimize markdown pricing.
They have POS data in Snowflake (3 years), current margin rules in Excel,
and they want to use Fabric to build a smarter markdown engine.
```

```
Dinesh, generate synthetic POS data: 200,000 transactions, 500 SKUs across
5 categories (produce, dairy, bakery, meat, beverages), with seasonality,
day-of-week patterns, and price elasticity baked in.
```

```
Gilfoyle, for the markdown optimization use case — should we go with a
rules-based approach (fast to build, easy to explain) or a simple ML model
(better accuracy, harder to demo)? We have 1 day to build it.
```

```
Erlich, the demo audience is the Chief Merchandising Officer.
Translate everything into margin impact and waste reduction.
Skip the data engineering slides — lead with the business dashboard.
```

### Energy

```
Team, a wind farm operator wants to predict turbine failures and optimize
maintenance scheduling. They have SCADA data from 80 turbines (wind speed,
rotor RPM, generator temperature, power output), plus work order history.
Platform: Fabric + Azure AI.
```

```
Dinesh, generate synthetic SCADA data for 20 wind turbines over 90 days:
10-second intervals, wind speed (3-25 m/s with Weibull distribution),
rotor RPM, generator temp, power output (following the turbine power curve),
and injected degradation patterns (bearing wear, pitch misalignment).
```

```
Richard, build an anomaly detection notebook for turbine generator temperature:
rolling Z-score over 1-hour windows, flagging deviations > 2.5 sigma.
Cross-reference with wind speed to filter out expected temperature rises
during high-wind periods.
```

```
Erlich, the customer is an O&M director who thinks AI is overhyped.
Build the demo around a specific turbine event: "Turbine T-014 showed
early warning signs 3 days before the actual failure. Here's what the
dashboard would have shown your morning shift team."
```

---

## Tips for Getting the Best Results

| Tip | Example |
|---|---|
| **Be specific about data** | "CSV with 10 columns" beats "some data" |
| **Name the audience** | "plant managers" → Erlich tunes the language |
| **Set time constraints** | "we have 3 hours" → Gilfoyle scopes realistically |
| **Paste real context** | Drop in the customer brief, tech stack, or org chart |
| **Use names for focus** | `Dinesh, …` routes directly; `Team, …` broadcasts |
| **Ask for status often** | `Ralph, status` keeps the board honest |
| **Cut scope early** | Better to demo 2 polished things than 4 broken ones |
