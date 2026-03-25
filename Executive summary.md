# Executive Memo

## Bottom Line Up Front (BLUF)
Replicating Card & Krueger (1994), we confirm that New Jersey's 1992 minimum wage hike
did not reduce fast-food employment relative to Pennsylvania. However, a formal
pre-treatment parallel trends test, never conducted in the original paper, reveals that
NJ's food service employment was already declining relative to PA at 2.56% per year
before the policy took effect. As a result, the wage finding stands on solid ground
while the employment finding should be interpreted with caution.

---

## The Mechanism
Card & Krueger used a **Difference-in-Differences (DiD)** design, a natural experiment
that mimics a randomized trial. Think of NJ and PA as two nearly identical neighboring
states subject to the same economic conditions. NJ raises the minimum wage; PA does not.
If both states were on the same trajectory beforehand, any divergence afterward can be
attributed to the policy. This extension formally tests that "same trajectory" assumption
for the first time, using five years of pre-treatment BLS QCEW data to verify whether NJ
and PA were truly comparable before the 1992 hike.

---

## Visual Evidence
<img width="1288" height="495" alt="download" src="https://github.com/user-attachments/assets/c9ece7af-056d-494b-971b-69abec9f62e3" />

**Figure 1. Event Study Coefficient Plot with Indicative Uncertainty Bands (NJ vs. PA, 1987–1991)**  
*Coefficients show the NJ-PA log gap in each year relative to base year 1991. Left panel:
the wage gap hovers near zero with bands straddling zero, consistent with parallel trends
(p=0.174). Right panel: the employment gap trends steadily away from zero, indicating a
statistically significant pre-trend (p=0.006) that strengthens after population
normalization. Bands are indicative only; formal confidence intervals are not feasible
with n=2 states (Conley & Taber, 2011).*

---

## Policy Implications
The wage result is well-identified and policymakers can draw on it with confidence when
evaluating minimum wage interventions. The employment result, however, warrants caution.
The pre-existing divergence between NJ and PA suggests the DiD estimate may partly
reflect a structural trend already underway rather than the causal effect of the policy.
Future evaluations should adopt a formal parallel trends test and a broader set of
control states as standard practice before drawing causal conclusions from a two-state
comparison.

---

*Full replication code, data sources, and methodology available in the project repository.*  
*Slope test inference follows Conley & Taber (2011). Log specification follows Card & Krueger (1994).*
