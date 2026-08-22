<div align="center">

# 📊 Telco Customer Churn — Analysis & Predictive Modeling

### Understanding *why* customers leave, and predicting *who* will leave next

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-Model-red)](https://xgboost.readthedocs.io/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)](https://app.powerbi.com/links/JyLEMT_EZG?ctid=19fe7ed7-01ca-4ae6-9cb4-3d75b5264420&pbi_source=linkShare)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**[🔗 Live Interactive Dashboard](https://app.powerbi.com/links/JyLEMT_EZG?ctid=19fe7ed7-01ca-4ae6-9cb4-3d75b5264420&pbi_source=linkShare)** &nbsp;•&nbsp;
**[📓 Jupyter Notebook](./Telco_Customer_Churn_Organized_EN_v2.ipynb)** &nbsp;•&nbsp;
**[📄 Insights & Recommendations (PDF)](./Telco_Churn_Insights_Recommendations.pdf)**

</div>

---

## 📌 Overview

Customer churn is one of the costliest problems a subscription-based business faces. This project analyzes a telecom company's customer base end-to-end — from raw data to an interactive BI dashboard to a production-ready machine learning model — to answer two questions:

1. **Why** are customers leaving?
2. **Who** is most likely to leave next?

The result is a complete analytics package: a 6-page interactive **Power BI dashboard**, a fully documented **EDA + ML notebook**, and an **XGBoost model** that predicts churn with **86.9% accuracy**.

---

## 🖼️ Dashboard Preview

| Executive Overview | Customer Demographics |
|---|---|
| ![Executive Overview](./screenshots/executive_overview.png) | ![Customer Demographics](./screenshots/customer_demographics.png) |

| Services & Contract Analysis | Financial Impact |
|---|---|
| ![Services & Contract](./screenshots/services_contract.png) | ![Financial Impact](./screenshots/financial_impact.png) |

| Geographic Analysis | Churn Reasons |
|---|---|
| ![Geographic Analysis](./screenshots/geographic_analysis.png) | ![Churn Reasons](./screenshots/churn_reasons.png) |

> 💡 Add your dashboard screenshots to a `/screenshots` folder in the repo with the file names above so the images render correctly on GitHub.

**👉 Explore it live:** [Power BI Service Dashboard](https://app.powerbi.com/links/JyLEMT_EZG?ctid=19fe7ed7-01ca-4ae6-9cb4-3d75b5264420&pbi_source=linkShare)

---

## 🔑 Key Insights

| # | Insight |
|---|---|
| 1 | **Contract type is the #1 churn driver** — Month-to-month customers churn at **42.7%**, vs. 11.3% (1-year) and just 2.8% (2-year contracts). |
| 2 | **Support experience beats price** — *"Attitude of support person"* is the top-cited churn reason (192 cases), ahead of any competitor offer. |
| 3 | **Payment method signals risk** — Electronic check users churn at **45.3%**, ~3x higher than automatic payment methods. |
| 4 | **Tenure is protective** — Churn risk peaks in the first few months and drops sharply the longer a customer stays. |
| 5 | **Add-on services increase retention** — Customers without Online Security / Tech Support churn noticeably more. |
| 6 | **Geography is not a real driver** — Churn differences across regions are statistically insignificant (Chi-square p-value = 0.43). |

Full write-up with actionable recommendations: **[📄 Insights & Recommendations PDF](./Telco_Churn_Insights_Recommendations.pdf)**

---

## 🧠 Machine Learning Model

A binary classification model was trained to predict churn, using **SMOTE** to correct for class imbalance (only 26.5% of customers churn) before training.

| Metric | Score |
|---|---|
| **Model** | XGBoost Classifier |
| **Accuracy** | 86.86% |
| **ROC AUC** | 86.87% |
| **Precision / Recall / F1** | Balanced (0.86 – 0.88) across both classes |

The model can be used to generate a **Risk Score** per customer — the same concept shown in the *Financial Impact* page of the dashboard — so retention teams can prioritize the highest-risk accounts.

---

## 🗂️ Project Structure

```
telco-customer-churn/
│
├── Telco_Customer_Churn_Organized_EN_v2.ipynb   # Full EDA + ML notebook (organized, documented)
├── Telco_Churn_Insights_Recommendations.pdf      # Executive summary: insights + recommendations
├── requirements.txt                               # Python dependencies
├── LICENSE                                        # MIT License
├── screenshots/                                   # Dashboard page screenshots
│   ├── executive_overview.png
│   ├── customer_demographics.png
│   ├── services_contract.png
│   ├── financial_impact.png
│   ├── geographic_analysis.png
│   └── churn_reasons.png
└── README.md
```

---

## 🛠️ Tech Stack

- **Language:** Python 3.10
- **Data Analysis:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Machine Learning:** scikit-learn, XGBoost, imbalanced-learn (SMOTE)
- **Statistics:** scipy (Chi-square test)
- **BI / Dashboard:** Power BI Desktop & Power BI Service

---

## 🔬 Methodology

1. **Data Loading & Exploration** — shape, types, descriptive statistics, missing values.
2. **Exploratory Data Analysis** — demographics, tenure, services, contracts, payment methods, financial metrics.
3. **Geographic Clustering (KMeans)** — grouping customers by location and testing whether region affects churn (it doesn't, statistically).
4. **Data Preparation** — cleaning, leakage-safe feature selection, label encoding.
5. **Class Balancing (SMOTE)** — correcting the 26.5% vs. 73.5% class imbalance before training.
6. **Model Training & Evaluation** — XGBoost classifier evaluated with a confusion matrix, ROC AUC, precision, recall, and F1-score.
7. **Dashboard Design** — translating the same analysis into an interactive 6-page Power BI report for non-technical stakeholders.

---

## 🚀 How to Run

```bash
# Clone the repository
git clone https://github.com/<your-username>/telco-customer-churn.git
cd telco-customer-churn

# (Recommended) Create a virtual environment
python -m venv venv
source venv/bin/activate      # on Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook Telco_Customer_Churn_Organized_EN_v2.ipynb
```

---

## 💡 Recommendations for the Business

1. **Incentivize longer contracts** — the single highest-leverage retention lever.
2. **Invest in customer support training** — attitude, not price, is the top complaint.
3. **Target the first 90 days** with a dedicated onboarding/retention program.
4. **Investigate the electronic-check segment** and nudge customers toward automatic payments.
5. **Bundle add-on services** (Online Security, Tech Support) to raise switching cost.
6. **Prioritize retention efforts by contract type and service usage — not geography.**

---

## 📬 Contact

If you'd like to discuss this project, feel free to reach out via [LinkedIn](linkedin.com/in/ahmed-soliman-b9ba062b1) or open an issue in this repository.

---

<div align="center">

⭐ If you found this project useful, consider giving it a star!

</div>
