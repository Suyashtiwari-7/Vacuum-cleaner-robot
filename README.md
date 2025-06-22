# 🧹 Vacuum Cleaner Robot - Pathfinding AI

A Python project that simulates an intelligent vacuum cleaner robot navigating and cleaning a grid-based room using various search algorithms like **DFS**, **BFS**, **Uniform-Cost Search**, **Greedy**, and **A\***.

This project was developed as part of an Artificial Intelligence course to understand how different search strategies perform in pathfinding tasks involving cost, heuristics, and decision making.

---

## 🔧 How to Run

```bash
python cleaner_robot.py <search-type> <input_file>

```

➤ <search-type> can be:
DFS – Depth First Search
BFS – Breadth First Search
UCS – Uniform-Cost Search
GS – Greedy Search using Manhattan Distance
A*1 – A* with basic Manhattan heuristic
A*2 – A* with custom heuristic (as explained in report.pdf)

➤ Example:
```bash
python cleaner_robot.py A*1 init1.txt
```
📁 Input File Format
Each input file (e.g., init1.txt, init2.txt, etc.) represents a grid:

```bash
txt
Copy
Edit
xxxxxxxx
xc     x
x  j 21x
xxxxxxxx
```

Symbols:
c → cleaner's starting position
x → wall/obstacle
digits (1, 2, ...) → dirt (requires that many "suck" actions)
j → jumper: pushes the agent forward by one more step
(space) → free space

### 🤖 Robot Actions & Costs

| Action | Cost | Description                         |
|--------|------|-------------------------------------|
| left   | 1    | Move left one space                 |
| right  | 1    | Move right one space                |
| up     | 2    | Move up one space                   |
| down   | 2    | Move down one space                 |
| suck   | 5    | Clean one unit of dirt from the tile |

### 🔍 Search Algorithms Used

| Algorithm | Description                                             |
|-----------|---------------------------------------------------------|
| DFS       | Explores as far as possible before backtracking         |
| BFS       | Explores all neighbors first (shortest path in steps)   |
| UCS       | Explores lowest-cost path                               |
| Greedy    | Uses heuristic to closest dirt (Manhattan distance)     |
| A*1       | Combines actual cost and heuristic distance             |
| A*2       | Custom A* using weighted vertical cost heuristic        |

Heuristic in A*2:
f(n) = g(n) + (z,oal-2+2xygoal - y)
This accounts for higher vertical movement cost.

###  📊 Output Example
```bash
number of expanded nodes: 28  
path: right down right right suck suck right suck  
cost of the solution: 21  
```
If using A*2, it will also print the initial heuristic value.

### 📎 Files Included

| File              | Description                                             |
|-------------------|---------------------------------------------------------|
| `cleaner_robot.py`| Main program logic                                      |
| `initX.txt`       | Test input files (init0 to init5)                       |
| `README.md`       | Project documentation                                   |
| `report.pdf`      | Heuristic design explanation and problem modeling       |

### 🧠 Learning Outcomes

- Difference between **uninformed** (DFS, BFS, UCS) and **informed** (Greedy, A*) search strategies
- Use of **heuristics** to improve search performance and guide the agent efficiently
- Understanding of **action costs**, state representation, and node expansion during search


