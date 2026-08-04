# Final Project — Mental Health Sentiment Classification

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## Problem Statement
Can a machine learning classifier, trained on TF-IDF features from social media posts, accurately identify whether a post reflects stable, moderate, or severe mental health sentiment? This project explores whether natural language patterns in user-generated text can serve as a scalable, automated screening signal for mental health platforms.

## Dataset
- **Source:** Kaggle Mental Health Corpus (53,043 posts across 7 conditions)
- **Sample used:** 14,712 posts after null removal and deduplication
- **Classes:** Stable (31.5%), Moderate/12.2%), Severe (56.3%)

## Approach & Methods
- **Preprocessing:** 8-step text cleaning pipeline (lowercase, URL/mention/emoji removal, punctuation, stopwords, normalization)
- **Feature Extraction:** TF-IDF with 5,000 features, unigrams + bigrams, `sublinear_tf=True`
- **Models trained:** Logistic Regression, Multinomial Naive Bayes, LinearSVC
- **Class imbalance:** Addressed via `class_weight='balanced'` on LR and SVC; macro F1 used as primary metric

## Results

| Model | Accuracy | Macro F1 | Macro Recall |
|-------|----------|----------|--------------|
| **Logistic Regression** | **87.63%** | **0.8454** | **0.8669** |
| LinearSVC | 87.87% | 0.8384 | 0.8413 |
| Multinomial NB | 75.20% | 0.6643 | 0.6175 |

**Best model: Logistic Regression** — selected for highest macro F1 and recall, plus probability output support for confidence-threshold triage.

## Key Takeaways
1. Class imbalance handling (`class_weight='balanced'`) was as impactful as model selection
2. Moderate posts were consistently the hardest to classify — smallest class, most ambiguous vocabulary
3. TF-IDF with bigrams effectively captured clinical language patterns without requiring large language models
4. 87.6% accuracy with 12.4% error rate — most errors occur at class boundaries (Moderate↔Severe), which is clinically expected

## Tools Used
`Python` · `scikit-learn` · `pandas` · `Matplotlib` · `Seaborn` · `WordCloud` · `Google Colab`
