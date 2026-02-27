# Minimum Wages and Employment: A Difference-in-Differences Replication

## Track & Paper

**Track:** Track A — The Causal Policy Track (Difference-in-Differences)

**Paper:** Card, D., & Krueger, A. B. (1994). *Minimum Wages and Employment: A Case Study of the Fast-Food Industry in New Jersey and Pennsylvania.* The American Economic Review, 84(4), 728–748.

📄 [Link to Original Paper (PDF)](https://davidcard.berkeley.edu/papers/njmin-aer.pdf)

---

## Main Causal Question

The paper asks: **Did New Jersey's April 1992 minimum wage increase (from $4.25 to $5.05/hour) cause a reduction in fast-food employment, as standard competitive labor market theory predicts?**

Using Pennsylvania fast-food restaurants as a control group, Card and Krueger compare employment changes before and after the policy change in a difference-in-differences (DiD) framework. Contrary to the classical prediction, they find that employment in New Jersey *increased* slightly relative to Pennsylvania, challenging the conventional view that minimum wage hikes reduce low-wage employment.

---

## Data Source

- **Source:** [David Card's Public Data Sets — UC Berkeley](https://davidcard.berkeley.edu/data_sets.html)
- **File:** `public.dat` (the New Jersey–Pennsylvania fast-food survey dataset)
- **Description:** A telephone survey of ~410 fast-food restaurants (Burger King, KFC, Wendy's, Roy Rogers) in New Jersey and eastern Pennsylvania, conducted in two waves:
  - **Wave 1 (Before):** February–March 1992 — prior to NJ minimum wage increase
  - **Wave 2 (After):** November–December 1992 — ~8 months after the NJ increase
- **Key Variables:** Full-time equivalent (FTE) employment, starting wage, hours open, chain, whether NJ or PA, and various store characteristics.

---

## Project Structure

```
.
├── README.md               # This file
├── data/
│   └── public.dat          # Raw data from Card & Krueger (1994)
├── notebooks/
│   └── analysis.ipynb      # Main DiD analysis notebook
├── scripts/
│   └── clean.py            # Data cleaning and FTE construction
└── outputs/
    └── figures/            # Plots (parallel trends, event study, etc.)
```

---

## Methodology Overview

This replication follows the **Difference-in-Differences** design:

| | Before (Feb–Mar 1992) | After (Nov–Dec 1992) | Difference |
|---|---|---|---|
| **New Jersey** (treated) | Employment_NJ_pre | Employment_NJ_post | ΔNJ |
| **Pennsylvania** (control) | Employment_PA_pre | Employment_PA_post | ΔPA |
| **DiD Estimate** | | | **ΔNJ − ΔPA** |

Key empirical checks include:
- Parallel pre-trends validation (placebo tests)
- Robustness to alternative control groups
- Heterogeneity analysis by initial wage distribution

---

## Citation

> Card, D., & Krueger, A. B. (1994). Minimum Wages and Employment: A Case Study of the Fast-Food Industry in New Jersey and Pennsylvania. *The American Economic Review*, 84(4), 728–748.
