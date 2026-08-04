# Lab 06 — Regression vs. Classification

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Trained and compared both a regression model (predicting continuous fare prices)
and a classification model (predicting binary survival outcomes) on the Titanic
dataset, evaluating each with its appropriate metric.

## Results
- **Classification Accuracy (Survival Prediction):** 74.83%

## Knowledge Check — Key Questions & My Answers

**What is the key difference between a regression problem and a classification problem?**
The key difference is the type of output. A **regression** problem predicts values in a
continuous pattern — like house prices or future temperatures. A **classification**
problem categorizes data into distinct groups — like interpreting pixels in an image to
recognize a frog from a bird.

**What do the `.coef_` values represent in a LinearRegression model?**
These coefficients represent the weights (slopes) of the features — in this case Age
and Class. They show the direction and strength of the relationship between each feature
and the target variable (Fare). Specifically:
- For each additional year of age, the model predicts the ticket price drops by ~$0.46.
- Moving down one ticket class (e.g., 1st to 2nd) predicts a ticket price drop of ~$37.92.

**Why use MSE for regression but accuracy for classification?**
MSE (Mean Squared Error) measures how far predicted values are from actual values — well
suited for models predicting continuous values with no upper or lower limit.
Accuracy normalizes results between 0 and 1, fitting best for classification models where
results are evaluated in a binary or categorical context. Accuracy would not work for fare
prediction because the model predicts continuous values with no fixed bounds.

## What I Learned
- The fundamental distinction between regression and classification tasks
- How to interpret model coefficients as real-world relationships between features
- Why matching your evaluation metric to your problem type is critical

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Matplotlib` · `Google Colab`
