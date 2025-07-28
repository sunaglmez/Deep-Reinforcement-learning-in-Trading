# Reward Function Design in Reinforcement Learning

## Fundamentals of Reinforcement Learning:
Reinforcement Learning (RL) allows an artificial agent to learn the best strategy in an environment through trial and error. The agent takes an action, the environment provides feedback in the form of a reward, and the agent learns what is good or bad based on this feedback.  
In essence, the agent tries to learn: “Which of my actions lead to more long-term rewards?”

## 💡 What is a Reward Function?
A reward function is a set of rules that assigns a numerical value to each action the agent takes, indicating how good or bad that action was.

## ❗ Why “Profit” Alone is Not Enough?
Especially in fields like financial trading, many attempt to base the reward function solely on “profit.” However, this is an incomplete approach. Why?

The same profit can be obtained in different ways:

- You might earn 1% profit in 2 minutes.  
- You might earn the same 1% profit in 2 years.

If you look only at the “profit” value, the system may see these two as equal — though they are actually very different scenarios.

## The Quality of Profit Matters

- Is the profit stable?  
- Or does it occur through random fluctuations?  
- Do trades last too long?  
- Is the agent trading too frequently?

If these are not considered, bad behaviors might also get rewarded. ❌

## What to Do? — Alternative Metrics
Therefore, more conscious metrics are considered:

- Profit per tick (i.e., profit normalized by trade duration)  
- Sharpe ratio (profit relative to risk)  
- Penalty for holding position too long (punish agents that keep trades open too long)

These calculations force the agent to behave more “intelligently and balanced.”

In this process, the reward function is critical. If it’s not well-defined, the agent may mistakenly interpret wrong behaviors as “good.” Learning becomes meaningless or incorrect.
