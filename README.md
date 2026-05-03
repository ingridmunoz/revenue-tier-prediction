# Revenue Tier Prediction for Transaction Segmentation

A machine learning project that predicts whether a transaction belongs to a **Low**, **Medium**, or **High** revenue tier and provides **actionable business insights and recommendations** based on transaction patterns.

---

## 🎯 Project Objective

The goal of this project is to help businesses understand which transaction characteristics are associated with high revenue performance and support better decision-making in areas such as pricing, inventory, and marketing.

---

## ⚙️ How the Model Works

### 1. Revenue Tier Definition

The continuous revenue variable is transformed into three categories:

- Low  
- Medium  
- High  

This is done using percentile-based segmentation to ensure balanced classes.

---

### 2. Data Cleaning and Preparation

- Missing values are handled  
- Inconsistent entries are fixed  
- Categorical variables are encoded  
- Numerical variables are prepared for modeling  

This ensures the model receives clean and reliable input data.

---

### 3. Feature Selection (No Data Leakage 🚨)

The model only uses **observable transaction features**:

- Product category  
- Customer region  
- Discount percent  
- Payment method  
- Month (seasonality)  
- Rating  
- Review count  

❗ Variables that directly calculate revenue (such as price × quantity) are intentionally excluded to maintain model validity.

---

## 🤖 Model Information

- **Algorithm:** Logistic Regression (Multinomial Classification)  
- **Target Variable:** Revenue Tier (Low / Medium / High)  
- **Number of Features:** 7  

### Features Used (7 total):

- product_category  
- customer_region  
- discount_percent  
- payment_method  
- rating  
- review_count  
- month  

---

## 📊 Model Performance

- **Accuracy:** 0.78  
- **Macro F1 Score:** 0.72  

These metrics indicate balanced performance across all revenue tiers, making the model reliable for multi-class classification.

---

## 📈 App Features (Streamlit Dashboard)

### 📊 Dashboard

- Visualize prediction distribution (Low vs Medium vs High)  
- Identify top-performing product categories  
- Understand key drivers of high revenue  
- View model performance metrics  

---

### 🎯 Single Prediction

- Input transaction details  
- Get instant revenue tier prediction  
- View prediction confidence  

---

### 📁 Batch Analysis

- Upload a CSV file  
- Predict revenue tier for multiple transactions  
- View distribution and insights  
- Download results  

---

## 🔍 Business Insights

The model reveals important patterns in transaction behavior:

- High revenue transactions are associated with:
  - Lower discounts (~4.9%)  
  - Higher ratings (~2.98)  
  - More customer reviews (~251)  

- Fashion products dominate the **high revenue tier**  
- Electronics are more frequently associated with **low revenue**

---

## 💼 Business Recommendations

Based on the model insights:

- Increase inventory for high-performing categories (e.g., Fashion)  
- Reduce discounts in high-revenue segments  
- Improve pricing strategy for low-performing categories (e.g., Electronics)  
- Focus marketing efforts on high-performing regions  

These recommendations help optimize revenue without relying on direct revenue calculations.

---

## 🧠 Smart Business Recommendation Engine

**Example Output:**

**Insight:**  
Fashion dominates high revenue.

**Recommendation:**

- Increase stock in Fashion by 15%  
- Reduce discounts in Electronics  
- Focus marketing on high-performing regions  

---

## 🚀 Quick Start (Run in 5 Minutes)

### 1. Clone the Repository

```bash
git clone https://github.com/ingridmunoz/revenue-tier-prediction
cd revenue-tier-prediction

