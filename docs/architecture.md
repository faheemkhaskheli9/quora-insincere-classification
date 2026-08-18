# Architecture Notes: Insincere Question Classification

## Pipeline

```text
Text -> Tokenization/Embedding -> Model (TF-IDF+LR / LSTM / Transformer / BERT) -> Classification -> Metrics
```

## Components

- TF-IDF + Logistic Regression baseline
- LSTM model
- Transformer model
- BERT fine-tuning
- Precision/recall/F1 analysis

## Design Notes

- Keep provider/model choices swappable behind interfaces (see `multi-llm-router`
  and similar projects in this portfolio for the general pattern).
- Prefer configuration-driven pipelines (YAML/JSON in `configs/`) over hardcoded
  parameters so experiments are reproducible.
