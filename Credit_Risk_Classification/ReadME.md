# Credit Risk Assessment  

## Project Overview  
This project leverages predictive modeling to **classify customers into high-risk and low-risk categories**, enabling financial institutions to make data-driven lending decisions with reduced manual effort. By applying advanced data processing and predictive modeling, we enhance risk assessment accuracy and streamline loan approval processes.  

---

## Dataset

- **Source**: [Kaggle - Credit Score Classification](https://www.kaggle.com/datasets/parisrohan/credit-score-classification?select=train.csv)  
- **Size**: 100,000 Rows × 27 Columns  
- **Target Variable**: `Credit_Score` (Categorized as Good, Standard, and Poor)  
- **Reclassified Risk Levels:**  
  - **Low Risk (1)** = Good & Standard  
  - **High Risk (0)** = Poor  

### Data Preprocessing Workflow  

- **Data Aggregation**: Monthly records were merged to create a **single-row representation per customer** to avoid bias from multiple records for the same individual.  
- **Feature Engineering**: Redundant columns (e.g., **monthly salary** when **annual income** exists) were removed.  
- **Outlier Handling**: Applied **Mahalanobis Distance** to eliminate extreme values that could distort model performance.  
- **Feature Selection**: Utilized **Principal Component Analysis (PCA)** and **correlation analysis** to identify and retain only the **most influential features**, ultimately narrowing down the dataset to **9 key predictors**.  

### Most Important Features for Prediction  

1. **Outstanding Debt** – Higher debt correlates with higher risk  
2. **Avg Delay from Due Date** – Late payments indicate lower creditworthiness  
3. **Num of Credit Cards & Loans** – Higher numbers suggest financial overextension  
4. **Interest Rate** – Anomalies in lending risk assessment  

### Final Processed Data  

| Dataset Type | Rows | Columns |
|-------------|------|---------|
| **Raw Dataset** | 100,000 | 27 |
| **Optimized (Significant Features Only)** | 8,442 | 9 |

---

## Key Insights from Exploratory Data Analysis   

1. **Customers with an extensive credit history** are generally classified as **low risk**, indicating that a well-established credit track record contributes to financial stability.

   ![Credit Risk vs Age](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Credit_Risk_Classification/Images/Credit%20Risk%20Age%20%20vs%20Risk.png)

3. **Longer payment delays** are strongly associated with **higher credit risk**, as frequent late payments suggest **financial instability or poor repayment behavior**.

   ![Avg Payment Delay](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Credit_Risk_Classification/Images/Avg%20Payment%20Delay%20vs%20Risk.png)

5. **High-risk borrowers often receive lower interest rates**, which may indicate **inefficiencies in risk-based pricing strategies**, potentially leading to **mispriced lending decisions**.

   ![Interest Rate](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Credit_Risk_Classification/Images/Interest%20Rate%20vs%20Risk.png)

7. **The top 20% of low-risk customers are 1.7× more likely to repay their loans**, highlighting the **benefits of prioritizing low-risk borrowers** in lending strategies.
   
   ![Lift Curve](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Credit_Risk_Classification/Images/Lift%20Curve.png)

---

## 🤖 Machine Learning Models  

Multiple models were tested to determine the best approach for risk classification.  

### Models Evaluated  

 **Decision Tree** 🌟 (*Best Model*)  (Decision trees exceled in **handling categorical data and non-linear relationships**)
Logistic Regression  
Neural Networks  
Bootstrap Forest  
Boosted Trees  
K-Nearest Neighbors (KNN)  
Naïve Bayes

### Final Model Performance  

| Metric | Score |
|--------|-------|
| **Total Accuracy** | **84.07%** |
| **AUC Score** | **0.8963** |

![ROC Curve](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Credit_Risk_Classification/Images/ROC%20Curve.png)

---

## Business Impact  

- **Lending Efficiency**: Automating credit risk assessment reduces manual processing and accelerates loan approvals.  

- **Strategic Targeting**: By prioritizing **low-risk customers**, banks can **optimize lending strategies** and **reduce defaults**.  

- **Risk Mitigation**: The model **prevents misclassification**, reducing **bad loans and financial losses**.  

