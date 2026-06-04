# 🧠 Flappy Bird RL Agent

This project implements a **Deep Q-Network (DQN) agent** to play the classic **Flappy Bird** game using **Reinforcement Learning (RL)**.  
The agent learns through trial and error, balancing exploration and exploitation, and gradually improves its performance to achieve higher scores.

---

## 🚀 Project Overview
- Environment built with **Pygame**.
- Agent trained using **DQN** with **Experience Replay** and a **Target Network**.
- Implements **epsilon-greedy policy** with decay for exploration.
- Modular design for experimenting with different RL algorithms.

---

## 🛠️ Requirements
- Python 3.x
- Pygame
- NumPy
- PyTorch or TensorFlow

Install dependencies:
```bash
pip install pygame numpy torch tensorflow
```

---

## ⚙️ Setup & Training Workflow
The training process follows these key steps:

1. **Set Env**  
   - Initialize the Flappy Bird environment (`flappy_env.py`).
   - Define state space (bird position, velocity, pipe positions) and action space (flap or no action).

2. **Define DQN**  
   - Build a neural network to approximate Q-values for each action.

3. **Create the Experience Replay**  
   - Store past experiences `(state, action, reward, next_state)` in a replay buffer.
   - Sample mini-batches to break correlation and stabilize training.

4. **Multiple Episodes DQN Train → Setup**  
   - Run multiple episodes where the agent interacts with the environment.
   - Update Q-values using the Bellman equation.

5. **Epsilon-Greedy Policy + Hyperparams (Epsilon Decay)**  
   - Start with high exploration (random actions).
   - Gradually decay epsilon to favor exploitation (choosing best-known actions).

6. **Target Network**  
   - Maintain a separate target network to stabilize learning.
   - Update periodically with weights from the main network.

7. **Train & Test**  
   - Train the model across thousands of episodes.
   - Test the trained agent by letting it play Flappy Bird autonomously.

👉 **Tip:** Train the model as much as you can — more episodes generally lead to better results and higher rewards.

---

## ▶️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Qazim-07/FlappyBird-RL-Agent.git
   cd FlappyBird-RL-Agent
   ```
2. Train the agent:
   ```bash
   python train_agent.py
   ```
3. Test the trained agent:
   ```bash
   python play_agent.py
   ```

---

## 📂 Project Structure
```
FlappyBird-RL-Agent/
│── assets/              # Game images (bird, pipes, background)
│── flappy_env.py        # Flappy Bird environment (Pygame)
│── train_agent.py       # Training script (DQN)
│── play_agent.py        # Run trained agent
│── models/              # Saved models/checkpoints
│── README.md            # Documentation
```

---

## 📊 RL Concepts Used
- **State Representation**: Bird position, velocity, pipe positions.
- **Action Space**: Flap or do nothing.
- **Reward Function**: +1 for passing pipes, negative reward for collisions.
- **Algorithm**: Deep Q-Network (DQN) with replay buffer and target network.

---

## 🚀 Future Improvements
- Implement advanced algorithms (PPO, A3C, Double DQN).
- Add training progress visualization (TensorBoard/Matplotlib).
- Experiment with reward shaping for faster learning.
- Improve graphics and add sound effects.

---

## 📜 License
This project is open-source. Feel free to use, modify, and improve it!
