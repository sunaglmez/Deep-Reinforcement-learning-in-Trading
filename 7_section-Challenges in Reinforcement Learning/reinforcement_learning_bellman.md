# Reinforcement Learning, Q-Learning, and the Bellman Equation

## What is Reinforcement Learning (RL)?
- The agent learns through **rewards and punishments**.  
- Goal: **Maximize total reward**.  
- Learning by **trial and error**.

---

## 🔁 Markov Decision Process (MDP)
Includes:  
- **State (s)**  
- **Action (a)**  
- **Reward (r)**  
- **Transitions**  
- **Policy (π)**

---

## Q-Learning and the Bellman Equation

### What is Q-Learning?
Q-Learning is a **Reinforcement Learning** algorithm that learns how much **reward** to expect for each possible **action** in a given **state**.

### Q-Table
A Q-table stores **expected rewards (Q-values)** for every state-action pair.

**Example:**

| State | Eat | Wait |
|-------|-----|------|
| S1    | 1   | 1.06 |
| S2    | 1   | 1.18 |

These values are updated using the **Bellman equation**.

### Bellman Equation
\[
Q(s, a) = R(s, a) + \gamma \cdot \max Q(s', a')
\]

Where:  
- **s** = current state  
- **a** = action  
- **s'** = next state  
- **R(s, a)** = immediate reward  
- **γ (gamma)** = discount factor (importance of future rewards)

#### Effect of Gamma (γ)
- **γ = 0** → Q = R (no future consideration)  
- **γ > 0** → Agent considers long-term gains

---

## 🤖 Deep Q-Learning

In high-dimensional environments, Q-tables become impractical.

### What changes?
- A **neural network** approximates Q-values instead of storing them in a table.  
- This network predicts the reward for each possible action given a state.  
- This is called a **Deep Q-Network (DQN)**.

---

## 🔁 Experience Replay

To train the network, the agent collects:

- State  
- Action  
- Reward  
- Next State  

These are stored in **replay memory**, and random samples are used during training.

**Benefits:**
- Adds diversity to training  
- Reduces overfitting  
- Makes learning more stable

---

## Q-Table vs R-Table

| Feature          | R-Table            | Q-Table                     |
|------------------|--------------------|-----------------------------|
| Content          | Actual reward      | Estimated reward (learned) |
| Defined when?    | Predefined         | Learned over time          |
| Time-dependent?  | Static             | Dynamic and adaptive       |

---

## 💰 Finance/Trading Example

- **Actions**: Buy / Sell / Hold  
- **Rewards** are often **delayed**  
- Bellman allows assigning value to actions like "Hold" based on future gains

**Example Calculation**  
γ = 0.9, Q(1, a) = 1.8  
\[
Q(0, Wait) = R + 0.9 \times 1.8 = 1.62 \Rightarrow R = 0
\]

---

## What the Bellman Equation Provides

- Considers **future rewards**, not just immediate ones  
- Enables **step-by-step Q-value updates**  
- Helps balance **past experience** and **future potential**  
- Allows discovering the **optimal strategy** over time 🏆

---

## Deep RL vs Classic RL

- **Classic RL**: Q-values in tables  
- **Deep RL**: Q-values predicted by neural networks  
- Deep RL is better for large, complex environments

---

## Conclusion

- Bellman is the **core** of RL.  
- It helps agents **learn the value of waiting** or planning ahead.  
- Q-learning and Deep Q-learning make it possible to apply this idea even in **very complex environments** like finance.
