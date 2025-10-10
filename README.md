
# Firm Tax Evasion Risk Prediction

**Author:** Dong Liu  
**Course:** Machine Learning Mini-Project 2 (University of Chicago, 2025)

## Objective
To identify firms with a high likelihood of tax evasion based on audit and financial indicators, helping regulators prioritize audits.

## Methods
- Logistic Regression (threshold tuning at 0.5 and 0.6)
- K-Nearest Neighbors (KNN) with scaling and cross-validation
- ROC AUC evaluation and confusion-matrix visualization

## Key Findings
- Logistic Regression achieved **AUC = 99.93 %**, with strong trade-off control between false positives and false negatives.  
- KNN (k = 1) yielded **95.9 % accuracy** after 5-fold CV; scaling slightly reduced performance.
- Recommended lower threshold to minimize false negatives in public-sector applications.

## Tools
Python (pandas, scikit-learn, seaborn, matplotlib), Jupyter Notebook

## Relevance
Demonstrates data-driven decision-making, model evaluation, and visualization — transferable to creative product analytics (e.g., evaluating GenAI campaign performance or content-funnel optimization).
