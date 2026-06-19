
# Stock Price Prediction using ML & LSTM

A complete end-to-end Machine Learning project that predicts stock prices using **Linear Regression**, **Random Forest**, and **LSTM (Long Short-Term Memory)** neural networks — with a deployed **Streamlit web app**.

Built as part of an ML internship program.

---

##  Project Overview

Stock price prediction is a **regression + time series** problem. This project fetches real historical stock data, engineers financial indicators as features, trains three ML models, evaluates them, and deploys an interactive web app where any stock ticker can be analyzed.

---

## Live Demo

> Run locally or deploy via Streamlit — see setup instructions below.



---


##  Project Phases

| Phase | Description |
|-------|-------------|
| Phase 1 | Problem Understanding — Regression vs Classification, Time Series concept |
| Phase 2 | Data Collection — yfinance, OHLCV data, 5 years of AAPL |
| Phase 3 | EDA — Moving averages, daily returns, volume analysis, correlation heatmap |
| Phase 4 | Feature Engineering — RSI, MACD, EMA, lag features, volatility |
| Phase 5 | Preprocessing — MinMaxScaler, sliding window sequences (60 days) |
| Phase 6 | Model Building — Linear Regression, Random Forest, LSTM |
| Phase 7 | Evaluation — MAE, RMSE, MAPE in real USD, predicted vs actual plots |
| Phase 8 | Deployment — Streamlit web app with dynamic date validation |

---

##  Models Used

### 1. Linear Regression
- Baseline model
- Flattened 2D input (919, 780)
- Fast and simple

### 2. Random Forest
- 100 decision trees
- Non-linear pattern learning
- Feature importance analysis

### 3. LSTM (Long Short-Term Memory)
- 2-layer LSTM: 128 units → 64 units
- Dropout (20%) for regularization
- Early stopping to prevent overfitting
- Input shape: (60 days × 13 features)

---

##  Features Engineered

| Category | Features |
|----------|----------|
| Trend | MA_20, MA_50, EMA_12, EMA_26 |
| Momentum | RSI_14, MACD, MACD_Histogram |
| Volatility | Price_Range, Volatility_20 |
| Lag | Lag_1, Lag_2, Lag_3 |
| Volume | Volume_Ratio |

---

##  Results (AAPL — 2021 to 2026)

| Model | MAE | RMSE | MAPE |
|-------|-----|------|------|
| Linear Regression | $2.33 | $3.04 | 1.36% |
| Random Forest | $7.99 | $10.99 | 4.35% |
| LSTM | $4.80 | $5.56 | 2.71% |

> LSTM average error of **$4.80 on a ~$190 stock = 2.71% error rate**

---

## 🛠️ Tech Stack

- **Python 3.10+**
- **yfinance** — stock data fetching
- **pandas / numpy** — data manipulation
- **matplotlib / seaborn** — visualization
- **scikit-learn** — Linear Regression, Random Forest, MinMaxScaler
- **TensorFlow / Keras** — LSTM neural network
- **Streamlit** — web app deployment
- **pyngrok** — Colab tunneling

---

##  How to Run

### Option 1 — Google Colab (Recommended)

1. Open `notebook.ipynb` in Google Colab
2. Run all cells top to bottom
3. For the app, get a free token from [ngrok.com](https://ngrok.com)
4. Run the launch cell — click the generated URL

### Option 2 — Local Setup

```bash
# 1. Clone the repo
git clone https:/gulrafia93-rgb/github.com//stock-price-prediction.git
cd stock-price-prediction

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the Streamlit app
streamlit run stock_app.py
```

---

##  requirements.txt

```
yfinance
pandas
numpy
matplotlib
seaborn
scikit-learn
tensorflow
streamlit
pyngrok
```

---

## App Features

-  Enter **any stock ticker** (AAPL, TSLA, GOOGL, AMZN...)
-  **Dynamic date range** — defaults to last 5 years automatically
-  **Date validation** — warns if range is too short
-  Choose **one model or all three**
-  Live **metric cards** — MAE, RMSE, MAPE
-  **Predicted vs Actual** price charts
-  **Comparison table** of all models
-  Raw data expander

---

##  Key Concepts Learned

- **Time Series vs Classification** — why order matters, no shuffling
- **Sliding Window** — how LSTM sequences are built (60-day lookback)
- **Feature Engineering** — RSI, MACD, EMA from scratch
- **MinMaxScaler** — why scaling is critical for neural networks
- **Inverse Transform** — converting scaled predictions back to USD
- **Regression Metrics** — MAE, RMSE, MAPE vs accuracy
- **Early Stopping** — preventing LSTM overfitting
- **Data Leakage** — why lag features must use shift()

---

## Disclaimer

This project is for **educational purposes only**. Stock price predictions are not financial advice. Markets are inherently unpredictable and past patterns do not guarantee future results.

---

##  Author

**Rafia**
Computer Science Student — Northern University Nowshera
4th Semester | ML Intern
[GitHub](https://github.com/gulrafia93-rgb)

---

##  License

This project is open source under the [MIT License](LICENSE).
