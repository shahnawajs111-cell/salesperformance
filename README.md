# 🛍️ Customer Behavior Analysis

## 📌 Project Overview

This project analyzes **e-commerce customer transaction data** to understand customer purchasing behavior, sales patterns, product category performance, returns, and churn.

The analysis was developed using **Python, Pandas, NumPy, Matplotlib, and Seaborn** and focuses on transforming raw customer transaction data into meaningful business insights.

The project was completed as part of **Task 1 for Alfido Tech**.

---

## 🎯 Business Objective

The main objective of this project is to understand customer behavior and identify patterns that can help a business:

* Understand purchasing behavior
* Identify popular product categories
* Analyze customer purchase trends over time
* Understand the relationship between quantity and purchase amount
* Analyze customer demographics
* Monitor returns
* Identify potential customer churn
* Develop data-driven recommendations for improving customer retention and sales

---

## 📊 Dataset

The dataset contains **250,000 customer transaction records** and **13 columns**.

### Dataset Features

| Column                  | Description                           |
| ----------------------- | ------------------------------------- |
| `Customer ID`           | Unique customer identifier            |
| `Purchase Date`         | Date and time of the purchase         |
| `Product Category`      | Category of the purchased product     |
| `Product Price`         | Price of the product                  |
| `Quantity`              | Quantity purchased                    |
| `Total Purchase Amount` | Total amount spent on the transaction |
| `Payment Method`        | Payment method used                   |
| `Customer Age`          | Age of the customer                   |
| `Returns`               | Return indicator                      |
| `Customer Name`         | Customer name                         |
| `Age`                   | Customer age                          |
| `Gender`                | Customer gender                       |
| `Churn`                 | Customer churn indicator              |

### Dataset Statistics

* **Rows:** 250,000
* **Columns:** 13
* **Customer IDs:** Up to 50,000 unique IDs
* **Age Range:** 18–70
* **Product Price Range:** 10–500
* **Quantity Range:** 1–5
* **Average Quantity:** ~3
* **Average Purchase Amount:** ~2,725
* **Average Customer Age:** ~44
* **Churn Mean:** ~20%

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

### Tools

* Jupyter Notebook
* Kaggle Notebook
* GitHub

---

## 🔄 Project Workflow

The analysis follows the following workflow:

```text
Raw Dataset
     ↓
Data Loading
     ↓
Data Understanding
     ↓
Data Quality Check
     ↓
Missing Value Analysis
     ↓
Duplicate Detection
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Customer Behavior Analysis
     ↓
Correlation Analysis
     ↓
Business Insights
     ↓
Recommendations
```

---

## 1️⃣ Data Loading

The customer transaction dataset was loaded using Pandas.

```python
df = pd.read_csv("ecommerce_customer_data_large.csv")
```

Initial exploration was performed using:

```python
df.head()
df.info()
df.describe()
```

This helped understand the structure, data types, numerical distributions, and overall quality of the dataset.

---

## 2️⃣ Data Quality Analysis

The project checks for:

* Missing values
* Duplicate records
* Incorrect data types
* Numerical distributions
* Categorical distributions

Missing values were identified using:

```python
df.isnull().sum()
```

The `Returns` column contains missing values that require treatment before further analysis.

Duplicate records were checked using:

```python
df.duplicated().sum()
```

Duplicate rows were removed using:

```python
df.drop_duplicates(inplace=True)
```

---

## 3️⃣ Data Cleaning

The project includes a data-cleaning workflow for:

* Handling missing numerical values
* Handling missing categorical values
* Removing duplicate records
* Converting date columns into datetime format
* Preparing the dataset for analysis

For numerical columns, median imputation was used:

```python
df[col].fillna(df[col].median(), inplace=True)
```

For categorical columns, mode imputation was used:

```python
df[col].fillna(df[col].mode()[0], inplace=True)
```

---

## 4️⃣ Exploratory Data Analysis

Exploratory Data Analysis was performed to understand customer and transaction behavior.

### Numerical Analysis

The project examines distributions of:

* Product Price
* Quantity
* Total Purchase Amount
* Customer Age
* Returns
* Churn

Summary statistics were generated using:

```python
df.describe()
```

Histograms and KDE plots were used to understand numerical distributions.

---

## 5️⃣ Product Category Analysis

The project analyzes product category popularity using:

```python
df['Product Category'].value_counts()
```

This helps identify categories with higher purchase volumes.

### Business Use

Category-level analysis can help businesses:

