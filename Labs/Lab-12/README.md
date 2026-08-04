# Lab 12 — AI Fairness & Bias in Machine Learning

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Analyzed a trained income classification model for demographic bias by computing
subgroup accuracy, False Positive Rate (FPR), False Negative Rate (FNR), and
True Positive Rate (TPR) separately for male and female groups.

## Fairness Audit Results
| Metric | Male | Female |
|---|---|---|
| Accuracy | 81.20% | 91.81% |
| False Positive Rate (FPR) | 10.26% | 2.81% |
| False Negative Rate (FNR) | 37.80% | 47.84% |
| True Positive Rate (TPR) | 62.20% | 52.16% |

**TPR Fairness Gap: 10.04% ❌ Significant disparity (gap > 10%)**

## Knowledge Check — Key Questions & My Answers

**Is there a significant difference in how the model performs for males vs. females?**
At first glance, the model appears more accurate for the female group (91.81% vs. 81.20%).
However, running the TPR Fairness Comparison reveals a more concerning picture — both
groups have a TPR below 70%, meaning the model misses a significant portion of creditworthy
applicants in both groups.

**Which group has a higher False Positive Rate and what is the real-world consequence?**
The male group has a higher FPR (10.26% vs. 2.81%). In a loan application context, a False
Positive means predicting high income when the applicant does not qualify — potentially
granting loans to unqualified candidates, creating financial risk for the lender.

**Would you approve this model for a hiring process?**
**No.** In a hiring context, a False Negative (FNR) is more harmful — a qualified person
gets screened out of the process. The FNR for the female group is 47.84% compared to 37.80%
for males, meaning qualified female candidates are screened out at a disproportionately higher
rate. High overall accuracy does not mean the model is fair.

**Would removing the 'sex' column make the model fair?**
No. This approach — "Fairness Through Unawareness" — is often naive and insufficient.
Several other columns are statistically correlated with gender (such as `marital-status`
and `relationship`), meaning the model can reconstruct gender patterns through proxy
variables and recreate the same bias indirectly.

## What I Learned
- That high accuracy can mask serious fairness disparities at the subgroup level
- Why removing a sensitive feature alone does not eliminate bias due to proxy variables
- How to evaluate a model with fairness-specific metrics (FPR, FNR, TPR gap)
- The real-world consequences of deploying biased models in high-stakes decisions

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Google Colab`
