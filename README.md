# Chef’s Hat Reinforcement Learning Agent  
## Opponent Modelling Variant

---

## Student Information

Student ID: 17084606  
17084606 % 7 = 0  
Assigned Variant: Opponent Modelling Variant  

---

## 1. Environment Description

This project uses the official Chef’s Hat Gym environment:

https://github.com/pablovin/ChefsHatGYM

Chef’s Hat is a competitive, turn-based, multi-agent card game environment featuring:

- Multi-agent interaction  
- Large discrete action space  
- Delayed match rewards  
- Non-stationary dynamics due to opponent behaviour  

The environment follows a Gym-compatible API and supports reproducible reinforcement learning experimentation.

---

## 2. Variant Focus: Opponent Modelling

This project investigates the impact of opponent behaviour on reinforcement learning performance.

The DQN agent was trained and evaluated against three Random agents. Random agents select valid actions without strategic reasoning.

This experimental setup allows analysis of:

- How a learning agent adapts to stochastic opponent behaviour  
- The effect of non-strategic opponents on policy development  
- Multi-agent competitive interaction  
- Non-stationarity in repeated matches  

Performance was evaluated over 100 testing matches against the same opponent configuration.

---

## 3. RL Algorithm Selection and Justification

A Deep Q-Network (DQN) agent was implemented.

DQN was selected because:

- The action space is discrete and large  
- Neural network function approximation is suitable for the state representation  
- Experience replay stabilises training  
- Target networks reduce oscillations  
- Dueling DQN improves value estimation  

The architecture includes:

- Fully connected layers (256 → 128 → 64)  
- Dueling DQN structure (Value + Advantage streams)  
- Huber loss function  
- Adam optimizer  
- Experience replay buffer  
- Epsilon-greedy exploration strategy  

This approach is appropriate for competitive multi-agent environments with delayed rewards.

---

## 4. Training Configuration

Hardware Used:
- Google Colab  
- NVIDIA Tesla T4 GPU (15GB VRAM)  

Training Setup:
- 100 matches for training  
- 100 matches for testing  
- Learning rate: 1e-4  
- Discount factor (gamma): 0.99  
- Epsilon decay for exploration  

The agent was trained exclusively against three Random agents.

---

## 5. Experimental Results

Testing Performance:

- Total Matches: 100  
- First Place Finishes: 25  
- Win Rate (1st Place): 25%  

In a four-player competitive setting, a 25% win rate indicates balanced competitive behaviour relative to random strategies.

Generated Evaluation Outputs:

- training_loss.png  
- training_positions.png  
- score_progression.png  

These demonstrate:

- Learning stabilisation over time  
- Distribution of finishing positions  
- Score comparison between DQN and Random agents  

---

## 6. Evidence of Learning

The training loss curve shows convergence behaviour over time.

Position statistics demonstrate that the DQN agent achieved competitive outcomes against Random agents.

The score progression plot indicates consistent performance relative to opponent baselines.

---

## 7. Critical Analysis and Insight

Training against Random agents exposes important aspects of opponent modelling.

Additionally, the experiment highlights how opponent behaviour influences policy learning. Since the agent was trained exclusively against Random agents, its strategy adapts specifically to stochastic and non-strategic play patterns. If the opponent configuration were changed (e.g., stronger heuristic agents or another learning agent), performance may vary significantly. This demonstrates the importance of evaluating reinforcement learning agents under varied opponent conditions to assess robustness and generalisation.

Key observations:

- The DQN agent learns patterns in stochastic opponent behaviour.  
- Performance stabilises after sufficient matches.  
- Multi-agent dynamics introduce non-stationarity.  
- Delayed match rewards complicate credit assignment.  

However, because training was conducted exclusively against Random agents, the learned policy may overfit to non-strategic behaviour.

If evaluated against stronger or adaptive opponents, performance may decrease.

Future Improvements:

- Training against mixed opponent types  
- Self-play learning  
- Double DQN implementation  
- PPO or Actor–Critic comparison  
- Robustness evaluation under varied opponent configurations  

These improvements would increase generalisation and competitive robustness.

---

## 8. Reproducibility

To reproduce results:

1. Clone the official Chef’s Hat Gym repository.  
2. Replace `agent_dqn.py` with the modified version in this repository.  
3. Run `test_room_dql_training.py`.  
4. Enable GPU for faster training.  

---

## 9. AI Use Declaration

Tool Used: ChatGPT 

Usage:
- Assisted with debugging environment setup.  
- Assisted with structuring documentation.  
- Assisted with clarifying reinforcement learning explanations.  

## Video Demonstration

Video presentation link:

https://drive.google.com/file/d/1CdnKbWBjTHWSol3G0JUOGJeO5ZfPQMXy/view?usp=drive_link

All implementation, experimentation, evaluation, and analysis were performed and fully understood by the student.
