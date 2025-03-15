# 🚀 Tesla Stock Price Prediction

## 📈 A deep dive into forecasting Tesla's stock price using Machine Learning and Deep Learning.

## 📌 Overview
This project applies time series analysis on Tesla's stock prices using:
- **SARIMA**
- **LSTM (Deep Learning)**
- **XGBoost**
- **Prophet**
- **NeuralProphet**
- **Hybrid Stacking Model (LSTM + XGBoost + Prophet)**

## 📊 Key Features
✔️ Data Preprocessing & Cleaning  
✔️ Stationarity Tests (ADF Test)  
✔️ Time Series Decomposition  
✔️ Advanced Forecasting Models  
✔️ Model Comparison & Evaluation  

## 🔧 Setup
```bash
pip install -r requirements.txt
```

## 📁 File Structure
```bash
📂 src
 ├── data_processing.py
 ├── sarima_model.py
 ├── lstm_model.py
 ├── xgboost_model.py
 ├── prophet_model.py
 ├── hybrid_model.py
 ├── app.py  # Streamlit dashboard (if applicable)
📂 data
 ├── TSLA_stock.csv
📂 notebooks
 ├── EDA.ipynb
 ├── Modeling.ipynb
```

## 📜 Results
✅ **SARIMA** - Short-term accuracy  
✅ **LSTM** - Captured trends well  
✅ **XGBoost** - Fast & efficient  
✅ **Prophet & NeuralProphet** - Seasonal patterns  
✅ **Hybrid Model** - Best overall performance  

## 📌 Project Summary
### **Key Questions Addressed**
1. **How has Tesla’s stock price changed over time?**
   - Visualized historical stock prices.
   - Identified trends and patterns.
2. **Is the stock price data stationary?**
   - Applied **Augmented Dickey-Fuller (ADF) test** to check for stationarity.
   - Used differencing to make the series stationary.
3. **What are the underlying components of Tesla's stock price?**
   - Used **Seasonal Decomposition of Time Series (STL Decomposition)** to separate **trend, seasonality, and noise.**
4. **What forecasting model works best for Tesla's stock price?**
   - Implemented and compared **SARIMA, LSTM, XGBoost, Prophet, Bayesian Ridge, and NeuralProphet models.**

### 📊 **Step-by-Step Process Followed**
#### **1️⃣ Data Collection & Preprocessing**
- **Dataset Source**: MacroTrends Tesla Stock Price Data.
- **Steps Taken:**
  - Loaded **CSV file**.
  - Checked for missing values.
  - Renamed and formatted columns.
  - Converted the `date` column to `datetime` format.
  - Set `date` as the index and sorted the dataset.

#### **2️⃣ Exploratory Data Analysis (EDA)**
- **Visualized Stock Prices Over Time:**
  - Plotted **Tesla’s closing price** over time.
  - Identified **upward trends and fluctuations.**
- **Checked for Stationarity:**
  - Performed **ADF Test**.
  - **Results:**
    - Initial test: ❌ **Stock price is NOT stationary**.
    - Applied **first-order differencing**.
    - Re-tested: ✅ **Stock price is now stationary**.

#### **3️⃣ Trend and Seasonality Analysis**
- **Used STL Decomposition:**
  - **Trend**: Showed an overall increase in stock price with fluctuations.
  - **Seasonality**: Identified **recurring patterns**, likely based on **market cycles or earnings reports**.
  - **Residuals (Noise)**: Captured random fluctuations.

#### **4️⃣ Forecasting Models Used**
- **📌 SARIMA Model**
  - Found optimal `(p, d, q)` parameters using **Auto-ARIMA**.
  - Trained a **SARIMA(2,1,2)x(1,1,1,12)** model.
  - **Output:** Successfully trained model with AIC/BIC evaluation.

- **📌 LSTM (Long Short-Term Memory) Model**
  - Created **time sequences (60-day window).**
  - Built and trained an **LSTM model** with:
    - **Two LSTM layers (128 and 64 neurons).**
    - **Dropout layers to prevent overfitting.**
  - **Output:** Trained over 50 epochs with low MSE loss.

- **📌 XGBoost Model**
  - Used **closing price and volume** as features.
  - Trained **XGBoost model** on historical data.
  - **Output:** Made **accurate predictions on test data**.

- **📌 Prophet Model (by Facebook)**
  - Converted dataset to `ds` (date) and `y` (close price).
  - Trained **Prophet model** with daily seasonality.
  - **Output:** Forecasted future stock prices with **confidence intervals**.

- **📌 Hybrid Stacked Model**
  - Stacked predictions from **LSTM, XGBoost, and Prophet**.
  - Used **Bayesian Ridge Regression** to blend models.
  - **Output:** Final hybrid model produced smoother predictions.

- **📌 NeuralProphet Model**
  - Installed and configured **NeuralProphet**.
  - Trained on Tesla stock price data.
  - **Output:** Generated forecasts with improved trend modeling.

## 📉 Final Outputs & Findings
✅ **Stock price is non-stationary initially but can be made stationary with differencing.**  
✅ **SARIMA performed well for short-term forecasting.**  
✅ **LSTM captured trends well but required significant training time.**  
✅ **XGBoost provided fast and accurate results.**  
✅ **Prophet and NeuralProphet handled seasonality effectively.**  
✅ **The Hybrid Model (LSTM + XGBoost + Prophet) gave the best overall predictions.**  

## 📌 Next Steps & Improvements
🔹 **Improve Feature Engineering** – Include macroeconomic indicators (interest rates, inflation, etc.).  
🔹 **Optimize Model Parameters** – Perform **hyperparameter tuning** for better accuracy.  
🔹 **Deploy the Model** – Use **Flask, FastAPI, or Streamlit** to build an interactive dashboard.  
🔹 **Test on Other Stocks** – Extend the approach to different stocks or cryptocurrencies.  

## 📢 Contributing
Feel free to fork this repository, create a branch, and submit a PR! 🚀
