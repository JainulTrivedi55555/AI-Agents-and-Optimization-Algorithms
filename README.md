# AI Agents and Optimization Algorithms

A collection of four AI assignments implemented in Python, covering search algorithms, game-playing agents, environment simulation, and local search optimization. Each notebook is self-contained with implementation, analysis, and written discussion.

---

## Notebooks

### 1. AI Agent Implementation for Optimal Maze Navigation

Implements four search algorithms from scratch to navigate an agent through different mazes from start `S` to goal `G`. The environment is fully observable, discrete, deterministic, and known — a classic open-loop planning problem.

**Algorithms implemented:**
- Breadth-First Search (BFS) — uses a queue, tracks a `reached` set, guarantees shortest path
- Depth-First Search (DFS) — uses a stack, cycle checking only, significantly lower memory footprint
- Greedy Best-First Search (GBFS) — uses Manhattan distance heuristic with a priority queue
- A* Search — combines path cost g(n) and heuristic h(n) for optimal informed search
- Iterative Deepening Search (IDS) — wraps DFS with increasing depth limits

**Tested on 8 maze types:** small, medium, large, open, wall, loops, empty, empty_2

For each maze and algorithm, reports: path cost, nodes expanded, max tree depth, and max frontier size. Results visualized as grouped bar charts comparing all four strategies.

---

### 2. Algorithmic Design of the Connect 4 Game using Python

Builds a full Connect 4 game engine and progressively stronger AI agents to play it on a configurable board (default 6×7).

**Agents implemented:**
- Random agent — selects uniformly from valid columns
- Minimax agent with Alpha-Beta Pruning — searches the full game tree with pruning
- Heuristic Alpha-Beta agent — cuts off at a fixed depth and uses a board evaluation function that scores windows of 4 for potential winning alignments
- Pure Monte Carlo Search agent — simulates random rollouts from each candidate move and picks the highest average utility

**Experiments include:**
- 1,000 random vs. random games to measure first-player advantage
- Minimax vs. Random on a 4×4 board with win/loss/draw analysis
- Scaling test: how computation time grows as board size increases from 4 to 7 columns
- Move ordering strategies and their effect on alpha-beta pruning efficiency
- Two heuristic agents with different cutoff depths playing head-to-head

---

### 3. Intelligent Vacuum Cleaner Simulation using AI

Simulates an automatic vacuum cleaner robot cleaning an n×n room and compares three agent types on energy efficiency.

**Agents implemented:**
- Randomized agent — ignores sensors, moves and cleans randomly
- Simple reflex agent — reacts to bumper (avoids walls) and dirt sensor (cleans when dirty)
- Model-based reflex agent — builds an internal state, locates the nearest corner first, then navigates and cleans the entire room systematically

**Performance measure:** Total energy units (actions) used to clean the whole room.

**Simulation study:** 100 random runs each on 5×5, 10×10, and 100×100 rooms. Results compared with tables and charts. Also analyzes agent robustness under imperfect sensors — 10% dirt sensor error rate and 10% bumper sensor error rate.

---

### 4. N-Queens Problem Solver using Local Search

Solves the N-Queens problem using local search methods. The goal is to place N queens on an N×N board so no two queens share a row, column, or diagonal. State is represented as an integer vector where each value is the row position of the queen in that column.

**Objective:** Minimize the number of pairwise conflicts between queens.

**Local search methods implemented and compared** across different board sizes (n = 8, 20, 100+).

---

## Stack

Python · NumPy · pandas · matplotlib · seaborn · `queue.PriorityQueue`

---

## Project Layout

```
├── AI Agent Implementation for Optimal Maze Navigation.ipynb
├── Algorithmic Design of the Connect 4 Game using Python.ipynb
├── Intelligent Vacuum Cleaner Simulation using AI.ipynb
├── N-Queens Problem Solver using Local Search.ipynb
└── LICENSE
```

> Maze `.txt` files referenced in the maze notebook (`small_maze.txt`, `medium_maze.txt`, etc.) and the `maze_helper.py` module are not included in the repo — these were part of the original course setup.