* Focus marketing campaigns
* Optimize inventory
* Identify high-demand categories
* Design category-specific promotions

---

## 6️⃣ Purchase Trend Analysis

The `Purchase Date` column is converted to datetime format:

```python
df['Purchase Date'] = pd.to_datetime(df['Purchase Date'])
```

Monthly purchase trends are then analyzed to understand changes in transaction volume over time.

This can help identify:

* High-demand periods
* Low-demand periods
* Seasonal patterns
* Opportunities for promotional campaigns

---

## 7️⃣ Correlation Analysis

A correlation matrix is used to understand relationships between numerical variables.

The project analyzes relationships between:

* Product Price
* Quantity
* Total Purchase Amount
* Customer Age
* Returns
* Age

A correlation heatmap is created using Seaborn.

The project also examines relationships such as:

```text
Quantity → Total Purchase Amount
Customer Age → Total Purchase Amount
```

These relationships can help understand factors associated with customer spending.

---

## 8️⃣ Customer Behavior Analysis

The analysis focuses on understanding:

* Purchase frequency
* Product category preferences
* Customer demographics
* Purchase amount
* Quantity purchased
* Returns
* Churn

The goal is to identify patterns that can support customer-focused business decisions.

---

## 📈 Key Business Questions

This project is designed to answer questions such as:

1. Which product categories are purchased most frequently?
2. How does purchase volume change over time?
3. Does quantity purchased affect total purchase amount?
4. How does customer age relate to purchasing behavior?
5. Which payment methods are most commonly used?
6. What percentage of transactions involve returns?
7. What customer characteristics are associated with churn?
8. Which customer segments could require retention strategies?
9. Are there specific periods with unusually high or low purchase activity?
10. How can customer behavior insights support marketing decisions?

---

## 💡 Business Recommendations

Based on the analysis framework, the following business actions can be considered:

### 1. Focus on Popular Categories

Marketing and inventory strategies can prioritize frequently purchased product categories.

### 2. Use Seasonal Promotions

Promotional campaigns can be planned around periods with lower transaction activity.

### 3. Monitor Returns

Return patterns should be analyzed to identify potential product or customer-experience issues.

### 4. Improve Customer Retention

Customers showing churn-related behavior can be targeted with personalized retention campaigns.

### 5. Personalize Offers

Customer demographics and purchasing behavior can be used to create more targeted offers.

### 6. Analyze Purchase Quantity

Understanding how quantity relates to transaction value can help businesses design bundle offers and volume-based promotions.

---

## 📁 Project Structure

A recommended GitHub repository structure is:

```text
Customer-Behavior-Analysis/
│
├── Customer_Behavior_Analysis.ipynb
├── ecommerce_customer_data_large.csv
├── README.md
└── images/
    ├── correlation_heatmap.png
    ├── category_analysis.png
    └── purchase_trend.png
```

> If the dataset is too large or has redistribution restrictions, don't upload the CSV directly. Instead, provide the original dataset source in the README.

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/customer-behavior-analysis.git
```

### 2. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Open Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open

```text
Customer_Behavior_Analysis.ipynb
```

### 5. Run the notebook

Run the notebook cells sequentially from beginning to end.

---

## 📌 Skills Demonstrated

This project demonstrates practical experience with:

* Python for Data Analysis
* Pandas
* NumPy
* Data Cleaning
* Missing Value Treatment
* Duplicate Detection
* Exploratory Data Analysis
* Data Visualization
* Statistical Summary
* Correlation Analysis
* Customer Behavior Analysis
* Business Problem Solving
* Business Recommendations

---

## 🔮 Future Improvements

The project can be extended with more advanced customer analytics:

* **RFM Analysis**
* **Customer Segmentation**
* **K-Means Clustering**
* **Churn Analysis**
* **Customer Lifetime Value (CLV)**
* **Cohort Analysis**
* **Retention Analysis**
* **Purchase Frequency Analysis**
* **Power BI Dashboard**
* **Interactive customer segmentation dashboard**

These additions would make the project stronger as an end-to-end Data Analyst portfolio project.

---

## 👨‍💻 Author

**Shahnawaj Siddique**

Aspiring Data Analyst | Python | SQL | Power BI | Excel | Tableau

---

## ⭐ Project Goal

The goal of this project is to demonstrate how raw e-commerce transaction data can be transformed into **actionable customer and business insights using Python and data analytics techniques**.

If you find this project useful, feel free to ⭐ the repository.
