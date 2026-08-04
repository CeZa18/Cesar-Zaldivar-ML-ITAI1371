# Lab 08 — Bias, Variance & the Overfitting Problem

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Explored the concepts of underfitting and overfitting using polynomial regression
models of varying degrees, and analyzed learning curves to understand how training
and validation scores reveal model complexity problems.

## Knowledge Check — Key Questions & My Answers

**Which model (degree 1, 4, or 15) is underfitting, which is overfitting, and which is a good fit?**
- **Degree 1 → Underfitting:** Plots a straight line that misses the signal entirely.
  It captures the general directional decline but is too simple to capture the curving
  sine wave pattern.
- **Degree 15 → Overfitting:** The line looks shaky with many sharp shifts — overly
  complex, capturing noise rather than the true underlying trend.
- **Degree 4 → Good Fit:** A smoother line that fits the data points consistently
  without overreacting to noise. The right balance of complexity.

**What does the learning curve for the underfitting model tell you?**
Both the training and cross-validation scores converge to a low score very quickly.
This tells us the model has **high bias** — it is too simple, and adding more training
data will not improve its performance.

**What does the learning curve for the overfitting model tell you?**
There is a large gap between the high training score and the much lower cross-validation
score. This tells us the model has **high variance** — it has memorized the training set
perfectly but fails to generalize to new, unseen data.

## What I Learned
- The visual intuition for identifying underfitting, overfitting, and a good fit
- How learning curves diagnose high-bias vs. high-variance problems
- Why model complexity must be tuned — too simple misses the signal, too complex
  memorizes noise

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Matplotlib` · `NumPy` · `Google Colab`
