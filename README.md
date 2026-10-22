# Graph Search System using BFS and DFS

This project implements graph search on a directed graph using two uninformed search strategies:

- **Breadth-First Search (BFS)** using a queue
- **Depth-First Search (DFS)** using a stack

Given a graph, start node, and goal node, the program searches for a valid route, records the explored nodes, reconstructs the path, and reports the number of expanded nodes.

## Project Objectives

- Compare BFS and DFS on the same directed graph.
- Find a path from the start node to the goal node.
- Prevent repeated exploration using a visited set.
- Measure path length, nodes expanded, and execution time.
- Document the system architecture through C4 diagrams and an Architecture Decision Record (ADR).

## Core Design

The system uses the following main functions and data items:

| Item | Purpose |
| --- | --- |
| `bfs(graph, start, goal)` | Performs Breadth-First Search using a queue. |
| `dfs(graph, start, goal)` | Performs Depth-First Search using a stack. |
| `graph` | Stores directed graph connections. |
| `visited` | Tracks explored nodes and prevents duplicate exploration. |
| `path` | Stores the route from the start node to the goal node. |
| `nodes_expanded` | Counts nodes explored during the search. |

## Search Flow

1. Provide a directed graph, start node, and goal node.
2. Select BFS or DFS.
3. Add the start node to the frontier.
4. Remove a node from the frontier and check whether it is the goal.
5. Add unvisited neighbours to the frontier and record them as visited.
6. Reconstruct and display the path when the goal is found.

## Why a Visited Set Is Used

Graphs can contain cycles and multiple paths to the same node. The visited set makes sure that a node is explored only once. This prevents repeated work, avoids infinite loops on cyclic graphs, and keeps the node-expansion count meaningful for performance comparison.

## SLE-2 Performance Results

Both algorithms found the following path:

`A -> C -> F -> J -> N -> R -> V -> X -> Z`

| Metric | BFS | DFS |
| --- | ---: | ---: |
| Path length (edges) | 8 | 8 |
| Nodes expanded | 25 | 20 |
| Run 1 (ms) | 1099.568 | 1098.097 |
| Run 2 (ms) | 1062.292 | 1216.371 |
| Run 3 (ms) | 1048.642 | 1179.768 |
| Average time (ms) | 1070.167 | 1164.746 |
| Average time per search (ms) | 0.010702 | 0.011647 |
| Searches per run | 100,000 | 100,000 |

For this benchmark, BFS had the lower average execution time, while DFS expanded five fewer nodes. Both found a path of the same length.

## Architecture

The system was documented using the C4 model:

- **Context:** A user provides graph input and receives the search result.
- **Container:** Input, graph representation, search processing, memory management, path handling, and output work together.
- **Component:** The Search Engine contains the BFS/DFS controller, frontier, explored or closed set, goal test, and path reconstructor.
- **Code:** The `bfs()` and `dfs()` functions use `graph`, `visited`, `path`, and `nodes_expanded`.

## How to Run

Run the Python file that contains the `bfs()` and `dfs()` functions using Python 3:

```bash
python <your_python_file>.py
```

No external Python packages are required for the core graph search implementation.

## Course Context

- **Course:** 02AML204 - Introduction to Artificial Intelligence
- **Student:** Shreyash Potdar

## Documentation

- SLE-1: BFS and DFS implementation with an AI contribution log.
- SLE-2: Performance comparison of BFS and DFS.
- SLE-3: C4 architecture diagrams.
- SLE-4: Architecture Decision Record defending the use of a visited set.

