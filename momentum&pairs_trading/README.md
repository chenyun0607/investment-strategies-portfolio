# Momentum Investing & Pairs Trading

This repository contains implementations, analysis, and backtests of **quantitative trading strategies**, focusing on **Momentum Investing** and **Pairs Trading**. The work is based on research and projects from the Department of Statistics at Rice University.

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

## Data
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


---

## Findings & Insights

Our analysis across multiple strategies led to several key takeaways:

1. **Momentum Persistence**
   - Momentum is weak at short horizons (daily, weekly) but **more persistent at monthly and yearly horizons**.
   - Intermediate-term lookbacks (e.g., 12 months) provided the most reliable signals.

2. **Cross-Sectional Momentum**
   - Seasonal rebalancing (quarterly) generated **higher cumulative returns** (≈ 378%) than classic semiannual rebalancing (≈ 284%).  
   - However, this came at the cost of **higher volatility and drawdowns**, showing a clear return–risk tradeoff.

3. **Time-Series Momentum**
   - Short-term models (21- or 63-day) often underperformed due to **whipsaw trades and high volatility**.  
   - The **252-day lookback** strategy produced **more stable and positive returns**, though it still lagged buy-and-hold in absolute performance.

4. **Pairs Trading**
   - **Cointegration-based methods** outperformed correlation- and distance-based approaches, offering statistically validated long-term relationships.  
   - **Machine learning (PCA + KMeans)** improved pair selection by clustering stocks with similar behavior, leading to stronger mean-reversion trades (e.g., MKC & WAB).

5. **Cross-Asset Enhancements**
   - The Improved Cross-Asset TSMOM (I-XTSM) using industrial metals as an external signal significantly **reduced drawdowns** and outperformed standard momentum in stress periods (e.g., 2008).  
   - Demonstrates the value of integrating **macro signals** for crash protection.

6. **Limitations**
   - Backtests assume **frictionless markets** (no transaction costs/slippage).  
   - Real-world performance may differ due to market impact, regime shifts, and execution costs.

**Overall takeaway:**  
- Momentum strategies work best at **intermediate horizons**,  
- Pairs trading is strongest when backed by **cointegration or ML-based selection**,  
- And **cross-asset signals** can help mitigate the risks of momentum crashes.

