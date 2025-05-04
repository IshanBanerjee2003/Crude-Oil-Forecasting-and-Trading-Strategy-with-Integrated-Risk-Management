# 🛢️ Crude Oil Forecasting and Trading Strategy with Integrated Risk Management

This repository contains a complete machine learning pipeline to **forecast next-day returns for WTI crude oil** and implement a **rule-based trading strategy** using Random Forest regression. It integrates data preprocessing, model training, evaluation, and backtesting of a trading strategy.

---

## 📈 Project Overview

This project aims to:

- Use historical financial and macroeconomic data to forecast **WTI Crude Oil (CL=F)** returns.
- Engineer time-series features and train a **Random Forest model** for prediction.
- Generate trading signals (long/short) based on predictions.
- Evaluate the profitability and performance of the resulting strategy using metrics like **Sharpe Ratio** and **cumulative return**.

---

## 📊 Dataset & Features

**Data Source**: [Yahoo Finance](https://finance.yahoo.com)

### Instruments Used:
- WTI Crude Oil Futures (CL=F)
- US Dollar Index (DX-Y.NYB)
- 10-Year Treasury Yield (^TNX)

### Engineered Features:
- Daily returns for each instrument
- Lagged returns for past 1, 2, and 3 days
- Target variable: next-day return of WTI crude oil

---

## 🧠 Machine Learning

- **Model**: Random Forest Regressor
- **Libraries**: `scikit-learn`, `pandas`, `matplotlib`, `yfinance`
- **Train/Test Split**:
  - Train: Jan 2018 – Dec 2021
  - Test: Jan 2022 – present

### 📌 Results:
- Test MSE: `0.000883`
- Test R²: `-0.6233`
- **Top Features**: Current and lagged WTI returns, Treasury yield changes

---

## 💰 Trading Strategy

A simple rule-based strategy was tested:

- **Go long** if predicted return > 0  
- **Go short** if predicted return < 0  
- **Returns** are calculated using actual next-day returns and model signal

### 📈 Performance:
- **Cumulative Return**: `+99.53%` (test period)
- **Sharpe Ratio**: `0.76`

---

## 🔧 Folder Structure

