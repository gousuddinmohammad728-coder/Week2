# Week 2 Lab: Dynamic Programming

## Overview
This project implements classical Dynamic Programming (DP) algorithms for solving Markov Decision Processes (MDPs), based on Sutton & Barto (Chapter 4).

The implementation includes:
- Policy Evaluation (prediction problem)
- Policy Improvement Theorem
- Policy Iteration
- Value Iteration
- Generalized Policy Iteration (GPI)

A custom GridWorld environment is built using Gymnasium, along with application to FrozenLake-v1.

---

## Features
- Custom GridWorld (configurable size)
- Deterministic and stochastic transition dynamics
- Full transition model: P(s', r | s, a)
- Policy Iteration (synchronous and in-place)
- Value Iteration (synchronous and in-place)
- Visualization:
  - Value function heatmaps
  - Policy arrow plots (quiver)
  - Convergence curves
- Performance comparison (iterations and execution time)
- Integration with Gymnasium environments

---

## Environment

### GridWorld
- State space: N × N grid
- Action space: 4 actions (Up, Right, Down, Left)
- Reward:
  - Step cost: -1
  - Terminal state: 0 reward
- Terminal states: start and goal positions

### Transition Types
- Deterministic: agent moves in intended direction
- Stochastic: 
  - 80% intended direction
  - 10% deviation to each perpendicular direction

---

## Algorithms

### Policy Evaluation
Computes the value function V(s) for a given policy using iterative updates until convergence.

### Policy Improvement
Updates the policy greedily based on the current value function.

### Policy Iteration
Alternates between policy evaluation and policy improvement until the policy becomes stable.

### Value Iteration
Directly updates the value function using the Bellman optimality equation and derives the optimal policy after convergence.

### Update Methods
- Synchronous: uses a copy of the value function for updates
- In-place: updates values directly to improve efficiency

---

## FrozenLake Integration
The implementation also applies Value Iteration to Gymnasium's FrozenLake-v1 environment by accessing its transition dynamics using:


env.unwrapped.P


---

## Requirements


pip install numpy matplotlib gymnasium


---

## How to Run


python Week2_DP_Lab.ipynb


or run all cells in Jupyter Notebook.

---

## Learning Outcomes
- Implemented DP algorithms from scratch
- Understood policy improvement and GPI framework
- Analyzed convergence behavior of DP methods
- Worked with known transition models
- Applied DP techniques to standard Gymnasium environments