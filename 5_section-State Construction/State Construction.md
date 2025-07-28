# State Construction in Reinforcement Learning for Trading

This module focuses on how to build effective **state representations** for reinforcement learning (RL) in algorithmic trading systems.

## 📌 What is a "State"?

In RL, a **state** is the input the algorithm uses to decide what action to take.  
In a trading context, this state should contain **meaningful, predictive information** about the market environment.

## Key Principles for State Construction

- ✅ **Predictive**: Features must help predict future price movements better than random.
- ✅ **Stationary**: Features should have stable statistical properties (like a stable mean).
- ❌ Raw prices are **not** stationary → avoid using them directly.

## ⚙️ Recommended Input Features

1. **Technical Indicators**:
   - RSI (Relative Strength Index)
   - MACD (Moving Average Convergence Divergence)
   - Momentum, Volatility, etc.

2. **Return-based Features**:
   - Use **percentage changes** or **log returns** instead of raw prices.
   - Pros: More stationary.
   - Cons: May lose some useful information.

3. **Advanced Techniques**:
   - 📈 **Fractional Differencing** (by Marcos López de Prado):  
     Balances stationarity and information retention.

4. **Dimensionality Reduction**:
   -  **PCA (Principal Component Analysis)** helps remove redundant, highly correlated features.

## Goal

Build a state vector that captures the market condition at time `t` in a way that is:
- Informative
- Predictive
- Compact
- Robust

This allows the RL agent to make consistent, intelligent trading decisions.
