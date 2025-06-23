**Objective:** A predictive modeling solution developed to analyze borrower financial and personal data classifying them into high,low-risk buckets, aimed at improving credit risk assessment and reducing loan defaults.

**Tools:** SQL, Python, JMP

---

**Data:**
Each row represents loan borrower's demographic details, credit usage, payment behaviors, debt indicators and monthly financial activity.

**Source:** Kaggle (https://www.kaggle.com/datasets/parisrohan/credit-score-classification?select=train.csv)

**Method:**
1. Dealt  messy data, redundancy & data errors with robust techniques like long-to-wide, elimination, aggregation, imputation, missing data pattern, normalization and domain knowledge improving the model's accuracy by 45%.
2.  Performed correlation, principal component (PCA), univariate (IQR plots) & multivariate outlier analysis (Mahalanobis distance) and feature importance uncovering key risk factors like delinquency, credit usage, net disposable balance etc for loan default.
3. Partitioned the data into train, validation, test. Built and compared models-Logistic Regression, Decision Tree, Random Forest, XG Boost etc improving the accuracy to 84.07% (Decision tree) on test data while addressing class imbalance with SMOTE, focusing on sensitivity/False Negative (FN) Reduction adjusting cut-off and balancing models bias-variance.

**Evaluation Metrics:**
Classification report (F1-Score), Total Accuracy (Misclassification rate), Sensitivity, AUC-ROC

**Business Impact:**
A loan repayment boosting strategy of targeting low-risk customers (1.7x) identified through lift-curve analysis reduces loan default-risk.
