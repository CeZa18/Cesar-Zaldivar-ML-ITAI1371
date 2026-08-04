# Lab 09 — Ensemble Methods: Decision Trees & Random Forests

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Compared a single Decision Tree against a Random Forest ensemble on the Iris dataset,
analyzed feature importance scores, and validated findings with statistical analysis
of each species' petal and sepal measurements.

## Knowledge Check — Key Questions & My Answers

**What is the main idea behind ensemble methods?**
In the ensemble method, models cover for each other's weaknesses. The committee approach
works by voting on the correct responses, canceling errors out. A single "expert" model
has blind spots — given high variance, it can tend to overreact to noise. A committee
of diverse models corrects for this collectively.

**Which model performed better — the Decision Tree or the Random Forest?**
As expected, the **Random Forest** performed better — even with a `max_depth=2` limitation
— due to the ensemble's voting mechanism. Multiple trees, each trained on a random subset,
collectively outperform any single tree.

**Which two features were most important for classifying the iris flowers?**
**Petal width** and **petal length** did most of the heavy lifting. I validated this
mathematically by analyzing the mean values for each species:
- For sepal width/length, the means between Versicolor and Virginica are nearly identical,
  meaning a single split struggles to separate them.
- For petal length and width, there are massive jumps between species:
  - Setosa: ~1.46 cm petal length
  - Versicolor: ~4.26 cm
  - Virginica: ~5.55 cm

This statistical gap explains exactly why the tree targets petal dimensions first.

## What I Learned
- How ensemble voting reduces the impact of individual model errors
- Why petal measurements are far more discriminative than sepal measurements for
  classifying Iris species
- How to validate feature importance scores with statistical analysis

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Matplotlib` · `Google Colab`
