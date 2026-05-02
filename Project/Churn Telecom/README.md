# 📡 Telecom Customer Churn — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=flat&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C8CBF?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557c?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat)

---

## 📌 Project Overview

Customer churn — when a customer stops using a company's service — is one of the most critical challenges in the telecommunications industry. Acquiring a new customer costs **5× to 25×** more than retaining an existing one, making churn prediction and prevention a top business priority.

This project performs a comprehensive **Exploratory Data Analysis (EDA)** on a real-world telecom dataset to answer one central business question:

> **"What are the key drivers of customer churn, and what actionable steps can the business take to reduce it?"**

The analysis moves through data cleaning, univariate and multivariate exploration, and feature engineering, culminating in a set of concrete, data-backed business recommendations.

---

## 📂 Dataset Description

| Property | Details |
|---|---|
| **Source** | IBM Sample Dataset — Telco Customer Churn |
| **Records** | 7,043 customers |
| **Features** | 21 columns (demographics, services, account info) |
| **Target Variable** | `Churn` (Yes / No) |
| **Class Distribution** | ~73.5% No Churn / ~26.5% Churned |

### Feature Groups

**Demographics:** `gender`, `SeniorCitizen`, `Partner`, `Dependents`

**Services Subscribed:** `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`

**Account Information:** `Contract`, `PaperlessBilling`, `PaymentMethod`, `tenure`, `MonthlyCharges`, `TotalCharges`

---

## 🔬 Methodology

The analysis follows a structured, end-to-end EDA workflow:

```
1. Business Understanding  →  Define the problem and objectives
2. Data Overview           →  Shape, dtypes, descriptive statistics
3. Data Cleaning           →  Duplicates, type casting, missing values
4. EDA — Univariate        →  Distribution of each feature independently
5. EDA — Bivariate         →  Each feature vs. the Churn target
6. EDA — Multivariate      →  Interactions between 3+ variables
7. Feature Engineering     →  Tenure binning, Total Services count
8. Conclusions             →  Key findings & actionable recommendations
```

### Data Cleaning Summary

- **0 duplicate** records found across 7,043 rows.
- `SeniorCitizen` re-mapped from `{0, 1}` → `{'No', 'Yes'}` for consistency.
- `TotalCharges` had **11 missing values** where `tenure = 0` (new customers); these rows were **dropped** as imputation via `tenure × MonthlyCharges` was invalid.
- Final dataset: **7,032 clean records**.

---

## 💡 Key Findings & Actionable Insights

### 🔍 What the Data Tells Us

| # | Finding | Impact |
|---|---|---|
| 1 | **26.5%** overall churn rate — moderate class imbalance | High |
| 2 | **80%+ of churn** is concentrated in the first **0–12 months** of tenure | Critical |
| 3 | **Fiber optic** users churn at an alarmingly high rate despite paying premium prices | Critical |
| 4 | **Month-to-month** contract customers are far more likely to churn than annual/biannual subscribers | High |
| 5 | Customers paying via **Electronic Check** show the highest churn rates | Medium |
| 6 | Customers **without** `TechSupport`, `OnlineSecurity`, or `OnlineBackup` are highly vulnerable | High |
| 7 | **Senior Citizens** and customers with no `Partner` or `Dependents` churn at above-average rates | Medium |
| 8 | Churned customers have **higher median MonthlyCharges** but **lower TotalCharges** (they leave early) | High |

### 🎯 Actionable Recommendations

**1. Fix the First-Year Onboarding Experience**
> Implement proactive check-in calls at months 1, 3, and 6. Offer a loyalty reward or a free service upgrade at the 6-month mark to push customers past the critical churn window.

**2. Audit Fiber Optic Quality & Pricing**
> Conduct immediate technical performance audits and run targeted satisfaction surveys for Fiber Optic users. Compare pricing with competitors and consider restructuring tiers if necessary.

**3. Incentivize Long-Term Commitment**
> Offer a 10% discount or a free month of service to customers who upgrade from month-to-month to annual contracts and switch to auto-pay (Credit Card / Bank Transfer).

**4. Bundle Value-Added Support Services**
> Offer a "Security & Support Bundle" free for the first 3 months to new internet subscribers to deepen product integration and reduce early churn.

**5. Tailor Plans for Vulnerable Demographics**
> Create simplified, discounted "Senior Plans" with priority support. For single customers without dependents, design attractive streaming bundles to increase the perceived value of their subscription.

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Python 3.10+** | Core programming language |
| **Pandas** | Data manipulation & cleaning |
| **Matplotlib** | Base plotting engine |
| **Seaborn** | Statistical data visualization |
| **Jupyter Notebook** | Interactive development environment |

---

## 🚀 How to Run Locally

### Prerequisites
- Python 3.8 or higher
- Git

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/eda-telecom-churn.git
cd eda-telecom-churn
```

**2. (Recommended) Create a virtual environment**
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Launch Jupyter Notebook**
```bash
jupyter notebook
```

**5. Open the notebook**

Navigate to `notebooks/EDA_Churn_Telecom.ipynb` and run all cells (`Kernel → Restart & Run All`).

> **Note:** The dataset file `Telco-Customer-Churn.csv` should be placed in the `data/` folder. Make sure the path in the notebook's loading cell matches: `../data/Telco-Customer-Churn.csv`.

---

## 📁 Project Structure

```
eda-telecom-churn/
│
├── data/
│   └── Telco-Customer-Churn.csv       # Raw dataset
│
├── notebooks/
│   └── EDA_Churn_Telecom.ipynb        # Main analysis notebook
│
├── images/                            # Exported chart images (optional)
│
├── requirements.txt                   # Python dependencies
├── README.md                          # Project documentation
└── LICENSE
```

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improving the analysis or adding a modeling phase, feel free to open an issue or submit a pull request.

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

*Built with ❤️ as part of a Data Science Portfolio.*
