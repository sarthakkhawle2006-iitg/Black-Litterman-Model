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
