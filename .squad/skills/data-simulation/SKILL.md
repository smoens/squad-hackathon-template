# Data Simulation

Synthetic data generation patterns for hackathon demos — per-industry templates, realistic messiness, and security-first generation practices.

## When to Use This Skill

- Customer data is unavailable, delayed, or restricted
- Building demo-ready datasets that look like the customer's world
- Creating realistic simulators for live demo moments
- Generating test data for build sprints
- Replacing sensitive data with safe synthetic alternatives

---

## Simulation Philosophy

### Core Principles

1. **Mirror their data shapes.** Same column names, same value ranges, same messiness. If their production data has a `plant_id` column with codes like `PLT-001`, your synthetic data should too.
2. **Don't make it too clean.** Real data has nulls, outliers, format inconsistencies, and duplicates. Perfect data looks fake and breaks trust.
3. **Label everything.** Every synthetic dataset must be clearly marked as simulated. No ambiguity.
4. **Never use real PII.** Not even "anonymized" real data. Generate from scratch.
5. **Match their scale impression.** 100-1000 rows is enough to be convincing without slowing demos.

### The Realism Spectrum

| Level | Description | When to Use |
|-------|-------------|-------------|
| **Sketch** | Right column names, random values | Very early ideation, proving a concept |
| **Shaped** | Realistic distributions, correct ranges, some patterns | Build sprint, initial demos |
| **Polished** | Industry-authentic values, realistic correlations, deliberate messiness | Final demo, customer-facing presentations |

**Target: Shaped for build sprints, Polished for final demos.**

---

## Per-Industry Patterns

### Manufacturing

| Data Type | Key Columns | Realistic Patterns | Messiness to Add |
|-----------|-------------|-------------------|------------------|
| **Sensor time-series** | `timestamp`, `sensor_id`, `machine_id`, `value`, `unit`, `quality_flag` | OPC-UA naming conventions (`ns=2;s=Temperature.PV`), 1-sec or 1-min intervals, values drift within operating range with occasional spikes | Missing readings (2-5%), occasional sensor dropout (NaN for a few minutes), timezone inconsistencies |
| **Quality inspection** | `batch_id`, `inspection_time`, `inspector_id`, `defect_type`, `severity`, `pass_fail` | Defect rates 1-5%, clustered around shift changes, seasonal patterns | Handwritten notes in free-text field, inconsistent defect naming ("scratch" vs "Scratch" vs "surface_scratch") |
| **Maintenance records** | `work_order_id`, `asset_id`, `reported_date`, `completed_date`, `failure_mode`, `parts_used`, `downtime_hours` | Planned maintenance every N hours, unplanned follows Weibull distribution | Missing completion dates (20% of records), vague failure descriptions |
| **Production batch** | `batch_id`, `product_sku`, `start_time`, `end_time`, `yield_pct`, `line_id`, `shift` | Yield 85-98%, lower on night shifts, dips after changeovers | Overlapping batch times (data entry errors), missing yield for some batches |

**Manufacturing-specific tips:**
- Use realistic machine/line naming: `LINE-A`, `CNC-04`, `PRESS-12`
- Sensor values should have physical meaning (temperature 60-120°C, pressure 2-8 bar)
- Include weekends with reduced or zero production (unless 24/7 operation)

### Financial Services

| Data Type | Key Columns | Realistic Patterns | Messiness to Add |
|-----------|-------------|-------------------|------------------|
| **Transaction ledger** | `txn_id`, `account_id`, `timestamp`, `amount`, `currency`, `merchant_category`, `channel` | Daily patterns (more activity weekdays), amount distributions by category, rare large transactions | Duplicate entries (0.1%), currency format inconsistencies ($1,000 vs 1000.00), missing merchant category |
| **Customer profiles** | `customer_id`, `segment`, `tenure_years`, `product_count`, `risk_score`, `region` | Segmentation matches realistic distributions (retail heavy, private banking small), tenure correlates with product count | Outdated addresses (10%), conflicting segment labels between systems |
| **Market data** | `date`, `ticker`, `open`, `high`, `low`, `close`, `volume` | OHLCV follows realistic patterns, volume spikes on earnings days | Missing data for holidays (some systems fill forward, some leave gaps) |
| **Compliance docs** | `doc_id`, `customer_id`, `doc_type`, `status`, `expiry_date`, `reviewer` | KYC docs expire, AML flags follow patterns, review cycles | Expired but not renewed (15%), inconsistent naming of doc types |

**Financial-specific tips:**
- Never generate real account numbers — use formatted fakes (`ACCT-XXXX-XXXX`)
- Transaction amounts should follow power-law distribution (many small, few large)
- Include realistic regulatory markers (SAR, CTR thresholds)

### Healthcare

