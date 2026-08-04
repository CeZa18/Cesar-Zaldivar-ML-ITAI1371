# Midterm Project — Supervised Learning Pipeline

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## Problem Statement
Built a complete supervised machine learning pipeline to classify outcomes from
structured tabular data, demonstrating the full workflow from raw data exploration
to a trained and evaluated model.

## Approach & Methods
- **Data Preprocessing:** Handled missing values using median imputation for skewed
  features, applied One-Hot Encoding for categorical variables, and scaled numerical
  features where required
- **Exploratory Data Analysis:** Visualized distributions, correlations, and class
  balance to inform preprocessing and modeling decisions
- **Models Trained:** Applied and compared multiple classification algorithms
- **Evaluation:** Used accuracy, precision, recall, and F1-score with macro averaging
  to assess performance fairly across all classes

## Results
The best-performing model achieved strong accuracy on the held-out test set. Evaluation
metrics confirmed the model generalizes beyond the training data without significant overfitting.

## Key Takeaways
- Data quality and preprocessing decisions have a greater impact on final model performance
  than model selection alone
- Matching your evaluation metric to the problem type is as important as the metric value itself
- A well-understood dataset is the foundation of any successful ML pipeline

## Tools Used
`Python` · `scikit-learn` · `pandas` · `Matplotlib` · `Seaborn` · `Google Colab`
