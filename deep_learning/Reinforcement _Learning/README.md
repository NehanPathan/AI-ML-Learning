# Reinforcement Learning (RL)

From classical tabular decision algorithms to Deep Reinforcement Learning (DRL) with neural network function approximators.

---

## 📂 Directory Contents

| Path | Topic | Type |
| :--- | :--- | :--- |
| `Q_Learning.ipynb` | Tabular Off-Policy Temporal Difference Learning | Algorithm Notebook |
| `SARSA.ipynb` | Tabular On-Policy State-Action-Reward-State-Action Learning | Algorithm Notebook |
| `prac.ipynb` | Gym environment exploration and reward-shaping experiments | Experimentation |
| `Flappy_Bird_Game/` | Complete Deep Q-Network (DQN) playing Flappy Bird autonomously | Project Application |

---

## 🧭 Theoretical Foundations

Reinforcement Learning frames problems as a **Markov Decision Process (MDP)** defined by $(S, A, P, R, \gamma)$:
- **State ($S$)**: Representation of the environment.
- **Action ($A$)**: Available choices for the agent.
- **Reward ($R$)**: Feedback signal from taking action $A$ in state $S$.
- **Discount Factor ($\gamma \in [0, 1)$)**: Balances immediate vs. long-term future rewards.

### Comparison: Q-Learning vs. SARSA

| Attribute | Q-Learning (Off-Policy) | SARSA (On-Policy) |
| :--- | :--- | :--- |
| **Update Target** | Uses the maximum Q-value of next state regardless of action taken: $\max_a Q(s', a)$ | Uses the actual next action chosen by current policy: $Q(s', a')$ |
| **Update Rule** | $Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma \max_{a'} Q(s', a') - Q(s, a)]$ | $Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma Q(s', a') - Q(s, a)]$ |
| **Behavior** | Optimistic; learns the optimal policy directly | Safer; accounts for exploration risks while learning |

---

## 🕹️ Deep Q-Networks (DQN)

When the state space becomes continuous or too large for a lookup table (such as pixels or physics game states), a Neural Network approximates the action-value function:

$$Q(s, a; \theta) \approx Q^*(s, a)$$

See the [`Flappy_Bird_Game/`](Flappy_Bird_Game/README.md) subfolder for the full DQN agent, replay memory buffer, and hyperparameter configuration.
