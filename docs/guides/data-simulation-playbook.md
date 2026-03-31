← [Docs](../index.md) | [Guides](./)

# Data Simulation Playbook

Real customer data is the best demo prop. But access is often delayed, restricted, or impossible. **Data simulation** lets you build and demo with realistic synthetic data when the real thing isn't available — without losing 4 hours to a data pipeline that goes nowhere.

---

## When to Simulate

| Scenario | Simulate? | Why |
|----------|:---------:|-----|
| Real data delayed (IT approval) | Yes | Build PoC with synthetic, swap when real arrives |
| Data is sensitive (PII, medical) | Yes | Simulate, demo with synthetic, scale with real later |
| No real data exists (greenfield) | Yes | Synthetic is the only option |
| Real data available in 2 hours | No | Wait — 2 hours of PoC isn't worth the distraction |

---

## Simulation Strategies

Choose based on **how much you know** about the customer's data:

| Strategy | When to use | Tools | Time |
|----------|------------|-------|:----:|
| **Random values** | Testing code paths; don't care about realism | `numpy.random` | 5 min |
| **Statistical distributions** | You know the range and shape | `numpy`, `scipy.stats` | 15 min |
| **Time-series patterns** | Need temporal correlation (trend, seasonality) | `numpy` + rolling aggregates | 30 min |
| **Domain generators** | Need industry-specific realism | `faker`, custom generators | 60 min |
| **SDV (Synthetic Data Vault)** | You have sample data and want to synthesize more | `sdv` library | 45 min |

---

## Strategy Examples

### Random Values (Fastest)

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    'sensor_id': np.random.randint(1000, 2000, 100),
    'temperature': np.random.uniform(20, 120, 100),
    'vibration': np.random.uniform(0, 500, 100),
    'timestamp': pd.date_range('2024-01-01', periods=100, freq='H')
})
```

**Cons:** Looks fake. No realistic patterns. **Pros:** Fast. Works for code testing.

### Statistical Distributions (Realistic ranges)

```python
import numpy as np

temps = np.random.normal(loc=55, scale=8, size=500)       # Bell curve
vibration = np.random.exponential(scale=100, size=500)     # Right-skewed
```

Common distributions:
- **Normal:** bell curve (sensor readings)
- **Exponential:** right-skewed (costs, time-to-failure)
- **Poisson:** count data (events per day)
- **Log-normal:** money amounts (transactions)

### Time-Series Patterns (Trend + seasonality)

```python
hours = 365 * 24
t = np.arange(hours)

trend = 50 + 0.01 * t                          # Rising over time
seasonality = 10 * np.sin(2 * np.pi * t / 24)  # 24-hour cycle
noise = np.random.normal(0, 2, hours)

temperature = trend + seasonality + noise
```

Common patterns:
- **Trend:** `base + slope * t`
- **Seasonality:** `amplitude * sin(2π * t / period)`
- **Anomalies:** inject spikes at random intervals
- **Autocorrelation:** `value[t] = 0.8 * value[t-1] + noise`

### Industry-Specific Generators

**Manufacturing:** Sensors with baselines per equipment, daily temperature cycles, occasional anomalies.

**Retail:** Sales with weekend boosts, seasonal trends, product-level variation.

**Financial:** Transactions with log-normal amounts, variable daily volumes, category mix.

### SDV (From Sample Data)

If you have **any sample data** (even 100 rows), SDV synthesizes more with the same distributions:

```python
from sdv.tabular import GaussianCopula

model = GaussianCopula()
model.fit(real_data)
synthetic = model.sample(n=5000)
```

---

## Best Practices

### Match the Schema

Use the customer's exact column names, types, and realistic ranges — not generic `col1`, `col2`.

### Maintain Referential Integrity

If data has relationships (sensors → readings, products → sales), generate parent records first, then child records that reference valid parents.

### Temporal Realism

Use regular intervals (`pd.date_range`) not random timestamps. Real sensor data arrives at predictable frequencies.

### Document Assumptions

Add a `schema.yaml` describing columns, distributions, ranges, and units. Future users need to know what's synthetic.

---

## Where to Store Generated Data

```
data/
├── schema.yaml          ← Column descriptions and distributions
├── sample-sensors.csv   ← Generated dataset
├── simulation.py        ← Generation script (reproducible)
└── README.md            ← Why this data was chosen
```

---

## When NOT to Simulate

| Scenario | What to do instead |
|----------|-------------------|
| Customer data available (even if delayed 2 hours) | Wait — real data is always more convincing |
| Use case depends on patterns you don't understand | Ask customer for a sample before hackathon |
| Demo must show customer's actual results | Schedule for pilot, not hackathon |

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Use-Case-Driven Development](../concepts/use-case-driven-development.md) | Why data quality matters to use case credibility |
| [Accelerator Development](accelerator-development.md) | Including sample data in reusable packs |
| [Scope Management](../principles/scope-management.md) | When to cut a use case vs. building with simulated data |
