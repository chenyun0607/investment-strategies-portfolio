# ETF Risk–Return Analysis

## Overview
This project analyzes the historical return and risk characteristics of a variety of Exchange-Traded Funds (ETFs), including:

- **GICS Sector ETFs** (e.g., XLF, XLK, XLE, XLY, XLV, XLP, XLI, XLU, XLB, XLRE, XLC)
- **Market Index ETFs** (SPY, IWM)
- **Style & Factor ETFs** (VUG, VTV, MTUM)
- **Alternative Strategy ETFs** (DBV – carry trade, VXX – volatility)

The analysis evaluates both **short-term** and **long-term** performance, using metrics such as average and median returns, Compound Annual Growth Rate (CAGR), Sharpe ratios, Value at Risk (VaR), Conditional VaR (CVaR), and Maximum Drawdown (MDD).

---

## Data
- **Source:** Yahoo Finance (via [`yfinance`](https://pypi.org/project/yfinance/))
- **Period:** 1993 – January 2025
- **Frequency:** Daily closing prices

---

## Methodology
The project covers:

1. **Return Calculations**
   - Average & median returns across daily, weekly, monthly, yearly, and 10-year rolling windows
   - CAGR for 1, 3, 5, and 10-year periods (rolling)

2. **Risk Metrics**
   - Daily volatility (standard deviation of returns)
   - Historical simulation-based VaR and CVaR at 1% and 5% confidence levels
   - Sharpe ratios (using US T-Bill rate as risk-free rate)
   - Maximum Drawdown for an equally weighted portfolio of 11 GICS sector ETFs

3. **Statistical Distribution Analysis**
   - Skewness, kurtosis, and histogram analysis for SPY returns

4. **Visualizations**
   - Price series plots
   - Return vs. volatility scatterplots (mean & median)
   - Cumulative returns and drawdown plots

---

## Key Findings
- **Broad market ETFs** like SPY and VTV offer consistent long-term growth with moderate volatility.
- **Momentum (MTUM)** and **growth (VUG)** ETFs show high risk-adjusted returns.
- **Volatility ETF (VXX)** has high volatility, negative long-term returns, and poor Sharpe ratio performance.
- **Defensive sectors** (XLP, XLV) maintain stability with lower drawdowns.
- Maximum drawdown for the equally weighted GICS portfolio was **-26.6%** during early 2020.
