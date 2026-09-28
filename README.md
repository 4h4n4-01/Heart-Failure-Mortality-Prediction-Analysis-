# Heart Failure Mortality Prediction

Group coursework project: predict mortality (`DEATH_EVENT`) from clinical records of heart-failure patients. This repository is my cleaned and extended version of the analysis; I led preprocessing and EDA, class-imbalance handling, the modelling pipeline and performance reporting.

## Data

`data/heart_failure_clinical_records.csv`: 5,000 rows, 12 clinical features (age, sex, anaemia, diabetes, high blood pressure, smoking, ejection fraction, serum creatinine, serum sodium, creatinine phosphokinase, platelets, follow-up time) and the binary target (31.4% deaths).

## Method

Exploratory analysis → SMOTE for class imbalance → logistic regression and random forest → accuracy, precision, recall, F1, confusion matrices and ROC-AUC.

## Results

| Model | Test accuracy | Recall (death) | ROC-AUC |
|---|---|---|---|
| Logistic regression | 82–84% | 0.68–0.77 | 0.77 |
| Random forest | ~99% | 0.97–0.98 | 0.60 (inconsistent with its accuracy; see below) |

## An important caveat: duplicated records

On re-examination, **3,680 of the 5,000 rows are exact duplicates** (only 1,320 unique records). This dataset is an enlarged version of a smaller public cohort, so a random train/test split places copies of the same patient in both sets. The random forest's ~99% test accuracy is therefore most likely memorisation rather than generalisation, and it is inconsistent with its much weaker probability ranking. The logistic regression results are more credible but are affected by the same issue.

**Next step:** deduplicate before splitting (or split by unique record) and re-evaluate all models; until then, the numbers above should not be read as out-of-sample performance.

## Repository

```
data/        dataset and data notes
Notebooks/   Heart Failure Analysis.ipynb
```

Tools: Python, pandas, scikit-learn, imbalanced-learn, Matplotlib, Seaborn.
