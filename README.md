# DQN-Gridworld-Navigation
A reinforcement learning project implementing a Deep Q-Network agent that learns goal oriented navigation in a custom grid environment, with policy evaluation, visualization, and analytics.
# DQN-Gridworld-Navigation

A reinforcement learning project implementing a Deep Q-Network (DQN) agent that learns optimal goal-oriented navigation in a custom grid environment.

## 🎯 Project Overview

This project demonstrates core reinforcement learning concepts by training a DQN agent to efficiently navigate a grid world from start position to goal, while avoiding obstacles. The agent learns through trial-and-error using Q-learning, exploring the environment with an epsilon-greedy strategy.

## 🧠 Algorithm Details

### Deep Q-Network (DQN)
- **Learning Approach**: Value-based reinforcement learning with function approximation
- **Experience Replay**: Stores and randomly samples past experiences to break correlation between training samples
- **Epsilon-Greedy Exploration**: ε starts high (0.9) and decays gradually to enforce exploration → exploitation tradeoff
- **Target Network**: Separate neural network to stabilize training (fixed updates)

### Key Components
1. **State Space**: Grid position coordinates
2. **Action Space**: 4-directional movement (Up, Down, Left, Right)
3. **Reward Function**:
   - +100 for reaching goal
   - -1 per step (encourages efficiency)
   - Large penalty for hitting walls/obstacles
4. **Network Architecture**: Simple multi-layer perceptron (input → hidden → output)

## 🔧 Technical Stack

- **Language**: Python 3.8+
- **Libraries**: NumPy, TensorFlow/PyTorch, Matplotlib
- **Concepts**: Q-Learning, Neural Networks, Experience Replay, Markov Decision Process (MDP)

## 📊 How It Works

### Training Process
1. Initialize DQN agent with random weights
2. For each episode:
   - Agent starts at random position
   - Uses ε-greedy policy to select actions
   - Collects (state, action, reward, next_state) transitions
   - Stores in experience replay memory
   - Samples mini-batches and trains neural network
   - Updates target network periodically
3. Epsilon decays over time to reduce exploration

### Convergence
- Episodes measure performance improvement
- Reward per episode increases as agent learns
- Eventually agent finds near-optimal path to goal

## 📈 Results & Performance Metrics

- **Training Convergence**: Agent learns efficient navigation within 500-1000 episodes
- **Path Efficiency**: Achieves paths close to optimal A* pathfinding
- **Stability**: Experience replay prevents divergence in Q-values

## 🚀 How to Run

```bash
# Clone repository
git clone https://github.com/JanhaviK30/DQN-Gridworld-Navigation.git
cd DQN-Gridworld-Navigation

# Install dependencies
pip install numpy tensorflow matplotlib

# Run training
python dqn_agent.py

# Visualize learned policy
python visualize_policy.py
```

## 📁 File Structure

```
├── dqn_agent.py          # Main DQN implementation
├── gridworld.py          # Custom grid environment
├── train.py              # Training loop
├── visualize_policy.py   # Visualization of learned policy
└── README.md
```

## 💡 Key Learning Points

This project demonstrates proficiency in:
- ✅ Reinforcement learning fundamentals (MDP, Q-learning)
- ✅ Neural network implementation and training
- ✅ Exploration-exploitation tradeoff strategies
- ✅ Experience replay for stable learning
- ✅ Policy evaluation and visualization
- ✅ Algorithm optimization and convergence analysis

## 🔬 Future Enhancements

- Implement prioritized experience replay for better sample efficiency
- Add Double DQN for reduced overestimation bias
- Implement Dueling DQN architecture
- Extend to continuous action spaces
- Multi-agent scenarios

## 📚 References

- Mnih et al. (2015) - Playing Atari with Deep Reinforcement Learning
- Richard Sutton & Andrew Barto - Reinforcement Learning: An Introduction
- OpenAI Spinning Up in Deep RL

## 📝 License

MIT License - Feel free to use for educational and research purposes

---

**Interested in contributing?** Feel free to fork and submit PRs!