| Data Type | Key Columns | Realistic Patterns | Messiness to Add |
|-----------|-------------|-------------------|------------------|
| **FHIR resources** | Standard FHIR Patient, Observation, Condition, Encounter | Age-appropriate diagnoses, realistic vital sign ranges, coded values from standard terminologies | Missing optional FHIR fields, mixed coding systems (ICD-10 and SNOMED in same dataset) |
| **Clinical notes** | `note_id`, `patient_id`, `encounter_date`, `note_type`, `text`, `author` | Progress notes, discharge summaries, referral letters with realistic clinical language | Abbreviations, typos, inconsistent formatting, copy-paste artifacts |
| **Lab results** | `order_id`, `patient_id`, `test_code`, `result_value`, `unit`, `reference_range`, `flag` | Results cluster around normal with tails, abnormals correlate with diagnoses | Units vary (mg/dL vs mmol/L for same test), missing reference ranges |

**Healthcare-specific tips:**
- Use Synthea (open-source) for realistic FHIR patient records
- ALL data must be synthetic — healthcare has zero tolerance for real PHI in demos
- Include realistic clinical terminology but avoid overly rare conditions

### Retail / CPG

| Data Type | Key Columns | Realistic Patterns | Messiness to Add |
|-----------|-------------|-------------------|------------------|
| **POS transactions** | `txn_id`, `store_id`, `timestamp`, `sku`, `qty`, `unit_price`, `total`, `payment_method` | Seasonal spikes (holidays), weekend patterns, basket size varies by store type | Returns as negative lines, voided transactions, loyalty ID sometimes missing |
| **Inventory levels** | `store_id`, `sku`, `date`, `on_hand`, `on_order`, `min_stock`, `max_stock` | Sawtooth pattern (replenishment cycles), some items perpetually overstocked | Negative on-hand (system lag), phantom inventory, last-scan dates outdated |
| **Customer journey** | `session_id`, `customer_id`, `timestamp`, `channel`, `action`, `product_viewed`, `converted` | Funnel drop-off pattern (browse > cart > purchase ~3%), multi-channel journeys | Anonymous sessions (no customer_id), bot traffic mixed in, session ID conflicts |

### Energy / Utilities

| Data Type | Key Columns | Realistic Patterns | Messiness to Add |
|-----------|-------------|-------------------|------------------|
| **Smart meter readings** | `meter_id`, `timestamp`, `kwh`, `voltage`, `power_factor`, `tariff_code` | Daily load curves (morning/evening peaks), seasonal variation, weekday/weekend patterns | Meter communication gaps (3-8% missing readings), estimated reads flagged differently |
| **Grid telemetry** | `substation_id`, `timestamp`, `load_mw`, `frequency_hz`, `voltage_kv`, `alert_level` | Frequency hovers around 50/60 Hz, load follows predictable patterns with weather correlation | Telemetry gaps during outages (ironic but realistic), clock drift between substations |
| **Consumption patterns** | `customer_id`, `billing_period`, `usage_kwh`, `peak_demand_kw`, `tariff`, `estimated_flag` | Residential: seasonal (heating/cooling), commercial: flat weekday with weekend dip | Estimated reads (15-20% of bills), billing period misalignment |

---

## Tools and Techniques

### Python Libraries

| Tool | Best For | Example |
|------|----------|---------|
| **Faker** | Names, addresses, dates, phone numbers, company names | `fake.name()`, `fake.date_between()` |
| **NumPy** | Numeric distributions, time-series patterns | `np.random.normal(mean, std, size)` |
| **Pandas** | DataFrame construction, CSV/Parquet output | Structured data assembly |
| **SDV (Synthetic Data Vault)** | Learning distributions from sample data, generating more | When you have a small sample to amplify |
| **Faker providers** | Industry-specific fakes (IBAN, SWIFT, ICD codes) | Custom providers for domain data |

### Fabric Notebook Pattern

```python
# Standard synthetic data generation pattern for Fabric notebooks
import pandas as pd
import numpy as np
from datetime import datetime, timedelta

np.random.seed(42)  # Reproducible

n_rows = 500  # Demo-appropriate size

# Generate base data
df = pd.DataFrame({
    "record_id": range(1, n_rows + 1),
    "timestamp": pd.date_range("2025-01-01", periods=n_rows, freq="h"),
    "value": np.random.normal(loc=75, scale=10, size=n_rows).round(2),
    # ... add columns matching customer's schema
})

# Add realistic messiness
null_mask = np.random.random(n_rows) < 0.03  # 3% nulls
df.loc[null_mask, "value"] = np.nan

# Label as synthetic
df.attrs["synthetic"] = True
df.attrs["generated"] = datetime.now().isoformat()
df.attrs["generator"] = "hackathon-data-simulator"
```

### Distribution Cheat Sheet

