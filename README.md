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

### Step 1. Clone the Repository

```bash
git clone https://github.com/ingridmunoz/revenue-tier-prediction
cd revenue-tier-prediction
```

### Step 2: Install Python Packages
```powershell
pip install -r requirements.txt
```

### Step 3: Train the Model (First Time Only)
```powershell
python train_model.py
```

Expected output:
```
============================================================
Revenue Tier Prediction - Model Training
============================================================

[1/6] Loading dataset...
✓ Loaded X records from data/clean_amazon_sales.csv
...
============================================================
✓ TRAINING COMPLETE!
============================================================
```

### Step 4: Run the Streamlit App
```powershell
streamlit run app.py
```

### Step 5: Open in Browser
A browser window will automatically open at:
```
http://localhost:8501
```

---

## App Features

### 📊 Dashboard
- View model accuracy and macro F1 score
- See key business insights from the data
- Get automatic business recommendations

### 🎯 Single Prediction
1. Enter transaction details (category, region, discount, rating, etc.)
2. Click "Predict Revenue Tier"
3. Get instant prediction with confidence scores

**Example:**
```
Product Category: Electronics
Customer Region: North America
Discount: 15%
Rating: 4.5
Review Count: 250
Result: HIGH Revenue Tier ✅
```

### 📁 Batch Analysis
1. Upload a CSV file with multiple transactions
2. App automatically predicts revenue tier for all rows
3. View prediction distribution, top categories, insights
4. Download predictions as CSV

**Required CSV Columns:**
```
product_category, customer_region, discount_percent, payment_method, rating, review_count, month
```

**Example CSV:**
```
Electronics,North America,10,Credit Card,4.5,150,3
Books,Europe,20,Debit Card,3.8,95,5
Fashion,Asia,15,Wallet,4.2,200,7
```

---

## Project Structure

```
revenue-tier-prediction/
├── app.py                      
├── train_model.py              
├── requirements.txt            
├── README.md                   
├── data/
│   ├── amazon_sales.csv        
│   └── clean_amazon_sales.csv  
└── model/
    └── revenue_model.pkl       
```

---

## Troubleshooting

### Issue: "ModuleNotFoundError: No module named 'streamlit'"
**Solution:** Make sure you installed all packages:
```powershell
pip install -r requirements.txt
```

### Issue: "FileNotFoundError: model/revenue_model.pkl"
**Solution:** The model file doesn't exist. Train it first:
```powershell
python train_model.py
```

### Issue: Browser doesn't open automatically
**Solution:** Manually open:
```
http://localhost:8501
```

### Issue: CSV upload fails
**Solution:** Make sure your CSV has these exact columns:
```
product_category, customer_region, discount_percent, payment_method, rating, review_count, month
```

---

## Commands Reference

| Command | Purpose |
|---------|---------|
| `pip install -r requirements.txt` | Install all required packages |
| `python train_model.py` | Train the machine learning model |
| `streamlit run app.py` | Start the web application |

---

## Data Source

**Dataset:** Amazon Sales Data  
**Records:** ~49,000 transactions  
**Features:** 7 input features + 1 target variable  
**Target:** Revenue Tier (Low / Medium / High)

---

## FAQ

**Q: Do I need to modify the code?**  
A: No! Just run the commands exactly as shown above.

**Q: What if I don't have Python installed?**  
A: Download Python 3.8 or newer from https://www.python.org/

**Q: Can I use my own data?**  
A: Yes! Prepare a CSV with the same columns and use the Batch Analysis section to upload it.

**Q: Is this production-ready?**  
A: This is an educational project. For production use, add proper error handling, logging, and security measures.

---

## Next Steps

1. ✅ Run the app (you're done!)
2. 🔍 Explore different predictions in the Single Prediction section
3. 📊 Upload your own data in the Batch Analysis section
4. 📈 Try different ML models to improve accuracy
5. 🚀 Deploy online using Heroku, AWS, or Google Cloud

---

**Questions?** Check the troubleshooting section or review the code comments.

**Ready to start?**
```powershell
streamlit run app.py
```