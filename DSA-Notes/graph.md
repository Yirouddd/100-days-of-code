# Graph
A graph is a non-linear data structure consisting of vertices (nodes) and edges that connect pairs of vertices. 
It's used to represent relationships between objects.

## Basic Components
```text
Graph G = (V, E)
- V = Set of vertices (nodes)
- E = Set of edges (connections between vertices)
```
---

## Types of Graphs
### 1. Based on Direction
- Undirected Graph: Edges have no direction
```text
A ----- B
|       |
|       |
C ----- D
```
- Directed Graph (Digraph): Edges have direction
```text
A ──→ B
↑     ↓
│     │
C ←── D
```

### 2. Based on Weight
- Weighted Graph: Edges have weights/costs
```text
A ---5--- B
|         |
3         2
|         |
C ---4--- D
```
- Unweighted Graph: All edges have equal weight

### 3. Special Types
- Cyclic Graph: Contains at least one cycle
- Acyclic Graph: No cycles
- Tree: Connected acyclic undirected graph
- Complete Graph: Every vertex connected to every other vertex
- DAG (Directed Acyclic Graph)  
A DAG is a directed graph that contains no cycles. It's one of the most important graph structures in computer science.
```text
    A
   ↗ ↘
  B   C
   ↘ ↙
    D
    ↓
    E
```

---

## Ways to Represent a Graph
### 1. Adjacency Matrix
A 2D array where matrix[i][j] indicates an edge from vertex i to vertex j.   
```text
Graph:          Adjacency Matrix:
A --- B         [0, 1, 1, 0]
|     |         [1, 0, 1, 1]
C --- D         [1, 1, 0, 1]
                [0, 1, 1, 0]
```
If the graph is undirected, then G[i][j] = G[j][i]

### 2. Adjacency List
Array/list of lists where each index stores its neighbors.
```text
Adjacency List
A: ['B', 'C']
B: ['A', 'C']
C: ['B', 'A', 'D']
D: ['C']
```

---

## Bipartite Graph
A graph G = (V, E) is bipartite if its vertex set V can be partitioned into two disjoint sets U and V (often called partitions or partite sets) such that:
Every edge connects a vertex in U to a vertex in V. No edge connects vertices within the same set.

### Equivalent Definitions
A graph is bipartite if and only if:  
1. 2-Colorable
The vertices can be colored with exactly 2 colors such that no two adjacent vertices share the same color.  
2. No Odd Cycles  
The graph contains no cycles of odd length (3, 5, 7, etc.)  
3. Bipartite Graph Property
∀ edge (x,y): x and y are in different sets

An **odd cycle** is a cycle in a graph that contains an odd number of edges (and therefore an odd number of vertices).
```text
Tree (always bipartite)
        ●(U)
       /    \
      ●(V)  ●(V)
     /  \     \
    ●(U) ●(U) ●(U)

1(U) ─── 2(V)
 │         │
 │         │
4(V) ─── 3(U)
All edges go between U and V ✓
No edges within U: 1 not connected to 3 directly ✓
No edges within V: 2 not connected to 4 directly ✓
```


---

## Bipartite algorithm
A bipartite algorithm determines whether a graph is bipartite by attempting to 2-color it. 
If successful, the graph is bipartite; if a color conflict occurs, it's not.

### Core Algorithm: BFS-Based 2-Coloring
**The Basic Idea**  
1. Assign a color (0 or 1) to a starting vertex  
2. Give all neighbors the opposite color
3. Continue BFS/DFS through graph
4. If we find adjacent vertices with same color → NOT bipartite
