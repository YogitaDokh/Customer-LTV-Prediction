# 🧠 Customer Lifetime Value (LTV) Prediction

## 📌 Project Overview
Customer Lifetime Value (LTV) is a key metric for understanding long-term customer profitability.  
This project builds an end-to-end machine learning pipeline to predict customer LTV using purchase behavior and enables actionable customer segmentation for targeted marketing.

The solution leverages **RFM-based behavioral features** and an **XGBoost regression model** to estimate future customer value.

---

## 🎯 Objective
Predict the lifetime value (LTV) of customers based on historical transaction behavior to support:

- 🎯 Targeted marketing campaigns  
- 💰 Customer retention strategies  
- 📈 Revenue optimization  
- 🧩 Customer segmentation  

---

## 📂 Dataset
**Online Retail Dataset**

**Rows:** 541,909  
**Columns:**  
- InvoiceNo  
- StockCode  
- Description  
- Quantity  
- InvoiceDate  
- UnitPrice  
- CustomerID  
- Country  

---

## 🛠️ Tech Stack
- **Python**
- **Pandas, NumPy**
- **Scikit-learn**
- **XGBoost**
- **Matplotlib, Seaborn**
- **Excel (for review/export)**

---

## 🔄 Project Pipeline

### 1️⃣ Data Preprocessing
- Removed missing CustomerID
- Filtered cancelled/negative transactions
- Converted InvoiceDate to datetime
- Created Revenue column
- Aggregated data at customer level

---

### 2️⃣ Feature Engineering (RFM + AOV)
The following behavioral features were created:

- **Recency** — Days since last purchase  
- **Frequency** — Number of transactions  
- **Monetary** — Total spend  
- **AOV (Average Order Value)** — Monetary / Frequency  

These features capture customer purchasing behavior effectively.

---

### 3️⃣ Target Transformation
Customer LTV is highly right-skewed due to a small number of high-value customers.

To stabilize variance and improve model learning:

- Applied **log transformation** to LTV  
- Reduced impact of extreme outliers  
- Improved regression performance  

---

### 4️⃣ Model Training
Model used:

**XGBoost Regressor**

Why XGBoost?

- Handles non-linearity well  
- Robust to outliers  
- Strong performance on tabular data  
- Industry standard for regression tasks  

---

### 5️⃣ Model Evaluation

**Test Performance**

- MAE: **0.0236**  
- RMSE: **0.0643**

**Cross-Validation**

- CV MAE: **0.0273**  
- CV Std Dev: **0.0033**

✅ Low error  
✅ Stable across folds  
✅ Minimal overfitting  

---

### 6️⃣ Residual Analysis
Residual diagnostics show errors are randomly distributed around zero, indicating no strong systematic bias in model predictions.

---

### 7️⃣ Customer Segmentation
Customers were segmented based on predicted LTV using quantiles:

- 🔴 Low Value  
- 🟡 Medium Value  
- 🟢 High Value  

This enables targeted marketing and retention strategies.

---

## 💰 Business Impact
The model helps businesses:

- Identify high-value customers  
- Prioritize retention spending  
- Optimize marketing ROI  
- Personalize customer engagement  

High-value customers represent the primary revenue drivers and should be the focus of retention campaigns.

---

## 📦 Deliverables
- ✅ End-to-end Python notebook  
- ✅ Trained XGBoost model (`.pkl`)  
- ✅ Visualizations and diagnostics  
- ✅ Customer segmentation  
- ✅ Final prediction file  

---

## 📁 Output Files
### 🔹 Model File
ltv_xgboost_model.pkl

### 🔹 Final Predictions
Customer_LTV_Predictions.csv

**Columns:**

- CustomerID  
- Predicted_LTV  
- Customer_Segment  

---

## 🚀 Future Improvements
- Add customer tenure features  
- Incorporate product diversity metrics  
- Perform hyperparameter tuning  
- Build time-aware LTV model  
- Add SHAP explainability  

---

## 🧾 Conclusion
This project demonstrates a production-style machine learning workflow for customer value prediction.  
By combining behavioral feature engineering with gradient boosting, the solution provides accurate and actionable LTV estimates that can directly support data-driven marketing strategies.

---

## 👤 Author
**Yogita Dokh**

---

⭐ If you found this project useful, consider giving it a star!
