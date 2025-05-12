 # 🧠 Predicting Salaries from NYC Payroll Data

**Authors:** Aishwarya Bhethanabotla & Katherine Shagalov  
**Project Type:** Data Science / Machine Learning  
**Dataset:** [NYC OpenData Citywide Payroll Data (Fiscal Year)](https://data.cityofnewyork.us/)

## 📌 Problem Statement

Salaries in the public sector vary due to multiple factors like job role, employment status, work location, and hours worked. This makes budgeting and salary benchmarking difficult for both employers and job-seekers. Our objective is to develop a predictive model to estimate annual salary payouts for NYC agency employees using historical payroll data.

---

## 🗃️ Data Overview

- **Size:** 6.22 million rows
- **Key Features Used:**
  - Work Location Borough
  - Title Description
  - Leave Status
  - Base Salary
  - OT Hours, OT Paid
  - Other Pay
  - Pay Basis
  - Regular Gross Paid

- **Engineered Feature:**
  - `Total Pay Earned` = Regular Gross Paid + OT Paid + Other Pay

---

## 🧹 Data Preprocessing

- Dropped irrelevant columns (e.g., name, agency start date, etc.)
- Removed low-pay outliers (< \$5000)
- Filtered specific work boroughs: Manhattan, Bronx, Brooklyn, Queens
- Removed irregular job roles (e.g., election workers, part-time education)

---

## 📊 Exploratory Data Analysis

- Grouped statistics by borough and fiscal year
- Visualized total pay distribution and category-wise salary breakdown

---

## 📈 Feature Engineering & Dimensionality Reduction

- **StandardScaler:** Applied to normalize numeric features
- **PCA (Principal Component Analysis):** Reduced dimensions to 3 components while retaining most variance

---

## 🤖 Modeling

### 1. **Linear Regression**
- **MAE:** \$1,068.13  
- **Adjusted R²:** 0.9985  
- Simple and accurate, but less robust to complex patterns in pay distribution.

### 2. **Random Forest**
- **MAE:** \$8,326.26  
- **Adjusted R²:** 0.9238  
- Better suited for nonlinear patterns and variance in pay, ideal for evaluating scalability.

---

## ⚙️ Scalability Strategy

### Scaling Up (More Data)
- Evaluated model performance as we increased data: 20% → 40% → 60% → 80% → 100%

### Scaling Out (More Compute Nodes)
- Tested on Spark clusters with:
  - 1 Master, 2 Workers
  - 1 Master, 3 Workers
  - 1 Master, 4 Workers

- **Findings:** Random Forest scales better with cluster size, and showed improved computational efficiency with more workers.

---

## ✅ Key Insights

- Random Forest was more sensitive to compute resources, making it ideal for distributed processing.
- PCA helped reduce multicollinearity and dimensionality.
- Total Pay (including OT and bonuses) is a stronger predictor than Base Salary alone.

---

## 📎 Conclusion

Distributed machine learning using Random Forest provides a scalable and accurate approach to predict government employee salaries. This framework can assist in budget planning, compensation benchmarking, and HR analytics.

---

## 📌 Future Work

- Integrate salary trends across multiple fiscal years
- Deploy as an interactive dashboard or API
- Explore deep learning models for complex pay prediction scenarios

---

## 📬 Contact

For questions or collaboration:
- **GitHub:** [Aish970](https://github.com/Aish970)
- **Email:** (Add if desired)
