# Bitcoin Price Prediction 

An end-to-end machine learning pipeline that fetches live Bitcoin/USD market data,
engineers predictive features, trains and compares three regression models, evaluates
performance with standard metrics, and produces a multi-panel analytical dashboard
with 30-day price forecasts.

---

## Features

- Live data fetching with 3-tier fallback: CoinGecko API → yfinance → synthetic
- Automated preprocessing: null removal, IQR outlier filtering, chronological sorting
- Feature engineering: log returns, MA-7, MA-21, RSI-14, rolling volatility
- Three ML models trained and compared: Linear Regression, Polynomial Regression (degree 3), Moving Average
- Evaluation metrics per model: RMSE, MAE, R²
- 30-day price forecast with visual dashed projection
- 5-panel dark-themed Matplotlib dashboard
- Real-time adaptation via adapt_model(): appends new candles and re-preprocesses without restarting
- Step-by-step console output after every pipeline stage
---

## Output

**Console** — detailed logs after every step including raw data preview,
feature stats, model coefficients, 7-day forecast preview, and a comparison table.

**Chart** — `bitcoin_prediction.png` with five panels:

| Panel | Content |
|-------|---------|
| 1 | Full price history, all model fits, and dashed 30-day forecasts |
| 2 | RMSE and MAE bar chart per model |
| 3 | R² score horizontal bar chart |
| 4 | Closing price with MA-7 and MA-21 overlay |
| 5 | RSI-14 with overbought/oversold zones highlighted |

---

## Models

| Model | How it works |
|-------|-------------|
| Linear Regression | Fits a straight trend line through day index vs price |
| Polynomial Regression | Fits a degree-3 curve to capture non-linear momentum |
| Moving Average | Rolls a 7-day mean forward iteratively for forecasting |

---

## Requirements

| Package | Purpose |
|---------|---------|
| pandas | Data manipulation and time-series handling |
| numpy | Numerical operations and array math |
| scikit-learn | ML models, preprocessing, and metrics |
| matplotlib | Multi-panel chart generation |
| requests | CoinGecko REST API calls |
| yfinance | Yahoo Finance fallback data source |
