# SLE-3: C4 Architecture Design of Graph Search System using BFS and DFS

## Course Information

| Field | Details |
|---|---|
| Course | 02AML204 – Introduction to Artificial Intelligence |
| Activity | SLE-3 |
| Project | Graph Search System using BFS and DFS |
| Architecture Model | C4 Model |
| Diagram Tool | diagrams.net (draw.io) |
| Previous Activity | SLE-2: BFS vs DFS Empirical Performance Analysis |
| Author | Shreyash Potdar |

## Project Overview

This project presents the software architecture of a Graph Search System using Breadth-First Search (BFS) and Depth-First Search (DFS).

The system accepts a directed graph, a start node, and a goal node. It uses BFS or DFS to find a path and provides the search result, path length, and number of expanded nodes.

The architecture is represented using the four levels of the C4 model: Context, Container, Component, and Code.

## Objectives

- To understand and apply the C4 architecture model.
- To design four levels of architecture diagrams.
- To represent the BFS and DFS Graph Search System clearly.
- To identify the main modules and components of the system.
- To connect the architecture design with the SLE-2 implementation.

## C4 Architecture Diagrams

### Level 1 – Context Diagram

The Context Diagram represents the interaction between the user and the Graph Search System.

It includes:
- User
- Graph Search System (BFS/DFS)
- Search Result / Path Output

The user provides the graph, start node, goal node, and algorithm selection. The system returns the path, path length, nodes expanded, and search result.

### Level 2 – Container Diagram

The Container Diagram represents the six major functional modules of the system.

| Container | Responsibility |
|---|---|
| Input Module | Accepts graph, start node, goal node, and algorithm |
| Graph / Problem Representation | Stores graph structure and node relationships |
| Search Engine | Executes BFS or DFS |
| Visited / Memory | Tracks explored nodes |
| Goal Test & Path Handling | Checks the goal and maintains the path |
| Output Module | Displays the path and search results |

### Level 3 – Component Diagram

The Component Diagram focuses on the internal structure of the Search Engine.

| Component | Responsibility |
|---|---|
| BFS / DFS Controller | Controls the selected search algorithm |
| Frontier (Queue / Stack) | Maintains nodes waiting for exploration |
| Explored / Closed Set | Tracks visited nodes |
| Goal Test | Checks whether the goal node is reached |
| Path Reconstructor | Represents the path-handling logic |

### Level 4 – Code Level Overview

The Code Level represents the main functions and variables used in the BFS and DFS implementation.

| Function / Variable | Purpose |
|---|---|
| `bfs(graph, start, goal)` | Performs BFS using a queue |
| `dfs(graph, start, goal)` | Performs DFS using a stack |
| `graph` | Stores directed graph connections |
| `visited` | Tracks explored nodes |
| `path` | Maintains the search path |
| `nodes_expanded` | Counts expanded nodes |

## Design Decisions

The system is divided into separate modules for input, graph representation, search processing, memory management, path handling, and output.

BFS uses a queue, while DFS uses a stack. Both algorithms operate on the same graph-search problem.

A visited set prevents repeated node expansion, and separate goal testing and path handling make the architecture easier to understand.

## Tools Used

- Python – BFS and DFS implementation from SLE-2
- Visual Studio Code – Development environment
- diagrams.net (draw.io) – C4 architecture diagrams
- Microsoft Word – Architecture report
- GitHub – Project documentation and version control
- ChatGPT – AI assistance

## Project Files

| File | Description |
|---|---|
| `C4_Level1_Context.png` | Level 1 Context Diagram |
| `C4_Level2_Container.png` | Level 2 Container Diagram |
| `C4_Level3_Component.png` | Level 3 Component Diagram |
| `C4_Level4_Code.png` | Level 4 Code Level Overview |
| `SLE3_Report.docx` | Final SLE-3 architecture report |
| `README.md` | Project documentation |
| `AI_ContributionLog.md` | Student and AI contribution record |

## Conclusion

The SLE-3 activity successfully represents the BFS and DFS Graph Search System using the four levels of the C4 architecture model.

The diagrams explain the system from high-level user interaction to its main implementation functions. The architecture is simple, modular, and connected to the BFS and DFS implementation developed in SLE-2.
