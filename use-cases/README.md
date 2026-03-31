← [README](../README.md)

# Use Cases

This directory holds all individual use case work during the hackathon. Each use case gets its own folder.

---

## Use Case Lifecycle

```
Brainstorm → Canvas → Score → Select → Scope → Build → Demo
```

1. **Brainstorm** — Generate ideas (facilitated during ideation session)
2. **Canvas** — Structure each idea using the Use Case Canvas template
3. **Score** — Rate feasibility using the Scorecard
4. **Select** — Choose which use cases to build
5. **Scope** — Define the demo-able slice
6. **Build** — Implement the solution (accelerators + custom code)
7. **Demo** — Present in final customer demo

## Structure

Each use case folder follows this pattern:

```
use-cases/
├── uc-1-predictive-maintenance/
│   ├── README.md                  (overview)
│   ├── use-case-canvas.md         (filled template)
│   ├── feasibility-scorecard.md   (filled template)
│   ├── implementation/            (code, notebooks, configs)
│   ├── demo-script.md             (filled demo template)
│   └── assets/                    (images, test data)
├── uc-2-customer-churn/
│   └── ...
└── _template.md  ← Copy this to start a new use case
```

## Getting Started

1. **Brainstorm phase:** Use [`templates/use-case-canvas.md`](../templates/use-case-canvas.md) to structure ideas
2. **Scoring phase:** Use [`templates/feasibility-scorecard.md`](../templates/feasibility-scorecard.md) to evaluate
3. **Build phase:** Create a folder, implement the scoped slice
4. **Demo phase:** Use [`templates/demo-script-template.md`](../templates/demo-script-template.md) to structure the presentation

---

## 📎 Related

| Document | Purpose |
|----------|---------|
| [Use-Case-Driven Development](../docs/concepts/use-case-driven-development.md) | Core methodology behind the use case approach |
| [Use Case Prioritization](../docs/concepts/use-case-prioritization.md) | How to rank and select use cases |
| [Templates](../templates/) | Canvas, scorecard, and demo script templates |
| [Running Ideation](../docs/guides/running-ideation.md) | Facilitation guide for the ideation session |
