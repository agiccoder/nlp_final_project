# Final Project Results Summary

## Standard performance

| model                        | split   |   accuracy |   macro_f1 |   weighted_f1 |   mean_confidence |
|:-----------------------------|:--------|-----------:|-----------:|--------------:|------------------:|
| TF-IDF + Logistic Regression | test    |   0.847778 |   0.847883 |      0.847883 |          0.760712 |
| Frozen DistilBERT emb + LR   | test    |   0.724444 |   0.725724 |      0.725724 |          0.931769 |
| Fine-tuned DistilBERT        | test    |   0.851111 |   0.850699 |      0.850699 |          0.894473 |


## Robustness results

| model                  |   original |   product_cue_masked |   top_tfidf_feature_masked |   drop_product_cue_masked |   drop_top_tfidf_feature_masked |
|:-----------------------|-----------:|---------------------:|---------------------------:|--------------------------:|--------------------------------:|
| Fine-tuned DistilBERT  |   0.850699 |             0.718631 |                   0.46267  |                 0.132068  |                        0.388029 |
| TF-IDF + LR            |   0.847883 |             0.780107 |                   0.664319 |                 0.0677766 |                        0.183565 |
| Frozen DistilBERT + LR |   0.725724 |             0.576189 |                   0.256557 |                 0.149534  |                        0.469166 |


## Calibration summary

| model                  |       ece |   mean_confidence |   accuracy |   macro_f1 |
|:-----------------------|----------:|------------------:|-----------:|-----------:|
| Fine-tuned DistilBERT  | 0.0433621 |          0.894473 |   0.851111 |   0.850699 |
| TF-IDF + LR            | 0.0870662 |          0.760712 |   0.847778 |   0.847883 |
| Frozen DistilBERT + LR | 0.207325  |          0.931769 |   0.724444 |   0.725724 |


## Retrieval support summary

| support_bin     |   n |   accuracy |   mean_confidence | model                  |
|:----------------|----:|-----------:|------------------:|:-----------------------|
| (-0.001, 0.167] |  38 |   0.394737 |          0.51511  | TF-IDF + LR            |
| (0.167, 0.333]  |  60 |   0.566667 |          0.554029 | TF-IDF + LR            |
| (0.333, 0.5]    | 123 |   0.691057 |          0.649686 | TF-IDF + LR            |
| (0.5, 0.667]    | 184 |   0.869565 |          0.724914 | TF-IDF + LR            |
| (0.667, 0.833]  | 217 |   0.926267 |          0.806873 | TF-IDF + LR            |
| (0.833, 1.0]    | 278 |   0.964029 |          0.875674 | TF-IDF + LR            |
| (-0.001, 0.167] | 110 |   0.172727 |          0.823178 | Frozen DistilBERT + LR |
| (0.167, 0.333]  |  97 |   0.237113 |          0.868801 | Frozen DistilBERT + LR |
| (0.333, 0.5]    | 113 |   0.628319 |          0.921915 | Frozen DistilBERT + LR |
| (0.5, 0.667]    | 151 |   0.854305 |          0.954098 | Frozen DistilBERT + LR |
| (0.667, 0.833]  | 180 |   0.927778 |          0.964102 | Frozen DistilBERT + LR |
| (0.833, 1.0]    | 249 |   0.975904 |          0.97183  | Frozen DistilBERT + LR |
| (-0.001, 0.167] |  57 |   0.350877 |          0.732027 | Fine-tuned DistilBERT  |
| (0.167, 0.333]  |  70 |   0.528571 |          0.767735 | Fine-tuned DistilBERT  |
| (0.333, 0.5]    | 115 |   0.773913 |          0.863817 | Fine-tuned DistilBERT  |
| (0.5, 0.667]    | 178 |   0.893258 |          0.894417 | Fine-tuned DistilBERT  |
| (0.667, 0.833]  | 210 |   0.942857 |          0.939059 | Fine-tuned DistilBERT  |
| (0.833, 1.0]    | 270 |   0.974074 |          0.940042 | Fine-tuned DistilBERT  |