# Minimum Wages and Employment: A DiD Replication & Parallel Trends Extension
**Track:** Track A — The Causal Policy Track (Difference-in-Differences)  
**Paper:** Card, D., & Krueger, A. B. (1994). Minimum Wages and Employment: A Case Study of the Fast-Food Industry in New Jersey and Pennsylvania. [📄 Paper PDF](https://davidcard.berkeley.edu/papers/njmin-aer.pdf)  
**Data:** `public.dat` — [Download from David Card's site](https://davidcard.berkeley.edu/data_sets/njmin.zip)  
**Extension Data:** BLS QCEW SIC-Based Annual Singlefiles, 1987–1991 — [Download from BLS](https://www.bls.gov/cew/downloadable-data-files.htm)

---

## Main Causal Question
Did New Jersey's April 1992 minimum wage increase (from $4.25 to $5.05/hour) cause a reduction in fast-food employment, as standard competitive labor market theory predicts? Using Pennsylvania fast-food restaurants as a control group, Card and Krueger compare employment changes before and after the policy change in a difference-in-differences (DiD) framework. Contrary to the classical prediction, they find that employment in New Jersey increased slightly relative to Pennsylvania, challenging the conventional view that minimum wage hikes reduce low-wage employment.

---

## Phase 3 Extension: Formal Pre-Treatment Parallel Trends Test
The entire validity of Card & Krueger's DiD estimate rests on the **parallel trends assumption** — that NJ and PA would have followed similar wage and employment trajectories absent the 1992 minimum wage hike. Critically, the original paper never formally tests this assumption.

This extension fills that gap using **BLS QCEW annual data** for the Eating and Drinking Places sector (SIC 5810) from **1987–1991**, applying a log-scale slope trend test consistent with Card & Krueger's own specification:

> Δlog(Y)_t = α + β·t + ε_t

where a statistically significant β indicates a pre-existing differential trend and a violation of the parallel trends assumption. As a robustness check, employment is further normalized by state population using **U.S. Census Bureau intercensal estimates** to ensure any detected divergence reflects genuine labor market dynamics rather than demographic composition differences between the two states.

### Key Findings
| Outcome | β (slope) | p-value | Conclusion |
|---|---|---|---|
| Log Wage Gap | +0.33%/yr | 0.174 | ✅ Fail to reject — parallel trends hold |
| Log Employment Gap (raw) | −2.56%/yr | 0.006 | ❌ Reject — pre-trend detected |
| Log Employment Gap (normalized) | −2.85%/yr | 0.002 | ❌ Reject — pre-trend confirmed robust |

The extension **contextualizes** rather than invalidates Card & Krueger's findings: their wage result stands on solid identification ground, while their employment result warrants caution given a pre-existing structural divergence in NJ−PA employment trajectories that population normalization only strengthens.

---

## Repository Structure
```
├── README.md
├── .gitignore
├── /data
│   ├── /raw                        # Immutable original files
│   └── /processed                  # Cleaned output files
└── /notebooks
    ├── 01_Data_Cleaning.ipynb
    ├── 02_Replication_Analysis.ipynb
    └── 03_Extension_and_Results.ipynb
```

---

## References
- Card, D., & Krueger, A. B. (1994). Minimum Wages and Employment. *American Economic Review*, 84(4), 772–793.
- Conley, T. G., & Taber, C. R. (2011). Inference with "Difference in Differences" with a Small Number of Policy Changes. *Review of Economics and Statistics*, 93(1), 113–125.
- Dube, A., Lester, T. W., & Reich, M. (2010). Minimum Wage Effects Across State Borders. *Review of Economics and Statistics*, 92(4), 945–964.
- U.S. Census Bureau. State Intercensal Population Estimates, 1980–1990 and 1990–2000.
- U.S. Bureau of Labor Statistics. Quarterly Census of Employment and Wages (QCEW), SIC-Based Annual Singlefiles.
