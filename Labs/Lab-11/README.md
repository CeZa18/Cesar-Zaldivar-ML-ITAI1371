# Lab 11 — Hyperparameter Tuning & AutoML

## What I Did
Applied GridSearchCV and RandomizedSearchCV to systematically find optimal hyperparameters for classification models. Also explored AutoML concepts to understand how parameter search can be automated.

## What I Learned
- The difference between model parameters (learned during training) and hyperparameters (set before training)
- How GridSearch exhaustively tests all combinations while RandomizedSearch samples a subset — the latter being far faster on large grids
- How cross-validation within the search prevents overfitting the hyperparameter choices to a single split

## Challenges
GridSearchCV with many hyperparameters and a large dataset is computationally expensive — learning to narrow down the search space intelligently was an important takeaway.
