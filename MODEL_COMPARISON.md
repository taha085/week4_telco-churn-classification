# Telco Customer Churn — Model Comparison

## Test-set metrics

| Model                          |   Accuracy |   Precision |   Recall |    F1 |   ROC-AUC |
|:-------------------------------|-----------:|------------:|---------:|------:|----------:|
| Majority-class baseline        |      0.735 |       0     |    0     | 0     |     0.5   |
| Logistic Regression - Default  |      0.806 |       0.657 |    0.559 | 0.604 |     0.842 |
| Logistic Regression - Balanced |      0.738 |       0.504 |    0.783 | 0.614 |     0.841 |

## Confusion matrices

### Majority Baseline

Rows = actual; columns = predicted; order = No, Yes.

| | Predicted No | Predicted Yes |
|---|---:|---:|
| Actual No | 1035 (TN) | 0 (FP) |
| Actual Yes | 374 (FN) | 0 (TP) |

### Logistic Regression - Default

Rows = actual; columns = predicted; order = No, Yes.

| | Predicted No | Predicted Yes |
|---|---:|---:|
| Actual No | 926 (TN) | 109 (FP) |
| Actual Yes | 165 (FN) | 209 (TP) |

### Logistic Regression - Balanced

Rows = actual; columns = predicted; order = No, Yes.

| | Predicted No | Predicted Yes |
|---|---:|---:|
| Actual No | 747 (TN) | 288 (FP) |
| Actual Yes | 81 (FN) | 293 (TP) |

## Business interpretation

Compare churn recall, precision, F1 and false negatives. If missed churners are more costly than false alarms, prefer the model that catches more churners when its outreach burden is acceptable. ROC-AUC evaluates ranking across thresholds; it does not by itself determine the best business decision. The models here use the default 0.50 classification threshold.
