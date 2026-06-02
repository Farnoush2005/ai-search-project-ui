# UI AI Pathfinding & Search Algorithms

This repository contains a Python implementation of various search algorithms designed for an AI pathfinding agent navigating a grid environment. This project has been developed as a **B.Sc. Course Assignment for Artificial Intelligence** at the **University of Isfahan (UI)**.

The project demonstrates the application of both uninformed and informed search strategies to find optimal paths while avoiding obstacles and optimizing for specific game-like conditions (such as picking up weapons and clearing multiple targets).

---

## Implemented Algorithms

The project features four distinct search strategies, each sharing a unified state representation and variable naming convention for consistency:

1. **BFS (Breadth-First Search)**
   * **Type:** Uninformed Search
   * **Behavior:** Explores layer by layer using a FIFO queue. Guarantees the shortest path in terms of the number of steps/actions.
   
2. **DLS (Depth-Limited Search)**
   * **Type:** Uninformed Search
   * **Behavior:** A depth-bounded version of DFS designed to prevent infinite loops in deep state spaces. Optimized with a hard depth limit of 18, making it highly efficient for smaller or "easy" map layouts.

3. **UCS (Uniform Cost Search)**
   * **Type:** Uninformed Search (Cost-Optimized)
   * **Behavior:** Expands nodes based on the lowest cumulative step cost $g(n)$ using a priority queue, guaranteeing an optimal cost path.

4. **A*** **(A-Star Search)**
   * **Type:** Informed Search
   * **Behavior:** Combines the actual path cost $g(n)$ with a powerful heuristic function $h(n)$. 
   * **Heuristic Design:** Utilizes **Manhattan Distance** to the closest target combined with a **Minimum Spanning Tree (MST)** (implemented via Kruskal's algorithm) to estimate the distance between multiple targets. It also dynamically factors in weapon positions and ownership states to calculate the most cost-effective route.

---

## Code Structure & Uniformity

To ensure high-quality software design and a natural development footprint, all algorithms have been engineered to use a completely standardized vocabulary:
* `start_state`: The entry point for the grid map.
* `queue`: The underlying data structure (`collections.deque` or `heapq`).
* `visited`: State tracking to prevent redundant exploration and infinite loops.
* `curr_state` & `next_state`: Elements representing current evaluation and neighbor transitions.
* `action`, `step_cost`, and `path`: Variables tracking the movement sequence and total weight.

---

## Environment & Requirements

* **Language:** Python 3.x
* **Libraries Used:** * `heapq` (Standard Library)
  * `collections` (Standard Library)
  * `itertools` (Standard Library)

No external heavy dependencies are required, making the scripts incredibly lightweight and fast to execute.

---

## Academic Context
* **Institution:** University of Isfahan (دانشگاه اصفهان)
* **Degree:** Bachelor of Science (B.Sc.) in Computer Science
* **Course:** Artificial Intelligence (درس هوش مصنوعی)

### Group Members
* **Member 1:** [Farnoush Pourshaban / Student ID: 4024023007]
* **Member 2:** [Yeganeh Rastegari / Student ID: 4014013040]
* **Member 3:** [Farzaneh Salimi / Student ID: 4014013059]
