#  Genetic Algorithm for the Knapsack Problem

This project implements a **Genetic Algorithm (GA)** to solve the classic **0/1 Knapsack Optimization Problem** and benchmarks its performance against a non-population-based method (**Dynamic Programming**). The system also evaluates various GA design enhancements to improve solution feasibility, convergence, and computational efficiency.

---

##  Objectives
- Maximize total value while keeping weight under capacity
- Analyze the role of GA operators and hyperparameters
- Compare GA results against exact **Dynamic Programming (DP)**
- Study convergence behavior and computational cost

---

##  Methodology

###  Genetic Algorithm Pipeline
| Component | Technique Used |
|----------|----------------|
| Representation | Binary chromosome (0/1 indicating item selection) |
| Initial Population | Random binary vectors |
| Fitness Function | Item value − penalty for overweight |
| Selection | Roulette Wheel + Tournament Selection |
| Crossover | Single-point crossover |
| Mutation | Multi-gene flip (rate: 0.05–0.20) |
| Repair Strategy | Remove excess items sorted by value/weight ratio |
| Stopping Criteria | Fixed generations or early convergence detection |

---

##  Experiments & Insights

| Experiment | Objective |
|-----------|-----------|
| Selection-Only | Base consistency test without genetic operators |
| Add Crossover & Mutation | Improvements across generations |
| Penalty vs. No Penalty | Enforcement of constraint feasibility |
| Convergence-Based Stop | Faster & more stable optimization |
| Population Scaling | Analysis of solution quality vs. population size |

###  Key Findings
- **Repair-based strategy + penalty** produced significantly more feasible, high-value solutions
- **Convergence stopping** reduced runtime while improving best fitness
- **Population size** influenced performance but showed **no direct monotonic trend**
- Best GA result using convergence:  
  - **Total Value:** 5921  
  - **Weight:** 728 (feasible)

---

##  Dynamic Programming Benchmark

| Method | Pros | Cons |
|--------|------|------|
| **GA** | Scales to large spaces, avoids local optima | Hyperparameter tuning required |
| **DP** | Guarantees optimal solution | High memory/time cost on large inputs |

✅ DP achieved best total value (**7534**) for config1  
⚠️ But becomes infeasible for large-scale knapsacks → where GA excels

## 📂 Project Structure
