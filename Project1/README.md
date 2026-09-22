# Project 1 – Gandalf's Path: Uninformed & Informed Search

Computer Assignment 1 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

## Problem

Gandalf the Grey must lead the Fellowship of the Ring across a grid map to Gondor. The map contains:

- Gandalf's starting cell
- the current position of each Fellowship member
- the position each Fellowship member must be delivered to
- Orc positions, each with a military rank `n` that puts every cell within Manhattan distance `n`
  under patrol
- Gondor, the final destination

Gandalf moves one cell at a time (up/down/left/right) and cannot step on an Orc's cell. He *can*
sneak through a patrolled area at night, but only for `n` consecutive moves inside it — the `(n+1)`-th
move must leave the patrolled zone, after which the move counter resets if he re-enters later.
Walking over a Fellowship member's cell picks them up automatically, and reaching their assigned
cell drops them off at no extra cost; Gandalf can carry only one member at a time. The goal is to
deliver every Fellowship member to their assigned cell and then reach Gondor.

## What's implemented

The notebook models the problem as a search problem (`Node` class with `state`, `parent`, `action`,
`path cost`, `depth`) and solves it with:

- **BFS** (uninformed, FIFO frontier via `deque`) — optimal for unit-cost search
- **IDS** (Iterative Deepening Search, DFS with increasing depth limit)
- **A\*** (informed, priority queue via `heapq`) with three consistent heuristics:
  - `h1` — number of Fellowship members not yet in their target cell
  - `h2` — Manhattan distance from Gandalf to the relevant target(s)
  - `h3` — a third, more refined heuristic
- **Weighted A\*** with the same heuristics at multiple `alpha` values (e.g. `alpha=5`, `alpha=10000`)
  to trade optimality for speed

Each test case reports path cost, number of states expanded, number of unique states, and execution
time (averaged over multiple runs), so the algorithms can be compared directly.

## Input format

Each test file is structured as:

1. `n m` — grid dimensions (rows, columns)
2. start coordinates, then end coordinates (Gondor)
3. `k l` — number of Orcs, number of Fellowship members
4. `k` lines of `x y c` — an Orc's position and patrol radius (Manhattan distance)
5. `l` lines — current position of each Fellowship member
6. `l` lines — target position for each Fellowship member (member `i` must go to target `i`)

## Tech stack

- Python, Jupyter Notebook
- `collections.deque` (BFS/IDS frontier), `heapq` (A* priority queue), `time` (benchmarking)

## Files

- `AI_CA1.ipynb` — problem modeling, all four search algorithms, and results for every test case

## License

MIT
