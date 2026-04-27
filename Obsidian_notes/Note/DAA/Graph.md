It is a non leaner data structure consisting of vertices and edges

- The vertices are sometimes also referred to as nodes and the edge are lines or arcs that connect any two nodes in the graph
 
**Directed vs Undirected graph**

- In undirected graph edges are not associated with the direction with them if an edge exists between vertex a and b then vertices can be traversed from B to A as well as a to b
- Directed graph edges from an ordered paired edge represents a specific path from some vertex A to another vertex b Node A is called Initial node and node B is called terminal node  
- **Weighted Graph:** - There is some weight over the edges of the graph
- **Unweighted graph** - There is no weight over the edges of the graph 

## **Terms Used in Graph**
### Vertex

A node in graph.

### Edge

Connection between two nodes.

### Path

Route from one node to another.

### Cycle

A path that starts and ends at same node.

### Degree

Number of edges connected to a node.

### Adjacent Vertices

Two nodes directly connected.

# Graph Representation

#### Adjacency Matrix

Table of rows and columns.

If edge exists = 1  
Else = 0

Good for dense graphs.

#### Adjacency List

Each node stores connected neighbors.

A → B, C  
B → D

Uses less memory.

`Traversal means visiting all nodes.`

## BFS (Breadth First Search)

Visits level by level.

Uses **Queue**

Example:

 visits neighbors first, then their neighbors.

### Steps:

1. Start node
2. Add to queue
3. Remove front node
4. Visit neighbors
5. Repeat

### Time Complexity

O(V+E)

### Uses:

- Shortest path (unweighted graph)
- GPS
- Networking
- Web crawling

---

## B. DFS (Depth First Search)

Goes deep first, then backtracks.

Uses **Stack / Recursion**

### Steps:

1. Start node
2. Go deep to next node
3. If no path, return back
4. Continue

### Time Complexity

O(V+E)

### Uses:

- Cycle detection
- Path finding
- AI games
- Connected components

---

# 6. Spanning Tree

A **Spanning Tree** is a tree made from graph that:

- Includes all vertices
- Has no cycle
- Uses minimum edges

For `n` vertices:

n−1n-1n−1

edges required.

### Example:

5 vertices → 4 edges

---

## Properties of Spanning Tree

- No cycles
- Connected
- Minimum edges
- More than one spanning tree possible

---

# 7. Minimum Spanning Tree (MST)

A spanning tree with **minimum total weight**.

Used in:

- Cable networks
- Roads
- Electric lines
- Internet routing

---

# 8. Kruskal’s Algorithm

Used to find MST.

### Steps:

1. Sort edges by smallest weight
2. Pick smallest edge
3. Avoid cycles
4. Continue until complete

Greedy method.

---

# 9. Prim’s Algorithm

Also finds MST.

### Steps:

1. Start from one node
2. Add smallest connecting edge
3. Expand tree
4. Repeat

Greedy method.

---

# Easy Memory Trick

|Topic|Uses|
|---|---|
|BFS|Level by level|
|DFS|Deep first|
|Spanning Tree|Connect all nodes|
|MST|Cheapest connection|
|Kruskal|Smallest edges globally|
|Prim|Grow from one node|

---

# Most Important Exam Topics

- Graph definition
- Types of graph
- Adjacency matrix vs list
- BFS algorithm
- DFS algorithm
- Spanning tree
- MST
- Prim vs Kruskal

---

If you want, I can also make **1-day exam revision notes for this full Graph chapter**.