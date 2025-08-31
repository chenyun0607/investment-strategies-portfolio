# Investment Strategies Portfolio

This repository contains implementations, analysis, and backtests of **quantitative trading strategies**, focusing on **Momentum Investing** and **Pairs Trading**. The work is based on research and projects from the Department of Statistics at Rice University (STAT 686 – Market Model Mini Project 1).

---

## Strategies Covered

### 1. Momentum Investing
- **Cross-Sectional Momentum**
  - Classic 12-month lookback with semiannual rebalancing
  - Seasonal adjustment strategy using quarterly comparisons  
- **Time-Series Momentum (TSMOM)**
  - Short (21 days), medium (63 days), and long-term (252 days) lookbacks  
- **Cross-Asset Momentum Enhancements**
  - Improved Cross-Asset TSMOM (I-XTSM) using Industrial Metals Index (GSCI-IND)  
  - Style momentum exploration across equities, bonds, FX, and commodities  

### 2. Pairs Trading
- **Statistical Arbitrage Approaches**
  - Correlation-based  
  - Cointegration-based  
  - Distance-based  
- **Machine Learning Extension**
  - PCA + KMeans clustering for candidate selection  
  - Engle-Granger cointegration test for robust pair identification  
  - Example: MKC & WAB mean-reversion trading strategy  

---

## 📊 Data
- Primary: **S&P 500 constituents** (daily price data, 2005–2024)  
- Sources:  
  - [Yahoo Finance API (`yfinance`)](https://pypi.org/project/yfinance/)  
  - CRSP via Wharton Research Data Services (WRDS)  
- Additional:  
  - Healthcare sector subset (50 stocks)  
  - Industrial Metals Index (GSCI-IND)  

---

## Methodology
- Return calculation across multiple horizons (daily, weekly, monthly, yearly)  
- Autocorrelation function (ACF) for persistence/reversal detection  
- Backtesting metrics: cumulative return, Sharpe ratio, max drawdown, avg win/loss  
- Assumptions: frictionless markets, no arbitrage, persistence of momentum effects  

