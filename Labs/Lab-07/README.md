# Lab 07 — Model Evaluation: Precision, Recall & Cross-Validation

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Explored advanced model evaluation techniques including precision, recall, and
k-fold cross-validation — learning when each metric matters and why a single
train-test split can be misleading.

## Results
- **Cross-Validation Scores per fold:** [78.77%, 78.09%, 78.65%, 77.53%, 80.34%]
- **Average CV Score:** 78.68%
- **Standard Deviation:** 0.0094 (very stable)

## Knowledge Check — Key Questions & My Answers

**When would you care more about Precision than Recall?**
We prioritize Precision when there is very low tolerance for False Positives — when a
false alarm carries an exceptionally high cost. For example, an automated urgent-notification
filter for phone calls must be highly precise. If it mistakenly flags an important business
meeting or a family emergency as spam and blocks it (a False Positive), the cost of being
wrong is incredibly high.

**When would you care more about Recall than Precision?**
We prioritize Recall when minimizing False Negatives matters most — when it is far safer
to trigger a false alarm than to miss a critical event. For example, a fire department
dispatch model should have high recall. It is vastly preferable to respond to a false alarm
(a cat stuck in a tree) than to miss an actual house fire because the model incorrectly
dismissed the alert.

**Why is cross-validation more trustworthy than a single train-test split?**
Cross-validation ensures the performance score wasn't just the result of a "lucky split"
or an unrepresentative subset of data. By splitting the dataset into multiple folds and
rotating which fold acts as the test set, cross-validation evaluates the model across the
entire dataset. This homogenizes the training and testing phases, ensuring the final score
reflects a balanced distribution of data rather than an accidental bias from a single split.

## What I Learned
- That the right evaluation metric depends entirely on the real-world cost of each error type
- How cross-validation produces a much more reliable performance estimate than a single split
- The practical intuition behind when false positives vs. false negatives are more dangerous

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Google Colab`
