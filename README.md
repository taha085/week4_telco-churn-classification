# Telco Customer Churn — submission files

## Files
- `classification_baseline.py`: reproducible scikit-learn workflow.
- `MODEL_COMPARISON.md`: generated report containing measured metrics, confusion matrices, and business interpretation.

## Run it
Install dependencies:

```bash
pip install pandas numpy scikit-learn
```

Then run:

```bash
python classification_baseline.py --data WA_Fn-UseC_-Telco-Customer-Churn.csv
```

Pass the actual CSV path from Task 2. The script creates `MODEL_COMPARISON.md` in the current directory. Review the resulting metrics and interpretation before submitting; the report must be generated using the same dataset/source as Task 2.

## Validation notes
- `Churn=Yes` is the positive class.
- `TotalCharges` is converted to numeric before splitting; blanks become missing and are imputed within the pipeline.
- The split is stratified 80/20.
- `customerID` is excluded.
- Encoding and scaling are fit only on training data.
- The Task 2 baseline predicts the training-set majority class for every test row.
- Logistic Regression is evaluated at the default 0.50 probability threshold.
