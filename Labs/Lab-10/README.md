# Lab 10 — Unsupervised Learning: K-Means Clustering & PCA

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Applied K-Means clustering to the Iris dataset without using labels, used the elbow
method to find the optimal number of clusters, and applied Principal Component Analysis
(PCA) to reduce the 4-dimensional dataset to 2D for visualization.

## Knowledge Check — Key Questions & My Answers

**What is the fundamental difference between supervised and unsupervised learning?**
- **Supervised learning:** Data is classified with labels and maps an input to a known
  target output. Example: a model trained on labeled images to identify objects.
- **Unsupervised learning:** Data has no labels — the model looks for intrinsic structures,
  patterns, or groupings within the input data alone. Example: a model that groups objects
  without being told what they are.

**Why don't we just choose the largest possible k to get the lowest inertia?**
Choosing the largest possible k creates additional centers that divide clusters into
unnecessarily small groups — introducing noise and contaminating the analysis. It leads
to overfitting: every point becomes its own cluster, which is meaningless. The "elbow"
method helps find the point of diminishing returns — where adding more clusters gives
negligible improvement while overcomplicating the model.

**The first two PCA components explained over 95% of the variance — what does this tell you?**
It tells us that these two components capture the directions in which the majority of data
variation occurs. This high percentage indicates the original four features are highly
correlated with one another, meaning the other two dimensions can be discarded and the data
compressed into 2D with almost zero meaningful information loss.

## What I Learned
- The core distinction between supervised and unsupervised learning paradigms
- How to use the elbow method to select k without ground truth labels
- How PCA reduces dimensionality while preserving the vast majority of variance

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Matplotlib` · `Google Colab`
