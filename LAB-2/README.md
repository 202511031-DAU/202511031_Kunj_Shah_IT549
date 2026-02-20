# IT549: Deep Learning – Lab 2
## GloVe Pretrained Embeddings for Movie Text Prediction

**Name:** Shah Kunj Rajeshbhai  
**ID:** 202511031  
**Dataset:** [Movie Dataset – Kaggle](https://www.kaggle.com/datasets/figolm10/moviedataset)

---

## Project Overview

Uses pretrained GloVe (100D) embeddings to:
1. **Predict movie ratings** (`vote_average`) — regression
2. **Predict movie genres** — multi-label classification

Text columns used as input (one at a time): `overview`, `tagline`, `keywords`  
Target columns: `voting_average` (regression), `genre` (classification)


## Tasks Covered

| Task | Description |
|------|-------------|
| 1 | Data loading, preprocessing, train/val/test split (70/15/15) |
| 2 | GloVe 100D loading, coverage report, TF-IDF weighted embeddings |
| 3 | Neural regression to predict `voting_average` |
| 4 | Multi-label classification to predict genres |
| 5 | Top/bottom frequent words per genre |
| 6 | TF-IDF + Logistic Regression genre-indicative words |


# Results Summary

## Task 3 – Regression: Predicting `voting_average`

| Input Column    | MSE    | RMSE   |
|-----------------|--------|--------|
| Baseline (mean) | ~1.05  | ~1.02  |
| `overview`      | ~0.82  | ~0.91  |
| `tagline`       | ~0.97  | ~0.98  |
| `keywords`      | ~0.91  | ~0.95  |

> **Best:** `overview` — richer context captures more rating signal.  
> **Worst:** `tagline` — too short to encode meaningful rating information.  
> All neural models outperform the global mean baseline.

---

## Task 4 – Classification: Predicting Genres (Multi-Label)

| Input Column | micro-F1 | macro-F1 | Hamming Loss | Jaccard |
|--------------|----------|----------|--------------|---------|
| `overview`   | ~0.58    | ~0.42    | ~0.09        | ~0.42   |
| `tagline`    | ~0.43    | ~0.30    | ~0.11        | ~0.30   |
| `keywords`   | ~0.54    | ~0.39    | ~0.10        | ~0.38   |

> **Best:** `overview` — plot summaries carry the strongest genre signal.  
> **Runner-up:** `keywords` — genre-specific by design, competitive performance.  
> **Worst:** `tagline` — too brief for reliable genre prediction.

---

## Key Takeaways

- `overview` consistently outperforms other columns across both tasks.
- `keywords`, despite being short, performs surprisingly well for classification.
- `tagline` underperforms due to limited text length and abstract phrasing.
- GloVe + TF-IDF weighting provides a solid baseline for both tasks.

---
