# Elements of Reinforcement Learning

The three main components in the **Reinforcement Learning (RL)** process are:
- **State**
- **Action**
- **Reward**

## 🕹️ Example: Pong Game

We can use the famous 1980s game **Pong** as an example.

- **Actions**: Move up, move down, or stay still.
- Each action is taken at a specific **time step (T)**.

Based on this, we can move on to a trading application:

- An investor usually has three choices: **Buy, Hold, Sell**.
- These decisions are also actions taken at each time step.

## What is a State?

- **In Pong**: The position of the ball and paddle = current **state**.
- **In financial markets**: Market data (e.g., chart view) = state.

### Example:

On June 29, 2020, Tesla's **OHLC (Open, High, Low, Close)** data is taken.

But these numbers alone don’t provide enough **state information**. A more meaningful structure is needed.

## 🔍 How to Build Better State Information?

### Simple approach:
- Compare only the last closing price with the previous one.

### More advanced approach:
- Use the last N closing prices.
- Add technical indicators:
  - **Moving Averages**
  - **RSI (Relative Strength Index)**
  - **Momentum**
  - **Volatility**

## What is an Action?

### In Pong:
- The user’s move: up, down, or wait

### In Financial Trading:
- The investor's decision at each time step:
  - `Buy`
  - `Hold`
  - `Sell`

- When a `state` is observed, the system chooses an `action`.
- The selected action determines the investment outcome.
- The choice of action depends on past experience and the current `state`.

### Timeframe difference:
- The RSI indicator can be applied to minute, hourly, or daily charts.
- This provides information from different time scales.

All this data is combined to form the **State vector at time t (Sₜ)**.

## 👤 Human Investor Analogy

This state works just like a **human investor looking at the market and making a decision**.

- The decision is based on current price, indicators, and past experience.

## 📈 When and How is the Reward Determined?

> So what should the investor do on June 30?

As a result of the decision (action) taken, a **reward** is received.

But:

- This reward is only known **in the future**.
- For example: Buying the stock now → if the price rises later = reward, if it falls = penalty.