| Real-World Pattern | Distribution | NumPy |
|-------------------|--------------|-------|
| Sensor readings (normal operation) | Normal | `np.random.normal(mean, std, n)` |
| Transaction amounts | Log-normal | `np.random.lognormal(mean, sigma, n)` |
| Time between failures | Exponential / Weibull | `np.random.exponential(scale, n)` |
| Event counts per period | Poisson | `np.random.poisson(lam, n)` |
| Binary outcomes (pass/fail) | Bernoulli / Binomial | `np.random.binomial(1, p, n)` |
| Categorical (product types) | Categorical with weights | `np.random.choice(options, n, p=weights)` |
| Rare events (fraud, defects) | Heavily skewed Bernoulli | `np.random.binomial(1, 0.01, n)` |

---

## Data Quality Simulation

### Messiness Recipe

Don't generate clean data. Add these deliberately:

| Messiness Type | Realistic Rate | How to Inject |
|----------------|---------------|---------------|
| Missing values (nulls) | 2-8% per column | Random null mask |
| Format inconsistencies | 5-10% of string fields | Mixed case, trailing spaces, alternate formats |
| Duplicates | 0.1-1% of rows | Copy random rows with slight timestamp differences |
| Outliers | 1-3% of numeric fields | Values 3-5 standard deviations from mean |
| Stale records | 5-15% of reference data | Old dates, expired statuses not updated |
| Type inconsistencies | 2-5% of typed fields | Numbers stored as strings, date format mix |
| Encoding issues | Rare but impactful | An occasional special character (ü, é, ñ) in name fields |

### Correlation Preservation

Don't just add random noise — maintain realistic relationships:
- If temperature rises, energy consumption should too
- If a machine's maintenance is overdue, its defect rate should be higher
- If a customer has high tenure, they should have more products
- If it's a holiday, transaction volume should spike or drop (depending on industry)

---

## Volume Guidelines

| Context | Recommended Rows | Why |
|---------|-----------------|-----|
| Ideation demo | 50-100 | Just enough to show the concept |
| Build sprint | 200-500 | Enough for meaningful charts and patterns |
| Final demo | 500-1,000 | Convincing scale without slow queries |
| Stress test | 10,000-100,000 | Only if performance is part of the demo |

**Rule:** If your demo query takes more than 3 seconds, your dataset is too large for a live demo. Pre-aggregate or reduce.

---

## Security Rules

### Mandatory Practices

| Rule | Implementation |
|------|---------------|
| No real PII — ever | Generate all names, emails, addresses, phone numbers from Faker |
| Label all synthetic data | Every file: header comment, filename suffix `_synthetic`, metadata attribute |
| Document generation approach | Include a `DATA_GENERATION.md` in the dataset folder |
| Separate from real data | Synthetic data goes in `.hackathon/data/synthetic/`, never mixed with real data paths |
| Reproducible generation | Use fixed random seeds, document all parameters |
| Destroy after hackathon | Synthetic data generated for a specific customer engagement should not be reused elsewhere |

### File Naming Convention

```
{customer_shortcode}_{data_type}_synthetic_{date}.{format}

Examples:
contoso_sensor_readings_synthetic_20260315.parquet
fabrikam_transactions_synthetic_20260315.csv
```

### DATA_GENERATION.md Template

```markdown
# Data Generation Record

- **Generated for:** [Customer / Engagement]
- **Generated date:** [Date]
- **Generated by:** [Agent / Person]
- **Seed:** [Random seed used]
- **Row count:** [N rows]
- **Contains real data:** NO
- **Contains real PII:** NO
- **Generation method:** [Script name or description]
- **Destroy by:** [Date — typically hackathon end + 30 days]
```

---

## Integration Points

| Skill | Integration |
|-------|-------------|
| `engagement-kickstart` | Kickstart identifies data sources needed → simulation fills gaps |
| `industry-tailoring` | Industry-specific schemas and patterns feed simulation design |
| `hackathon-facilitation` | Data readiness is a gate criterion for Build phase |
| `demo-storytelling` | Demo data must support the narrative — simulate data that tells the story |

---

## Anti-Patterns

| Anti-Pattern | Why It Fails | Instead |
|--------------|-------------|---------|
| Perfect data (no nulls, no outliers) | Customer says "our data doesn't look like that" — credibility gone | Add deliberate messiness |
| Generic column names (`col_1`, `value`) | Demo doesn't feel real | Use their terminology, their column names |
| Way too much data (1M rows for a demo) | Slow queries, dashboard timeouts during live demo | 500-1,000 rows. Pre-aggregate for charts. |
| Reusing another customer's synthetic data | Schema doesn't match, industry doesn't fit, feels generic | Generate fresh for each engagement |
| No documentation of generation | Can't reproduce, can't verify, can't audit | Always include DATA_GENERATION.md |
| Realistic-looking PII | Even synthetic PII that "looks real" creates confusion | Use obviously fake patterns (names from fiction, addresses from non-existent streets) while keeping data SHAPES realistic |
