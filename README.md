# Credit Card Behaviour Score Prediction Using Classification and Risk-Based Techniques


## Overview and Modeling Strategy

The project aimed to predict credit card defaults using machine learning. The process included:

- **Data Cleaning:** Rows with missing age values were dropped to ensure data quality.
- **Feature Engineering:** New features were created to capture payment behavior, credit utilization, and financial stress, increasing the feature count by over 100%.
- **Class Imbalance Handling:** SMOTE was used to balance the dataset.
- **Model Selection:** Multiple models (Logistic Regression, Decision Tree, XGBoost, LightGBM) were evaluated, with XGBoost selected for its superior performance.


## EDA Findings and Visualizations

- **Payment History:** Delayed and consecutive late payments were strong predictors of default.
- **Credit Utilization:** High and increasing credit utilization ratios correlated with higher default risk.
- **Financial Stress:** Features combining severe delays, increasing bills, and decreasing payments were highly predictive.
- **Visualizations:** KDE plots and correlation bar charts showed the impact of engineered features and their relationships with default status.


## Financial Insights: Key Drivers of Default

- **Overdue Payments:** Customers with multiple late payments or severe delays were much more likely to default.
- **Credit Utilization:** Those using most of their credit limit while making minimal payments were at highest risk.
- **Repayment History:** Consistent late payments and zero-payment months significantly increased default probability.
- **Trends:** Increasing bill amounts and decreasing payments over time were clear warning signs.


## Model Comparison and Final Selection

| Model | Accuracy | Precision | Recall | F1 Score | F2 Score | ROC-AUC |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| Logistic Regression | 0.6991 | 0.7376 | 0.6179 | 0.6725 | 0.6386 | 0.7697 |
| Decision Tree | 0.8184 | 0.8046 | 0.8412 | 0.8225 | 0.8336 | 0.8184 |
| XGBoost | 0.8917 | 0.9291 | 0.8480 | 0.8867 | 0.8631 | 0.9474 |
| LightGBM | 0.8874 | 0.9370 | 0.8306 | 0.8806 | 0.8499 | 0.9438 |

**XGBoost was selected for its highest F2 score and strong recall, crucial for minimizing missed defaults.**

## Evaluation Methodology

- **Primary Metric:** F2 score, emphasizing recall to reduce costly false negatives.
- **Other Metrics:** Accuracy, precision, recall, F1, and ROC-AUC were also tracked for comprehensive assessment.


## Training Dataset Results (Tuned XGBoost)

- **Accuracy:** 89.63%
- **F1 Score:** 89.23%
- **Recall:** 86.01%
- **F2 Score:** 89.51%
- **Precision:** 92.71%
- **ROC-AUC:** 95.07%


## Classification Cutoff Selection

- **Threshold Tuning:** The optimal cutoff was found to be 0.16 (not the default 0.5), maximizing the F2 score.
- **Rationale:** A lower threshold increases sensitivity to potential defaults, aligning with business needs to minimize missed risks.


## Business Implications

- **Risk Management:** Improved default prediction supports better risk management and portfolio optimization.
- **Automation:** High model performance allows for confident automated credit decisions.
- **Regulatory Compliance:** Interpretable features support transparency and compliance.


## Summary of Findings and Key Learnings

- **Feature engineering significantly improved model performance.**
- **XGBoost outperformed other models, especially in recall and F2 score.**
- **Threshold tuning is critical for business alignment.**
- **The model is production-ready and supports robust, automated credit risk assessment.**
