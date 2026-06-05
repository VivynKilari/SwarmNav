# Obstacle Entrapment and Search Efficiency: A Comparative Study of Swarm Robotic Navigation

## Overview

This repository contains the research paper, supporting materials, and future simulation implementations for a comparative study of navigation strategies in swarm robotics.

The work investigates how decentralized robotic swarms perform in obstacle-rich search-and-rescue (SAR) environments, with particular emphasis on a common failure mode known as obstacle entrapment or local minima trapping. The study compares deterministic Artificial Potential Field (APF) navigation with stochastic Levy-flight-based exploration and evaluates their effectiveness in environments containing significant structural barriers.

The research was motivated by a fundamental question:

> Can randomness improve the ability of robotic swarms to navigate around obstacles that defeat traditional goal-directed navigation methods?

The results suggest that while deterministic navigation remains computationally efficient, stochastic movement strategies provide greater resilience in highly obstructed environments.

---

## Research Motivation

Search-and-rescue robotics is one of the most demanding applications of autonomous systems. In post-disaster environments, robots frequently encounter collapsed structures, debris fields, blocked corridors, and unpredictable terrain.

Traditional navigation algorithms often assume that moving directly toward a target is beneficial. However, when physical obstacles block the path, these methods can become trapped in local minima, repeatedly attempting to move through an inaccessible region.

This project explores whether introducing controlled randomness into swarm movement can improve the probability of successful target discovery.

The study focuses on:

- Obstacle entrapment
- Search efficiency
- Swarm exploration behavior
- Local minima avoidance
- Search-and-rescue applications
- Stochastic navigation methods

---

## Research Questions

The following questions guided this work:

1. How does deterministic APF navigation behave when a direct path to the target is obstructed?

2. Can Levy-flight-inspired stochastic motion improve exploration performance?

3. What trade-offs exist between directed navigation and random exploration?

4. How does swarm behavior change when agents encounter large structural barriers?

5. What implications do these findings have for future SAR robotic systems?

---

## Methodology

### Environment

A two-dimensional simulated environment was constructed containing:

- A target location
- Multiple swarm agents
- A significant central obstacle
- Fixed simulation boundaries

The obstacle was intentionally positioned to create a structural shadow between the swarm and the target.

This configuration forces agents to either:

- Discover an alternative route around the barrier
- Become trapped attempting to move directly toward the goal

### Navigation Models

#### 1. Artificial Potential Field (APF)

The deterministic approach uses an attractive potential centered on the target.

Agents continuously move in the direction of the negative gradient of the potential field.

Advantages:

- Computational simplicity
- Fast convergence in open environments
- Low implementation complexity

Limitations:

- Susceptibility to local minima
- Poor obstacle circumvention
- Reduced adaptability

---

#### 2. Levy-Flight Navigation

The stochastic approach introduces randomness into agent movement through Levy-flight-inspired step generation.

Key characteristics:

- Occasional long-distance jumps
- Non-Gaussian movement patterns
- Increased environmental exploration

Advantages:

- Improved exploration diversity
- Better escape capability from trapped regions
- Greater robustness in obstructed environments

Limitations:

- Less direct paths
- Reduced efficiency in obstacle-free environments
- Increased variability in performance

---

## Experimental Procedure

The study consisted of multiple simulation trials under identical environmental conditions.

For each trial:

1. Swarm agents were initialized.
2. Navigation strategy was selected.
3. Agents attempted to locate the target.
4. Search duration was recorded.
5. Success and failure outcomes were logged.

The primary evaluation metric was:

**Step Count to Target Discovery**

which serves as a simplified proxy for mission completion time.

---

## Key Findings

### Deterministic Navigation

The APF-based agents consistently moved toward the target.

However, when the obstacle blocked the direct path, agents repeatedly converged on the same trapped region.

This resulted in:

- Local minima entrapment
- Failure to bypass obstacles
- Near-zero behavioral diversity

---

### Stochastic Navigation

Levy-flight agents displayed more exploratory behavior.

Although many trials still failed to locate the target within the maximum simulation duration, some agents successfully discovered routes around the obstacle.

This demonstrates that randomness can function as an effective escape mechanism when deterministic strategies fail.

---

## Discussion

One of the most interesting observations from the study is that additional information does not always improve performance.

The deterministic agents possessed a constant directional estimate of the target location, yet this information repeatedly led them into the obstacle.

The stochastic agents, despite having less structured movement, occasionally discovered successful paths through exploration.

This highlights an important principle in swarm robotics:

> Exploration can be more valuable than optimization when environmental information is incomplete.

The findings suggest that future robotic swarms may benefit from balancing:

- Exploitation (goal-directed movement)
- Exploration (randomized search)

rather than relying exclusively on either approach.

---

## Future Work

Several extensions are planned:

### Hybrid APF-Levy Navigation

A hybrid controller that:

- Uses APF during normal operation
- Detects entrapment conditions
- Temporarily switches to Levy-flight exploration
- Returns to directed navigation after obstacle avoidance

---

### Dynamic Obstacles

Future experiments will introduce:

- Moving barriers
- Changing environments
- Time-varying targets

to better represent real disaster scenarios.

---

### Larger Swarms

Additional studies will evaluate:

- 50-agent swarms
- 100-agent swarms
- Heterogeneous agent populations

to investigate scaling effects.

---

### ROS Integration

Potential future implementation using:

- ROS 2
- Gazebo
- Webots

for higher-fidelity simulation and validation.

---

## Repository Structure

```text
.
├── paper/
│   └── swarm_robotics_research_paper.pdf
│
├── figures/
│   ├── results.png
│   ├── comparison_plot.png
│   └── environment_layout.png
│
├── simulations/
│   ├── apf_model/
│   ├── levy_model/
│   └── hybrid_model/
│
├── data/
│   └── experiment_results.csv
│
└── README.md
```

---

## Applications

Potential applications include:

- Search and Rescue Robotics
- Disaster Response Systems
- Autonomous Exploration
- Multi-Agent Systems
- Environmental Monitoring
- Warehouse Robotics
- Planetary Exploration

---

## References

1. Khatib, O. (1986). Real-Time Obstacle Avoidance for Manipulators and Mobile Robots.

2. Viswanathan, G. M. et al. (1999). Optimizing the Success of Random Searches.

3. Reynolds, C. W. (1987). Flocks, Herds and Schools: A Distributed Behavioral Model.

4. Braitenberg, V. (1984). Vehicles: Experiments in Synthetic Psychology.

5. Dorigo, M., & Birattari, M. (2007). Swarm Intelligence.

6. Mather, T. W., & Hsieh, M. A. (2011). Distributed Target Tracking with a Swarm of Robots.

---

## Author

**Vivyn Kilari**

Bachelor of Technology in Robotics and Automation

Independent Research Project

2026

---

## License

This repository is provided for academic and research purposes.

Please cite the work appropriately if you use any part of the methodology, results, or future implementations.
