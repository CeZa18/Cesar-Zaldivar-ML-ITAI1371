# Lab 12 — Natural Language Processing (NLP)

## What I Did
Preprocessed raw text data through tokenization, stopword removal, and vectorization using TF-IDF. Trained a text classifier and evaluated its performance on a text dataset.

## What I Learned
- How to convert raw text into numerical feature vectors that machine learning models can use
- The difference between bag-of-words and TF-IDF — TF-IDF penalizes common words and rewards rare, informative ones
- How bigrams (two-word combinations) capture more context than unigrams alone

## Challenges
Understanding why `fit_transform` must only be applied to training data and `transform` to test data — fitting on test data causes data leakage, artificially inflating results.
