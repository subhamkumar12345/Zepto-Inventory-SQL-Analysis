# 🛒 Zepto Inventory SQL Analysis

## 👤 Role: Data Analyst  
As a data analyst, I led the end-to-end process of exploring and cleaning raw e-commerce inventory data, designing the database schema, and writing SQL-based queries to drive actionable business insights.

---

## 🎯 Project Objective  
Simulate how real-world data analysts in e-commerce/retail work behind the scenes to:

- Set up a messy inventory **database** using SQL
- Perform **Exploratory Data Analysis (EDA)** to understand pricing, product availability, and catalog inconsistencies
- Clean and transform data to enable accurate business reporting
- Generate **business-driven insights** around **pricing, stock levels, and revenue optimization**

---

## 🛠 Tools & Skills Used  
**PostgreSQL**, **pgAdmin**, **Advanced SQL**, **Data Cleaning**, **Exploratory Data Analysis (EDA)**, **Joins**, **Aggregations**, **Case Statements**, **Business Insight Development**

---

## 📁 Dataset Description  
The dataset was sourced from [Zepto’s official product listings on Kaggle](https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv) and simulates a real-world e-commerce inventory system.

Each row represents a unique SKU (Stock Keeping Unit) of a product. Duplicate names exist due to different packaging or pricing variants.

### Key Columns:
- `sku_id`: Unique identifier (Primary Key)  
- `name`: Product name  
- `category`: Product type (Fruits, Beverages, etc.)  
- `mrp`: Maximum Retail Price (in ₹)  
- `discountPercent`: Applied discount  
- `discountedSellingPrice`: Final price after discount  
- `availableQuantity`: Units in stock  
- `outOfStock`: Boolean flag  
- `weightInGms`: Product weight  
- `quantity`: Number of units or grams per pack  

---

## 🔄 Workflow & Key Contributions

### 1. 🧱 Database & Table Creation  
Designed SQL table schema using appropriate data types:

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```
### 2. 📥 Data Import  
Loaded the CSV using **MySQL's import feature** through the GUI interface. Ensured proper column mappings and UTF-8 encoding for smooth insertion.

---

### 3. 🔍 Data Exploration  
- Counted the total number of records in the dataset  
- Viewed a sample of the dataset to understand structure and content  
- Checked for null values across all columns  
- Identified distinct product categories available in the dataset  
- Compared in-stock vs out-of-stock product counts  
- Detected products present multiple times, representing different SKUs  

---

### 4. 🧼 Data Cleaning  
- Removed rows where MRP or discounted selling price was zero  
- Converted `mrp` and `discountedSellingPrice` from **paise to rupees** for consistency  
- Standardized column values for clean analysis  

---

### 5. 📊 Business Insights  
- Found top 10 best-value products based on discount percentage  
- Identified high-MRP products that are currently out of stock  
- Estimated potential revenue for each product category  
- Filtered expensive products (MRP > ₹500) with minimal discount  
- Ranked top 5 categories offering highest average discounts  
- Calculated price per gram to identify value-for-money products  
- Grouped products based on weight into Low, Medium, and Bulk categories  
- Measured total inventory weight per product category  
