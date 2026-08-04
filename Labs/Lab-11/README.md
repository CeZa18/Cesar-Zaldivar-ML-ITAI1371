# Lab 11 — Hyperparameter Tuning & AutoML

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Explored systematic hyperparameter optimization using Grid Search and Random Search,
then used AutoGluon's AutoML framework to automatically train and rank multiple model
types on the Iris dataset.

## AutoGluon Leaderboard Results (Top Models)
| Model | Test Accuracy | Validation Accuracy |
|---|---|---|
| XGBoost | 100.00% | 95.24% |
| ExtraTreesGini | 100.00% | 90.48% |
| NeuralNetTorch | 95.56% | 95.24% |
| LightGBM | 95.56% | 85.71% |

## Knowledge Check — Key Questions & My Answers

**What is the difference between a model parameter and a hyperparameter?**
**Parameters** are sets of information learned from data when the model trains
(e.g., coefficients in regression models). **Hyperparameters** are settings chosen by
the practitioner before training is executed to steer the learning behavior
(e.g., `penalty`, `max_depth`).

**When would you choose Grid Search over Random Search, and vice versa?**
- **Grid Search** is better when there are a small number (2–3) of high-impact
  hyperparameters. It is guaranteed to find the best combination but can be costly
  and slow. Best for datasets with low counts of different values.
- **Random Search** is more efficient — it tries random samples from a fixed number of
  combinations, covering the space efficiently. Best used to find a good combination
  fast when you have many hyperparameters, though it will not find the absolute best.

**Which model performed best in the AutoGluon leaderboard?**
**XGBoost** (along with several tree-based models like ExtraTrees) performed the best,
achieving 100% test accuracy and 95.24% validation accuracy. AutoML is incredibly powerful
because it automates the entire ML pipeline — data preprocessing, feature engineering,
trying multiple model types, tuning hyperparameters, and combining them into an optimized
ensemble — saving massive amounts of manual experimentation time.

## What I Learned
- The distinction between parameters (learned) and hyperparameters (set before training)
- When to apply Grid Search vs. Random Search based on search space size
- How AutoML frameworks like AutoGluon can outperform manual tuning with a fraction of the effort

## Tools Used
`Python` · `scikit-learn` · `AutoGluon` · `Google Colab`
