# Policies in Reinforcement Learning

## Purpose

This section explains the concepts of **policy**, **exploration**, and **exploitation** in reinforcement learning, as well as the ideal stages of the learning process.

## What is a Policy?

A policy is the set of rules that determines what action to take when faced with a certain state. In other words, an RL agent decides which action to choose through the policy.

**Example:**  
You have a business meeting 1000 miles away. Your transportation options: plane, train, car, or a sea cruise.

- If you want to save time: take the plane  
- If you're looking for a budget-friendly option: take the train  
- If you're seeking comfort: go on a luxury cruise  

Although the goal is to reach the meeting, the paths taken are different. These paths represent different policies.

---

## 🔁 Exploration vs Exploitation

There are two main types of policies in reinforcement learning:

### Exploration

The agent chooses actions randomly to explore the environment.  
Important for discovering new strategies.

### Exploitation

The agent prefers known actions that provide the highest rewards.  
The aim is to gain immediate returns.

**Example Situation:**

- If the price moves above the average, you take a short position assuming it will revert.
- If the price rises a bit more, a greedy policy might panic and exit at a loss.
- A smarter policy sees the bigger picture, remains patient, and waits for the price to drop.

---

## Ideal Policy During Learning

At the beginning of training, there's little knowledge about the environment, so the agent follows an **exploration-heavy** policy.  
As time passes, the model gains experience and can shift toward more **exploitation-focused** behavior.

---

## 📉 Balancing Exploration & Exploitation with Epsilon (𝜺)

A parameter called **epsilon (ε)** is used to balance exploration and exploitation.

- Epsilon is in the range \[0, 1].
- At each time step, a random number between \[0,1] is generated:

  - If the number < epsilon → **exploration** is performed (a random action is chosen).
  - Otherwise → **exploitation** is performed (the best action predicted by the Q-network is chosen).

### Epsilon Decay

- Initially: epsilon = 1 → Full exploration  
- Over time: epsilon is reduced (e.g., 0.8, 0.5...), lowering exploration and increasing exploitation.  
- This transition enables the RL agent to make more accurate decisions as learning progresses.

---

## 🔄 Learning and Policy Execution

As games (or trades) progress:

- The agent gains experience, and the Q-network is trained.
- Epsilon is gradually reduced.
- More exploitation is done, and less exploration occurs.
