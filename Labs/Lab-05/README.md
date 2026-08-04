# Lab 05 — Data Preprocessing & Feature Engineering

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Applied core preprocessing techniques to the Titanic dataset including missing value
imputation, categorical encoding, and feature scaling — preparing raw data into a
clean, model-ready format.

## Results
- **Survival Prediction Accuracy:** 74.83%
- Macro F1-Score: 0.74

## Knowledge Check — Key Questions & My Answers

**Why is it often better to impute missing values with the median instead of the mean?**
Imputing missing values with the median is preferred when dealing with skewed data
(such as income or age) because the median is robust against outliers. Outliers can
heavily pull the mean away from the true center of the distribution, while the median
simply represents the exact middle value — providing a more accurate representation
of central tendency for non-normal distributions.

**What does One-Hot Encoding do and why is it necessary?**
One-Hot Encoding converts categorical data into a series of binary columns (0 or 1),
creating a new column for each unique category within a feature. This is necessary
because most machine learning algorithms operate on mathematical equations and matrix
multiplication — they cannot directly interpret raw text strings. It is especially
useful for nominal data (like gender or color) where no inherent mathematical order
exists between categories.

**Would you need to apply Feature Scaling to a Decision Tree model?**
No. Decision Trees make decisions by selecting a feature and a threshold value to split
the data. Because the model evaluates each feature independently based on order rather
than magnitude, changing the absolute scale of the values will not change where or how
the splits are made.

## What I Learned
- That data quality and preprocessing decisions often matter more than model selection
- When to use median vs. mean imputation and why it matters for skewed data
- The mechanics behind One-Hot Encoding and why tree-based models don't need scaling

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Google Colab`
