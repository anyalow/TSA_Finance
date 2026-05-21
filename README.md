# TSA in Finance: ESG vs Conventional Indices

**Authors:** Alison Barnard & Anya Low  
**Course:** Time Series Analysis in Finance (TSA01)  
**Programme:** MSc Applied Information and Data Science  
**Institution:** Hochschule Luzern (HSLU)  
**Submission deadline:** 22 May 2026

---

## Project Overview

This project investigates whether ESG-screened equity indices exhibit 
different return and volatility dynamics compared to their conventional 
counterparts, with a focus on the 2020–2024 period.

Our central research question is: Did the return and volatility dynamics 
of ESG indices change relative to conventional indices during the 
2022–2024 rising interest rate period?

---

## Data

Daily price data sourced via the Yahoo Finance API and FRED:

| Ticker | Description | Pair |
|--------|-------------|------|
| ESGU | iShares MSCI USA ESG ETF | US ESG |
| ^GSPC | S&P 500 | US Conventional |
| SUWS.L | iShares MSCI World ESG Leaders ETF | Global ESG |
| IWDA.AS | iShares Core MSCI World ETF | Global Conventional |
| DGS10 | 10-Year US Treasury Yield (FRED) | Interest Rate |

Observation period: 2 January 2020 to 31 December 2024 (1,304 trading days)

---

## Repository Structure

TSA_Finance/
│
├── data/
│   ├── prices.csv          # Cleaned daily adjusted closing prices
│   ├── log_returns.csv     # Daily log returns for all series
│   └── rate_diff.csv       # First difference of 10Y Treasury yield
│
├── Time_Series_ESG_Project.Rmd   # Main analysis file
└── README.md

---

## How to Run

1. Open `Time_Series_ESG_Project.Rmd` in RStudio
2. On first run, execute the `install-packages` chunk manually
3. Run all chunks in order : data is pulled via API and saved to `/data`
4. On subsequent runs, data loads from the saved CSVs (no internet needed)

---

## Branch Structure

- `main` : final merged version
- `alison` : Alison's working branch (descriptive analysis, regime analysis)
- `anya` : Anya's working branch (stationarity, GARCH, VAR model)

---

## Methods

- Descriptive analysis (log returns, rolling volatility, summary statistics)
- Stationarity testing (Augmented Dickey-Fuller)
- Autocorrelation analysis (ACF, PACF)
- Volatility modelling (GARCH(1,1))
- Regime analysis (pre/post 2022 subsamples)
- Multivariate modelling (VAR, Granger causality)
