# Creating Q Tables and the Bellman Equation

## Objective
- To explain the **Bellman equation**.  
- To create **Q tables (state-action tables)**.

## Explanation with the Marshmallow Example 🍬

### Scenario
A child either **eats the marshmallow now (action 1)** or **waits to earn two marshmallows (action 2)**.

### R (Reward) Table
- There are two columns: **Eat** and **Wait**  
- **Eating at any time → 1 point**   
- **Waiting until the end → 2 points** ⏳  
- At the beginning, the reward for the “wait” action is mostly **0** (no immediate reward).  
- Only near the final step does "wait" get the **actual reward = 2**.

### Problem
- The R table only contains immediate rewards.  
  → The value of intermediate steps is unknown.  
  → If we look only at R, **we cannot understand what to do at each step**. ❌

## Solution: Bellman Equation

### Equation
\[
Q(s, a) = R(s, a) + \gamma \cdot \max Q(s', a')
\]

### Terms
- **S** → Current state  
- **A** → Set of possible actions  
- **I** → A specific action chosen from the set  
- **R** → Reward table (immediate rewards)  
- **Q** → Learned Q table (past + estimated future rewards)  
- **γ (gamma)** → Learning rate (how much future rewards are valued)

#### Effect of Gamma
- **γ = 0** → Q = R, meaning **no learning** ❌  
- **γ > 0** → Future rewards are considered → **Learning starts** ✔️

## How to Apply? 🔄

1. **Start from the last step** (e.g., minute 7).  
   - “wait” action reward is **2 points**   
   - So: Q(7, wait) = 2

2. **Go back one step (minute 6):**  
   - R(6, wait) = 0 (no immediate reward)  
   - Q(6, wait) = R(6, wait) + γ × max Q(7, a)  
   - max Q(7, a) = 2  
   - γ = 0.9  
     → Q(6, wait) = 0 + 0.9 × 2 = **1.8**

3. **Repeat backward for all steps.**  
   - Q table is filled **step by step**.

## What the Bellman Equation Provides

- It considers **not only immediate rewards** but also **future rewards**.  
  → The agent evaluates not just the reward of the current action, but also the **best possible future rewards**.

- It enables learning by **updating Q-values (state-action values) step by step**.  
  → This allows the agent to estimate **which action is more profitable in the long run** for each state.

- With the learning rate **gamma (γ)**, it lets us control **how much importance is given to future rewards**.  
  → The model can benefit from both **past experiences** and **future potential rewards** in a balanced way.

- As a result, the agent can discover the **optimal strategy** — the action sequence that leads to the **highest total reward**. 🏆

## Classic RL vs Deep RL 🤖

- **Classic RL:**  
  - Q values stored in a **table (Q-table)**.  
  - Computation gets harder as table grows.

- **Deep RL:**  
  - Q values predicted by a **neural network**.  
  - Better for large state-action spaces.
