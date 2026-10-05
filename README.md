# Quantitative Macroeconomic & Synthetic Banking Terminal


[![FastAPI](https://img.shields.io/badge/FastAPI-0.111.0-009688.svg?style=flat&logo=FastAPI&logoColor=white)](https://fastapi.tiangolo.com)
[![Next.js](https://img.shields.io/badge/Next.js-14.2-black.svg?style=flat&logo=next.js&logoColor=white)](https://nextjs.org/)
[![Python](https://img.shields.io/badge/Python-3.10-blue.svg?style=flat&logo=python&logoColor=white)](https://python.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue.svg?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3+-orange.svg?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.7+-red.svg?style=flat)](https://xgboost.readthedocs.io/)

---

## 1. Project Overview

This project develops an end-to-end **Quantitative Banking Terminal** and **Synthetic Retail Banking Simulation** to analyze the impact of **macroeconomic shocks and interest rate fluctuations** on retail banking credit and deposit portfolios.

Addressing the structural scarcity of longitudinal customer-level banking data across diverse interest-rate cycles in the UK, this platform integrates empirical historical data (Bank of England & ONS, 2008–2025) with supervised econometric models, time series diagnostics, generative AI synthesizers (CTGAN & TVAE), and interactive stress testing.

---

## 2. Quantitative Model Architecture & Benchmark Metrics

All models are trained and validated on canonical UK monthly macroeconomic time series (2008–2025, 216 monthly observations).

| Target Banking Aggregate | Model Architecture | Key Features / Lags | Metric ^2$ / Accuracy | MAE | RMSE |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Mortgage Approvals** | **XGBoost Regressor** | Bank Rate, CPI, GDP, Unemployment, HPI, Mortgage Lag | ** 0.7154** | 3,322.13 | 4,413.14 |
| **Consumer Credit** | **Random Forest Regressor** | Bank Rate, CPI, GDP, Unemployment, Consumer Credit Lag | ** 0.9215** | 584.08 | 787.92 |
| **Savings Accounts** | **Scaled Linear Regression** | Bank Rate, CPI, GDP, Unemployment, HPI, Savings Lag | ** 0.9350** | 1,944.04 | 2,614.21 |
| **Current Accounts** | **Scaled Linear Regression** | Bank Rate, CPI, GDP, Unemployment, HPI, Current Acc Lag | 0.9297** | 4,104.52 | 7,711.75 |
| **Credit Card Lending** | **Scaled Linear Regression** | Bank Rate, CPI, GDP, Unemployment, Credit Card Lag | ** 0.9459** | 196.90 | 236.07 |
| **Economic Regime** | **Logistic Classifier** | Bank Rate, CPI, GDP, Unemployment | **.9103 ** | ROC-AUC: 0.8958 | F1: 0.60 |



## 3. Quickstart & Local Installation

### Prerequisites
* **Python 3.10+**
* **Node.js 18+** & **npm**

### Step 1: Clone Repository

git clone https://github.com/your-username/msc-dsr-projects-group-12.git
cd msc-dsr-projects-group-12


### Step 2: Install Backend Dependencies

python -m venv .venv
 On Windows:
.venv\Scriptsctivate

### Step 3: Install Frontend Dependencies
`ash
npm install
npm --prefix ./frontend install
`

### Step 4: Run Application
Start both Backend and Frontend concurrently with a single command:
`ash
npm run dev
`

* **Frontend Dashboard**: [http://localhost:3000](http://localhost:3000)
* **Backend API Docs (Swagger UI)**: [http://localhost:8000/docs](http://localhost:8000/docs)
* **API Health Check**: [http://localhost:8000/health](http://localhost:8000/health)

---

## 4. Deployment Guidelines for GitHub

1. **Large File Handling**: Large databases (*.db, synthetic_bank.db) and build caches (.next/, 
ode_modules/, __pycache__/) are excluded in .gitignore to keep the repository compact, fast, and compliant with GitHub's file size limits.
2. **Offline-First Compatibility**: All fonts, icons, and chart packages are bundled locally without relying on external CDNs.
3. **Environment Security**: Sensitive keys and production secrets should be managed using environment variables (refer to .env.example).

---

## 5. Authors & Research Attribution

**MSc Data Science Dissertation Project**  


* **Saketh Pakala Sivasubramanyam**

