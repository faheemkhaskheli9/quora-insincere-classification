# Evaluation Notes: Insincere Question Classification

## Metrics

Precision/recall/F1 for the positive (insincere) class, plus the full
confusion matrix -- computed by the shared
`quora_insincere.evaluation.evaluate_predictions` function so every model in
this repo (baseline, LSTM, Transformer/BERT) is scored identically and stays
directly comparable below.

## Reproducing Results

```bash
PYTHONPATH=src python -m quora_insincere --train-baseline \
    --data examples/sample_questions.csv --model-out models/baseline_tfidf_logreg.joblib
```

## Result Log

| Date | Model | Precision | Recall | F1 | Support | Confusion Matrix | Notes |
|------|-------|-----------|--------|----|---------|-------------------|-------|
| 2026-09-12 | baseline (TF-IDF + LogisticRegression) | 1.000 | 1.000 | 1.000 | 15 | TP=7 FP=0 FN=0 TN=8 | Held-out 25% split of the 60-row bundled `examples/sample_questions.csv` sample, not the full Kaggle dataset -- a perfect score here is expected on this small, clean sample and is not representative of performance on the real (much larger, noisier) corpus. Re-run against the Kaggle CSV once downloaded locally. |
