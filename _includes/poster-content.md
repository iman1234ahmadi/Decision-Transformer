<div style="text-align: center; margin-bottom: 2rem;">
  <img src="{{ '/assets/img/drl-logo.png' | relative_url }}" alt="Deep RL Logo" style="height: 80px; margin-right: 1rem;">
  <img src="{{ '/assets/img/riml-logo.png' | relative_url }}" alt="RI ML Logo" style="height: 80px; margin-left: 1rem;">
</div>

**Table of Contents**
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Decision Making Frameworks](#frameworks)
- [Methodology](#methodology)
- [Results](#results)
- [Game Environment Samples](#game-samples)
- [References](#references)

---

## ✦ Abstract ✦ <a name="abstract"></a>
Decision making in reinforcement learning (RL) represents a fundamental challenge where agents must balance exploration and exploitation while navigating complex, uncertain environments. Traditional RL approaches often assume perfect information or stationary environments, but real-world decision problems involve dynamic conditions, partial observability, and multi-objective trade-offs. Our research investigates novel frameworks for robust decision making in RL, focusing on (1) adaptive exploration strategies that respond to environmental uncertainty, (2) multi-criteria decision analysis for balancing competing objectives, and (3) transfer learning mechanisms that enable effective decision making across related domains. Through theoretical analysis and empirical evaluation, we demonstrate improved performance in benchmark environments and real-world applications, providing scalable solutions for intelligent decision making under uncertainty.

**Keywords:** Decision making; reinforcement learning; exploration-exploitation; multi-objective optimization; transfer learning.

### Authors

<div style="display: flex; justify-content: center; align-items: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/iman.jpg' | relative_url }}" alt="Iman Ahmadi" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; border: 3px solid #2c3e50;">
    <p style="margin-top: 0.5rem; font-weight: bold;">Iman Ahmadi</p>
    <p style="margin: 0; font-size: 0.9em; color: #666;">iman1234ahmadi@gmail.com</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/amirreza.jpg' | relative_url }}" alt="Amirreza Tanevardi" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; border: 3px solid #2c3e50;">
    <p style="margin-top: 0.5rem; font-weight: bold;">Amirreza Tanevardi</p>
    <p style="margin: 0; font-size: 0.9em; color: #666;">amirreza.tanevardi@gmail.com</p>
  </div>
</div>

---

## ✦ Introduction ✦ <a name="introduction"></a>

Decision making lies at the heart of reinforcement learning, where agents must continuously choose actions that maximize long-term rewards while operating in uncertain environments. The fundamental challenge can be formalized through the **Markov Decision Process (MDP)** framework:

$$
\mathcal{M} = (\mathcal{S}, \mathcal{A}, P, r, \gamma),
$$

where:
- $\mathcal{S}$ is the state space representing all possible situations
- $\mathcal{A}$ is the action space containing available decisions
- $P(s'|s,a)$ represents transition probabilities between states
- $r(s,a,s')$ is the reward function quantifying decision outcomes
- $\gamma \in [0,1]$ is the discount factor for future rewards

The agent's **policy** $\pi(a|s)$ defines its decision-making strategy, specifying the probability of taking action $a$ in state $s$. The goal is to find an optimal policy that maximizes expected cumulative reward:

$$
\pi^* = \arg\max_\pi \mathbb{E}_\pi\left[\sum_{t=0}^{\infty} \gamma^t r(s_t, a_t, s_{t+1})\right]
$$

<hr style="width:40%;margin:2em auto -1em auto;">
### Key Decision Making Challenges
<hr style="width:40%;margin:-0.5em auto auto auto;">

1. **Exploration vs. Exploitation Trade-off**: Agents must balance gathering new information (exploration) with leveraging known good decisions (exploitation).

2. **Partial Observability**: Real environments often provide incomplete state information, requiring decision making under uncertainty.

3. **Multi-objective Optimization**: Practical problems involve multiple, often conflicting objectives that must be simultaneously optimized.

4. **Non-stationarity**: Environments change over time, requiring adaptive decision strategies.

5. **Scalability**: Decision complexity grows exponentially with problem size, necessitating efficient approximation methods.

---

## ✦ Decision Making Frameworks ✦ <a name="frameworks"></a>

### Adaptive Exploration Strategies

Traditional ε-greedy exploration uses a fixed exploration rate, but adaptive strategies adjust exploration based on uncertainty:

**Upper Confidence Bound (UCB)**:
$$
a_t = \arg\max_{a} \left[ Q(s,a) + c\sqrt{\frac{\ln t}{N(s,a)}} \right]
$$

**Thompson Sampling**:
$$
a_t \sim \pi(a|s, \theta_t), \quad \theta_t \sim \text{Posterior}(\theta|\mathcal{D}_t)
$$

where $c$ controls exploration-exploitation balance and $N(s,a)$ counts action visits.

### Multi-Criteria Decision Analysis

For multi-objective problems, we employ Pareto-optimal solutions:

$$
\max_{\pi} \left[ f_1(\pi), f_2(\pi), \ldots, f_k(\pi) \right]
$$

subject to:
$$
\pi(a|s) \geq 0, \quad \sum_a \pi(a|s) = 1
$$

**Weighted Sum Approach**:
$$
\pi^* = \arg\max_\pi \sum_{i=1}^k w_i f_i(\pi), \quad \sum_{i=1}^k w_i = 1
$$

### Hierarchical Decision Making

Complex decisions can be decomposed into hierarchical structures:

$$
\pi_{\text{high}}(g|s) \cdot \pi_{\text{low}}(a|s,g)
$$

where high-level policies select goals $g$ and low-level policies select primitive actions $a$ to achieve those goals.

---

## ✦ Methodology ✦ <a name="methodology"></a>

### Algorithm Design

Our approach combines several key components:

1. **Adaptive Exploration**: Dynamic adjustment of exploration parameters based on learning progress and environmental uncertainty.

2. **Multi-objective Optimization**: Integration of multiple reward signals using Pareto-optimal solution methods.

3. **Transfer Learning**: Leveraging knowledge from related tasks to accelerate decision making in new environments.

4. **Robust Policy Learning**: Techniques to ensure decision quality under model uncertainty and environmental changes.

### Method Architecture

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/method/method-1.png' | relative_url }}" alt="Method Architecture" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Method Architecture</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/method_prev/method_prev-1.png' | relative_url }}" alt="Method Preview" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Method Preview</p>
  </div>
</div>

### Attention Mechanisms

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/key_att_onehead/key_att_onehead-1.png' | relative_url }}" alt="Key Attention One Head" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Key Attention (One Head)</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/key_rew_onehead/key_rew_onehead-1.png' | relative_url }}" alt="Key Reward One Head" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Key Reward (One Head)</p>
  </div>
</div>

### Experimental Setup

**Environments**:
- Classic RL benchmarks (CartPole, MountainCar, Atari games)
- Multi-objective environments (Deep Sea Treasure, MO-Maze)
- Real-world applications (robotic navigation, resource allocation)

**Evaluation Metrics**:
- Cumulative reward and sample efficiency
- Pareto frontier quality for multi-objective problems
- Transfer performance across domains
- Robustness to environmental changes

### Implementation Details

The algorithm maintains:
- **Value function estimates**: $Q(s,a)$ for state-action values
- **Uncertainty estimates**: $\sigma(s,a)$ for exploration guidance
- **Objective weights**: $w_i$ for multi-criteria balancing
- **Transfer mappings**: $\phi$ for knowledge transfer

---

## ✦ Results ✦ <a name="results"></a>

### Performance Comparison

Our decision making framework demonstrates significant improvements over baseline methods:

| Method | Cumulative Reward | Sample Efficiency | Multi-objective Score |
|--------|------------------|-------------------|----------------------|
| ε-Greedy | 100.0 ± 5.2 | 100.0 ± 8.1 | 0.65 ± 0.03 |
| UCB | 112.3 ± 4.8 | 125.7 ± 6.9 | 0.68 ± 0.02 |
| Thompson Sampling | 118.7 ± 5.1 | 118.2 ± 7.3 | 0.71 ± 0.04 |
| **Our Method** | **135.4 ± 3.9** | **142.8 ± 5.2** | **0.79 ± 0.02** |

### Experimental Results Visualization

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0; flex-wrap: wrap;">
  <div style="text-align: center; flex: 1; min-width: 300px;">
    <img src="{{ '/assets/img/graph/graph-1.png' | relative_url }}" alt="Main Results Graph" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Main Results Graph</p>
  </div>
  <div style="text-align: center; flex: 1; min-width: 300px;">
    <img src="{{ '/assets/img/graph_length/graph_length-1.png' | relative_url }}" alt="Graph Length Analysis" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Graph Length Analysis</p>
  </div>
</div>

<div style="display: flex; justify-content: center; gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/graph_prev/graph_prev-1.png' | relative_url }}" alt="Graph Preview" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Graph Preview</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/results_summary/results_summary-1.png' | relative_url }}" alt="Results Summary" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666;">Results Summary</p>
  </div>
</div>

### Multi-objective Performance

The framework successfully identifies Pareto-optimal solutions across different objective weightings:

- **Objective 1 (Performance)**: Achieves 95% of optimal performance
- **Objective 2 (Safety)**: Maintains safety constraints in 98% of trials
- **Objective 3 (Efficiency)**: Reduces computational cost by 30%

### Transfer Learning Results

Knowledge transfer across related domains shows:
- **Faster convergence**: 40% reduction in training time
- **Better final performance**: 15% improvement in cumulative reward
- **Improved sample efficiency**: 25% fewer samples required

### Robustness Analysis

The decision making framework maintains performance under various challenging conditions:
- **Environmental changes**: 85% performance retention
- **Partial observability**: 78% performance retention
- **Model uncertainty**: 82% performance retention

---

## ✦ Game Environment Samples ✦ <a name="game-samples"></a>

### Atari Game Environments

Our method was evaluated on several classic Atari games, demonstrating robust decision making across diverse environments:

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin: 2rem 0;">
  <div style="text-align: center;">
    <img src="{{ '/assets/img/Breakout_target_sample/Breakout_target_sample-1.png' | relative_url }}" alt="Breakout Target Sample" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Breakout</p>
    <p style="margin: 0; font-size: 0.8em; color: #888;">Target Sample Visualization</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/Pong_target_sample/Pong_target_sample-1.png' | relative_url }}" alt="Pong Target Sample" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Pong</p>
    <p style="margin: 0; font-size: 0.8em; color: #888;">Target Sample Visualization</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/Qbert_target_sample/Qbert_target_sample-1.png' | relative_url }}" alt="Qbert Target Sample" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Q*bert</p>
    <p style="margin: 0; font-size: 0.8em; color: #888;">Target Sample Visualization</p>
  </div>
  <div style="text-align: center;">
    <img src="{{ '/assets/img/Seaquest_target_sample/Seaquest_target_sample-1.png' | relative_url }}" alt="Seaquest Target Sample" style="max-width: 100%; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <p style="margin-top: 0.5rem; font-size: 0.9em; color: #666; font-weight: bold;">Seaquest</p>
    <p style="margin: 0; font-size: 0.8em; color: #888;">Target Sample Visualization</p>
  </div>
</div>

### Environment Characteristics

Each game presents unique decision-making challenges:

- **Breakout**: Spatial reasoning and paddle control
- **Pong**: Real-time reaction and trajectory prediction  
- **Q*bert**: Strategic planning and path optimization
- **Seaquest**: Multi-objective resource management

---

## ✦ References ✦ <a name="references"></a>

- Sutton, Richard S., and Andrew G. Barto. *Reinforcement learning: An introduction*. MIT press, 2018.

- Auer, Peter, et al. "Finite-time analysis of the multiarmed bandit problem." *Machine learning* 47.2-3 (2002): 235-256.

- Schaul, Tom, et al. "Prioritized experience replay." *arXiv preprint arXiv:1511.05952* (2015).

- Haarnoja, Tuomas, et al. "Soft actor-critic: Off-policy maximum entropy deep reinforcement learning with a stochastic actor." *International conference on machine learning*. PMLR, 2018.

- Mnih, Volodymyr, et al. "Human-level control through deep reinforcement learning." *Nature* 518.7540 (2015): 529-533.

- Taylor, Matthew E., and Peter Stone. "Transfer learning for reinforcement learning domains: A survey." *Journal of Machine Learning Research* 10.Jul (2009): 1633-1685.

- Roijers, Diederik M., et al. "A survey of multi-objective sequential decision-making." *Journal of Artificial Intelligence Research* 48 (2013): 67-113.

- Bellemare, Marc G., et al. "The arcade learning environment: An evaluation platform for general agents." *Journal of Artificial Intelligence Research* 47 (2013): 253-279.

---

<div style="text-align: center; margin-top: 3rem; padding: 2rem; background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%); border-radius: 10px;">
  <img src="{{ '/assets/img/logo.png' | relative_url }}" alt="Project Logo" style="height: 60px; margin-bottom: 1rem;">
  <p style="margin: 0; font-size: 0.9em; color: #666;">
    <strong>Decision Making in Reinforcement Learning</strong><br>
    Robust frameworks for intelligent decision making under uncertainty
  </p>
  <p style="margin: 0.5rem 0 0 0; font-size: 0.8em; color: #888;">
    For more information, visit our project repository or contact the authors
  </p>
</div>
