# Stage 2: Machine Learning

<span class="stage-badge">2</span> Learn how models learn from data, how they fail, and how to evaluate them honestly.

## Goal

Classic machine learning teaches the habits that deep learning and LLM work
still require: baselines, splits, metrics, feature quality, leakage checks, and
error analysis.

## Learn

| Topic | What matters |
|---|---|
| Supervised learning | regression, classification, loss functions, features |
| Unsupervised learning | clustering, dimensionality reduction, embeddings intuition |
| Evaluation | accuracy, precision, recall, F1, ROC-AUC, calibration, confusion matrix |
| Data leakage | train/test contamination, target leakage, time leakage |
| Error analysis | slice errors by group, input type, length, source, or difficulty |
| Baselines | simple model first, complex model later |

## Build

Build an ML baseline report:

- choose a tabular, text, or image dataset
- train a simple baseline
- train one stronger model
- compare metrics and error slices
- write what failed and what you would try next

## Measure

Measure:

- primary metric
- baseline vs improved model
- train vs validation gap
- at least 3 error categories

## Exit Criteria

Move on when you can:

- explain underfitting and overfitting
- choose metrics for a problem
- identify likely data leakage
- write a short model card for your baseline
- explain why a simpler model may be better in production

## Suggested Tools

- scikit-learn
- pandas
- Jupyter or VS Code notebooks
- Weights and Biases, MLflow, or a simple CSV experiment log

## Next

Continue to [Stage 3: Deep Learning](03-deep-learning.md).
