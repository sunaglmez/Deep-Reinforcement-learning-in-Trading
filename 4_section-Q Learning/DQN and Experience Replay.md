# What is Q-Learning?

Q-Learning is a **Reinforcement Learning (RL)** algorithm that learns how much **reward** can be expected for each possible **action** in a given **state**.

## What is a Q-Table?

A Q-table contains the **expected rewards (Q-values)** for each **state-action** pair.

**Example:**

| State | Eat | Wait |
|-------|-----|------|
| S1    | 1   | 1.06 |
| S2    | 1   | 1.18 |

Here, for actions like "Eat" and "Wait", the expected rewards in different states are shown.  
These values are **updated using the Bellman equation**.

## 🧠 Deep Q-Learning

Traditional Q-learning stores a table of values for each state-action pair.  
However, in **high-dimensional environments** (e.g., financial trading), this becomes computationally expensive.

### What Changes with Deep Q-Learning?

Instead of a table, a **neural network** approximates the Q-values.

- The network **predicts the expected rewards** for each possible action given a state.
- This approach is called a **Deep Q-Network (DQN)**.

## 🔁 Experience Replay

To train the neural network, the following data is collected:

- Current state  
- Performed action  
- Received reward  
- Next state

These are stored in a memory called **replay memory**.  
During training, random samples are drawn from this memory.

**Benefits:**

- Adds diversity to training  
- Reduces overfitting  
- Makes learning more stable


## 📚 Q-Table vs R-Table

| Feature          | R-Table            | Q-Table                     |
|------------------|--------------------|-----------------------------|
| Content          | Actual reward      | Estimated (implied) reward |
| When Defined     | Predefined         | Learned through experience |
| Time Dependency  | Static             | Dynamic and evolving       |

---

The **Bellman equation** and **Q-learning** enable agents to estimate **future rewards** starting from the present.

However, classical Q-learning is inefficient in large environments.  
That’s why **Deep Q-Learning** was developed — offering a **flexible and powerful approach** using neural networks.
