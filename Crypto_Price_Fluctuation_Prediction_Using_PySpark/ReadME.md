# Cryptocurrency Price Prediction using PySpark  

## Project Overview  
Cryptocurrency markets are highly volatile, influenced by various factors such as market trends, investor sentiment, and external events.

This project aims to **predict whether a cryptocurrency’s price will increase or decrease within a two-week period (ticker is undisclosed)** by leveraging **PySpark** for scalable data processing and a structured **ML pipeline** for automated machine learning workflows.  

A well-optimized ML pipeline has been designed to handle **data preprocessing, feature selection, model training, and evaluation** in a streamlined manner.  
The objective is not only to achieve high predictive accuracy but also to derive insights into key factors driving price movements.  

---

## Technologies & Tools Used  
Big Data & Machine Learning:
 - PySpark (MLlib, DataFrame API) -  Efficient processing of large-scale data.
 - Pandas, Matplotlib, Seaborn - Data exploration & visualization.  

## Dataset & Feature Analysis  
The dataset, sourced from bitgrit, consists of 2,660 records and 78 features, covering various financial and behavioral indicators:  

* Market Data (`feature_x_y`) – Historical price movements, trading volumes, and market volatility indicators.  
* Event Indicator (`TR_x_EventInd`) – Key events that may influence crypto price trends.  
* Search Trends (`index_1`, `index_2`, `index_3`) – Crypto-related keyword popularity.  
* Target Variable (`Target`):  
   - `0` → Price *decreased* after two weeks.  
   - `1` → Price *increased* after two weeks.
### Key Observations from Data Exploration  
- Market-driven features exhibited stronger correlations with price movements compared to search trends.  
- `TR_3_EventInd` emerged as a highly influential feature, demonstrating a strong correlation with price increases.

  ![Event Type vs Price Fluctuation](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Crypto_Price_Fluctuation_Prediction_Using_PySpark/Images/Event%20Type%20vs%20Price%20Fluctuation.png)
  
- Search trend indicators (`index_2`, `index_3`) showed moderate relevance, while `index_1` had minimal impact.

  ![Search Trend vs Price Fluctuation](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Crypto_Price_Fluctuation_Prediction_Using_PySpark/Images/Search%20Trend%20vs%20Price%20Fluctuation.png)

---

## Machine Learning Pipeline Design  
To ensure efficiency and scalability, an end-to-end ML pipeline in PySpark was implemented, covering:  

### 1️⃣ **Data Preprocessing**  
- Features with >50% missing values (e.g., `TR_1_EventInd`, `index_1`) were excluded.
- Mean/mode imputation was applied for missing values.  
- StandardScaler was used for numerical feature normalization.  
- VectorAssembler was utilized to transform multiple input features into a single vector column.  

### 2️⃣ **Feature Engineering & Selection**  
- Features were categorized based on their properties.
- Permutation Importance was applied to retain only the most relevant features, improving model efficiency.  

### 3️⃣ **Model Training & Optimization**  
* Multiple models were evaluated to determine the best-performing approach:  
   - Decision Tree – Computationally efficient but with lower predictive power.  
   - XGBoost – Provided good accuracy but required significant computational resources.  
   - Random Forest – **Optimal balance between accuracy, interpretability, and efficiency.**  

* Grid Search with 5-fold cross-validation was used for hyperparameter tuning to maximize model performance.  

### 4️⃣ **Model Evaluation & Performance Metrics**  
* AUC-ROC, Precision, Recall, and F1-score were used for evaluation.  
* Weighted F1-score was prioritized to address class imbalance.  

---

## Best Model & Performance Metrics  

### Performance Comparison:  
| Model           | AUC-ROC Score | F1-score |
|---------------|--------------|----------|
| Decision Tree  | 0.72         | 0.64     |
| XGBoost       | 0.74         | 0.66     |
| **Random Forest** | **0.76**  | **0.68** |

![Model Evauation](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Crypto_Price_Fluctuation_Prediction_Using_PySpark/Images/Model%20Evaluation.png)

![ROC Curve](https://github.com/LikhithaGuggilla/Predictive-Modeling/blob/main/Crypto_Price_Fluctuation_Prediction_Using_PySpark/Images/ROC%20Curve.png)

* **Random Forest was selected as the final model**, achieving an **F1-score of 0.68**, improving upon the **baseline of 0.51**.  
* Feature selection reduced complexity without compromising performance.  
* Market-driven features (`E` and `C` groups) and event data (`TR_3_EventInd`) were key drivers of price movement predictions.  

---

## Key Insights & Takeaways  
* Event indicators (`TR_3_EventInd`) played a critical role in price predictions, proving more impactful than search trends.
* Feature selection significantly improved model efficiency, reducing noise while maintaining high accuracy.
* Random Forest provided the best trade-off between precision, recall, and computational efficiency.
* The optimized model outperformed the baseline 17%, achieving a notable improvement in F1-score.

---


## Conclusion  
This project successfully demonstrates how **a structured ML pipeline can be leveraged to predict cryptocurrency price movements**.  
By strategically integrating **feature engineering, model selection, and hyperparameter tuning**, a **highly efficient and scalable predictive model** was developed.  


