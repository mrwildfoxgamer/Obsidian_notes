[[DSA]]


* A Graph consists of a set od Vertices and nodes and edges connecting the pair of vertices
* Some times edges have weight/cost creating a weighted graph
		The two types of edges are Uncorrected and directed 

## Basic Terminology 

**Adjacency**

- vertex u is adjacent to vertex v if there is an edge connecting it
**Incidence Edge
- An edge is incident if one of end points in another vertex
**Degree**
- degree in un-directed graph means the number of edges incident on a vertex
- in-degree it means the number of incoming edges
- out-degree it means the number of outgoing edges
**Self Loop**
- an edge from a vertex to itself
**Simple graph**
- No self loops and no parallel edges


### Different types of Connected graph

**Connected graph**
- You can reach a vertex from any other vertex
**Tree**
- A connected graph with no cycles
**Simple path**
- A path with no repeated vertex
**Cycle**
- A path where first and last vertex are the same

### Graph Representation

### **Adjacency Matrix**

- An **n × n** matrix A
    
- A[i][j] = 1 if edge exists, else 0
    
- For weighted graphs → store weights
    
- Requires **O(n²)** storage
    
- Dense representation
    

For digraphs:

- Row sum = out-degree
    
- Column sum = in-degree
    

### **B) Adjacency List**

- More space-efficient
    
- For n vertices and e edges → size is n + 2e (undirected)
    
- Only stores neighbors of each vertex


## Graph Traversal
A Graph traversal visits every vertex in a systematic order without reputation


# BFS Algoritham

1. start
2. read Graph
3. initialize queue
4. mark all vertices uninvited
5. choose starting vertices 
6. Visit all uninvited adjacent vertices enqueue them
7. dequeue processed vertices
8. continue until queue empty
9. produce spanning tree
10. stop


# DFS (Depth_First_Search)

- uses a stack
- go deep before backtracking
- also produces a spanning tree
## Algorithm

1. push stating vertex
2. visit uninvited adjacent vertex
3. continue until stuck
4. backtrack
5. Repeat until stack is empty

# Dijkstra’s Algorithm

*Used to Find the shortest path from a source vertex to all other vertices*

- Works on both directed and undirected graphs
- All edge weight must be non negative
