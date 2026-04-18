# Black-Litterman Portfolio Optimization Model

This repository contains an implementation of the Black-Litterman model, a sophisticated mathematical approach to portfolio allocation. The model combines market equilibrium returns with specific investor views to generate optimized expected returns for a given set of assets. 

In this analysis, the model is applied to a technology-heavy portfolio consisting of Tesla (TSLA), Netflix (NFLX), Nvidia (NVDA), Advanced Micro Devices (AMD), and Microsoft (MSFT).

## Table of Contents
* [Overview](#overview)
* [Dependencies](#dependencies)
* [Methodology](#methodology)
* [Investor Views](#investor-views)
* [Results](#results)

## Overview
The traditional Markowitz Mean-Variance Optimization often results in highly concentrated portfolios that are extremely sensitive to input assumptions. The Black-Litterman model solves this by using the market's implied equilibrium returns as a starting point and adjusting them based on subjective investor views, weighted by the investor's confidence in those views.

**Assets Analyzed:**
* **Equities:** TSLA, NFLX, NVDA, AMD, MSFT
* **Market Benchmark:** S&P 500 (`^GSPC`)
* **Risk-Free Rate:** 10-Year Treasury Yield (`^TNX`)
* **Timeframe:** 1 Year (Daily Data)

## Dependencies
This project requires Python 3 and the following libraries:
* `numpy`
* `pandas`
* `yfinance`

To install the required packages, run:
```bash
pip install numpy pandas yfinance

"""
METHODOLOGY
1. Data Collection: Historical adjusted closing prices for the selected stocks, the S&P 500, and the 10-Year T-Bill are fetched using the Yahoo Finance API (yfinance).
2. Excess Returns: Daily asset returns and market returns are calculated and adjusted by subtracting the daily risk-free rate.
3. Price of Risk (A): Calculated as the ratio of the expected market excess return to the market variance.
4. Variance-Covariance Matrix (Σ): Extracted from the historical daily excess returns of the assets.
5. Market Weights (w): Calculated using the real-time market capitalizations of the 5 companies.
6. Implied Equilibrium Excess Returns (Π): The baseline returns implied by the market.
7. Integrating Views: The model scales the uncertainty of the prior market equilibrium (τ) and integrates specific investor views using a Pick Matrix (P) and a View Vector (Q).
8. Final Expected Returns: Calculated using the Black-Litterman master formula.

INVESTOR VIEWS
* View 1: Microsoft (MSFT) will outperform Tesla (TSLA) by 2%.
* View 2: Nvidia (NVDA) will outperform Advanced Micro Devices (AMD) by 4%.

RESULTS
The script outputs a contrast between the historically observed average returns of the assets and the expected returns derived from the Black-Litterman model.
"""
