# E-Commerce Product Return Risk Analysis & Dashboard

## 📘 Introduction
Product returns are a major challenge in the e-commerce industry, impacting profitability and customer experience.  
Predicting and analyzing return risk allows businesses to identify high-risk products, optimize inventory, and improve seller performance.  

This project focuses on **predicting product return probabilities using machine learning** and **performing SQL-based insights**, followed by **visual analysis using Power BI**.

---

## 🎯 Abstract
The project aims to **predict high-risk products prone to returns** using machine learning techniques and visualize insights through an interactive Power BI dashboard.

The dataset **`Ecommerce_Product_Sales.csv`** (from Kaggle) contains product attributes such as category, price, ratings, and return rates.

Two models were tested:
- **Logistic Regression:** ROC-AUC = 0.492  
- **XGBoost:** ROC-AUC = 0.781 ✅ *(best performing model)*

**XGBoost** was used to generate two output CSV files:
- `order_level_with_probs_xgb.csv` – Order-level return probabilities  
- `product_return_high_risk_xgb.csv` – Products with high return risk  

Additionally, **SQL queries** were executed using SQLite within Python to gain summary insights like return rates by category and top returned products.  
Finally, **Power BI** was used to design an interactive dashboard for business decision-making.

---

## 🧰 Tools Used
- **Python:** Pandas, NumPy, Scikit-learn, XGBoost, SQLite3  
- **Jupyter Notebook / VS Code:** For analysis and experimentation  
- **Power BI Desktop:** For dashboard and visualization  
- **Dataset:** `Ecommerce_Product_Sales.csv` (Kaggle)

---

## ⚙️ Steps Involved in Building the Project

### 1. 📂 Dataset Collection
- Downloaded `Ecommerce_Product_Sales.csv` from Kaggle.
- Contains fields like `Product_ID`, `Category`, `Price`, `Revenue`, `Ratings`, and `Return_Rate`.

### 2. 🧹 Data Preprocessing
- Handled missing values, encoded categorical columns, and normalized numerical features.  
- Defined **target variable:** `is_returned`.

### 3. 🤖 Model Development
- Built **Logistic Regression** → ROC-AUC: `0.492` (low performance).  
- Implemented **XGBoost** → ROC-AUC: `0.7806` (high performance).  
- Generated predicted probabilities for each order.

### 4. 💾 Model Output Files
- `order_level_with_probs_xgb.csv` → All products with return probabilities.  
- `product_return_high_risk_xgb.csv` → High-return-risk products.

### 5. 🧮 SQL-Based Insights (SQLite)
Executed analytical queries using SQLite inside Python:
- **Return Rate by Category:** Sports (17.6%) and Beauty (17.5%) had the highest return rates.  
- **Price vs Return Group:** Average price of low-return products ≈ 252.1.  
- **Top 5 Returned Products:** e.g., *Pro Product_88 (Toys)* and *Max Product_92 (Electronics)* with 30% return rate.

### 6. 📊 Power BI Dashboard

An **interactive Power BI dashboard** was designed to visualize model results and business insights derived from the XGBoost predictions and SQL summaries.  
It helps stakeholders quickly identify **high-risk products, sellers, and categories** contributing to higher return rates.

**Key Features and Visuals:**

- **KPI Cards:**  
  - `AvgReturnProb` → 0.98  
  - `RevenueLost` → 59.52M  
  - `TotalRevenue` → 60.33M  
  - `AvgUnitsSold` → 486.21  

- **Filter Panel (Slicers):**  
  - By *Category* and *Seller_Name* for focused analysis.

- **Visual Components:**  
  - **Table:** Displays Product_Name, Category, and Seller_Name with dynamic filtering.  
  - **Bar Chart (RevenueLost by Product_Name):** Highlights which products lead to maximum revenue loss due to returns.  
  - **Scatter Plot (Sum of Price vs Sum of Return Probability by Category):** Reveals correlation between product pricing and return tendency.  
  - **Bar Chart (AvgReturnProb by Category):** Compares average return probabilities across product categories.  
  - **Treemap (AvgReturnProb by Seller_Name):** Visualizes which sellers have the highest average return risks.  
  - **Bar Chart (AvgReturnProb by PriceGroup):** Shows return probability trends for different price segments (e.g., Low <100, Medium 100–500).  

**Insights from the Dashboard:**
- *Sports* and *Beauty* products exhibit higher average return probabilities.  
- *Seller_A* and *Seller_E* are associated with the highest average return risks.  
- Price range doesn’t significantly affect return probability — both low and medium price groups show similar trends.  
- The visual mix of KPIs, charts, and slicers provides an end-to-end analytical view of return risk across sellers and categories.

---
## 🗂️ Folder Structure
```
E-commerce_return_rate_reductions/
├── data/ # Dataset files (Ecommerce_Product_Sales.csv)
├── notebook/ # Jupyter notebooks (Logistic Regression, XGBoost)
├── output/ # Model output CSVs and EDA visuals
│ ├── order_level_with_probs_xgb.csv
│ └── product_return_high_risk_xgb.csv
├── dashboard/ # Power BI dashboard (.pbix file)
│ └── Dashboard.pbix
├── requirements.txt # Python dependencies
└── README.md # Project documentation
```
---

## 🧩 Key Results
| Model | ROC-AUC Score | Remark |
|--------|----------------|--------|
| Logistic Regression | 0.492 | Poor performance |
| XGBoost | 0.781 | Best performing model |

---

## 🏁 Conclusion
This project successfully integrates **machine learning, SQL analytics, and Power BI visualization** to identify and interpret product return risks in e-commerce.  
The **XGBoost model** outperformed Logistic Regression, providing a reliable way to estimate return probabilities.  

SQL analysis added business-level insights, and the **Power BI dashboard** transformed raw predictions into actionable visuals, helping stakeholders identify **high-risk categories, sellers, and products**.

This end-to-end project demonstrates how **data analytics and BI tools** can work together to support **business optimization in e-commerce**.
