# Machine Learning for Tax Evasion Risk Prediction
## A Classification Case Study Using Firm-Level Audit Data

### 1. Research Question

Can machine learning improve the targeting of tax audits? This project builds and evaluates classification models to predict whether an audited firm will be found to have evaded taxes, using firm-level characteristics and financial risk indicators as predictors. The goal is to identify high-risk firms before audits occur, improving detection without expanding audit resources.

### 2. Data

The analysis uses firm-level audit data from India, covering firms selected for audit by the Comptroller and Auditor General (CAG) of India. The outcome variable indicates whether the audit detected tax evasion (`Risk`). Predictors include quantitative measures capturing firm characteristics, financial activity, and risk-related indicators.

The dataset has been modified for instructional use and is not included in this repository. Key variables are described in the notebook.

**Important note on sample selection:** The dataset covers only pre-selected audited firms, not the full firm population. This means the sample is not representative of all firms, which likely makes prediction easier than it would be in a real-world deployment. Results should be interpreted accordingly.

### 3. Methodology

Tax evasion detection is framed as a binary classification problem. Two model classes are implemented and compared:

- **Logistic Regression** — interpretable baseline model with two classification thresholds (0.5 and 0.6)
- **K-Nearest Neighbors (KNN)** — flexible, non-parametric alternative; evaluated with and without feature scaling

Model performance is evaluated using out-of-sample test data and cross-validation. Particular attention is given to the trade-off between false negatives (missed evaders) and false positives (unnecessary audits), reflecting real-world enforcement priorities.

### 4. Key Results

| Model | TN | FP | FN | TP | Accuracy |
|---|---|---|---|---|---|
| Logistic (threshold 0.5) | 233 | 2 | 2 | 151 | 98.97% |
| Logistic (threshold 0.6) | 235 | 0 | 3 | 150 | 99.23% |
| KNN (unscaled) | 231 | 4 | 15 | 138 | 95.10% |
| KNN (scaled) | 230 | 5 | 9 | 144 | 96.39% |

Logistic regression substantially outperforms KNN on both overall accuracy and false negatives. The ROC AUC for logistic regression is approximately 0.999. The strong results likely reflect the structured nature of the selected audit sample rather than generalizability to the full firm population.

### 5. Repository Structure

```
tax-evasion-risk-prediction/
  code/
    tax_evasion_prediction.ipynb   — full analysis notebook
  results/
    result_details.pdf             — extended results and robustness checks
  media/
    image1.png                     — variable definitions table
    image2.png                     — ROC curve
  README.md
```

---

*Analysis by Dong Liu. Data source: firm-level audit data from India (Comptroller and Auditor General), modified for instructional use.*
