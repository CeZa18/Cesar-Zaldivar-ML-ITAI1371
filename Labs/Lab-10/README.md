# Lab 10 — Neural Networks & Deep Learning

## What I Did
Built and trained a basic neural network using scikit-learn's MLPClassifier, experimenting with hidden layer sizes, activation functions, and learning rates to observe their effect on convergence and accuracy.

## What I Learned
- The structure of a neural network: input layer, hidden layers, and output layer
- How backpropagation adjusts weights to minimize prediction error
- The tradeoff between network complexity and training time — deeper networks are more powerful but much slower to train

## Challenges
Getting the neural network to converge required careful tuning of `max_iter` and `learning_rate` — the default settings often resulted in a ConvergenceWarning.
