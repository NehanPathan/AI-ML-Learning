# Flappy Bird DQN Autonomous Agent

An autonomous Deep Q-Network (DQN) agent that learns to play **Flappy Bird** using **PyTorch** and **flappy-bird-gymnasium**.

---

## 📂 Project Architecture

```
Flappy_Bird_Game/
├── agent.py               # Main DQN Agent implementation, training loop, and evaluation
├── dqn.py                 # PyTorch Neural Network architecture (Q-function approximator)
├── experience_replay.py   # ReplayMemory buffer for experience replay (decoupling transitions)
├── game_flappy_bird.py    # Game environment runner and rendering script
├── parameters.yaml        # YAML configuration for hyperparameters and training regimes
└── runs/                  # Saved model checkpoints, training logs, and performance metrics
```

---

## 🧠 Core DQN Features Implemented

1. **Experience Replay Buffer (`experience_replay.py`)**:
   - Stores transitions $(s, a, r, s', \text{done})$ in a circular deque memory.
   - Breaks temporal correlations between consecutive steps by sampling mini-batches uniformly.
2. **Target Network Stabilization**:
   - Uses two networks: Policy Network ($Q_\theta$) and Target Network ($Q_{\theta^-}$) to eliminate moving target divergence during Bellman updates.
3. **$\epsilon$-Greedy Exploration & Decay**:
   - Starts with high exploration ($\epsilon_{\text{init}} = 1.0$) to explore actions, decaying over episodes down to $\epsilon_{\text{min}}$ (e.g. 0.05).
4. **Declarative Configuration (`parameters.yaml`)**:
   - Centralized YAML configuration enabling parameter tuning (learning rate $\alpha$, discount factor $\gamma$, replay buffer size, batch size) without altering code.

---

## 🚀 How to Run

### 1. Requirements
```bash
pip install torch gymnasium flappy-bird-gymnasium pyyaml
```

### 2. Training the Agent
```bash
python agent.py --train
```

### 3. Watching the Trained Agent Play
```bash
python game_flappy_bird.py
```

---

## ⚙️ Key Hyperparameters (`parameters.yaml`)

- `alpha` ($\alpha$): Learning rate for the optimizer (e.g., $1 \times 10^{-4}$)
- `gamma` ($\gamma$): Discount factor for future rewards (e.g., $0.99$)
- `epsilon_init` / `epsilon_min` / `epsilon_decay`: Exploration rate schedule
- `replay_memory_size`: Capacity of experience replay buffer
- `batch_size`: Mini-batch size sampled for gradient descent
