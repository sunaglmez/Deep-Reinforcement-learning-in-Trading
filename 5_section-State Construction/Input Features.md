# Input Features in Reinforcement Learning

This section explains more advanced **input features** used to create a **state** in **Reinforcement Learning (RL)** algorithms.  
The goal is to enable agents to make more **predictive** and **stable** decisions.

## 1. Chart Patterns

- Based on relationships between OHLC (Open, High, Low, Close) data.
- Instead of using raw returns:
  - **Positive change → +1**
  - **Negative change → -1**
- This helps the system process patterns more easily.
- For the same reason, "price change" is also used as an input.

## 🕓 2. Time Information (Time of Day, Week, Month)

- Markets may operate 24/7 (e.g., Forex, Futures).
- However, certain periods show:
  - **High volatility**
  - **Lack of liquidity**
  - **Wide spreads**
  - **Roll/expiry dates of futures contracts**

- During such anomaly periods, the system may:
  - ⚠️ Avoid risk  
  - Or take advantage of unique opportunities

## 🌐 3. Cross-Market Features

- For an asset like **DXY (USD Index)**:
  - Crude oil and gold futures prices  
  - Bond interest rates  
  - Other currencies  
  - Stock indices

- ⚠️ These time series are usually **non-stationary**
  - Solution:
    - Technical indicators  
    - **Fractional differencing**

## 🕰️ 4. Lookback & Granularity

- Longer lookback windows → Produce **smoother** signals.
- Different time scales should be considered:
  - Example: Calculate the RSI indicator for **10 minutes, 10 hours, and 10 days**.

- This way, the system can learn both **short-term** and **long-term** dynamics.

## 5. Alternative Data

- **News sentiment analysis**  
- **Satellite images**  
- **Example: CEO golf score**
  - The time a CEO spends on the golf course was used to estimate company performance.
  - A **negative correlation** was observed.

## 6. Information Coefficient (IC)

- An ideal input should have:
  - **High correlation with future returns**  
  - **Low correlation with other inputs**

- **Information Coefficient (IC)** measures:
  - The consistency between predicted values and actual outcomes.
