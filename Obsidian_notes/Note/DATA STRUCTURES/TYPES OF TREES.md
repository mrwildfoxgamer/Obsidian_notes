## Binary Tree 

[[DSA]]


- A binary tree has a special node called the **Root**.
    
- Every other node can have **at most 2 children**: a **left sub-tree** and a **right sub-tree**.
    
- Each sub-tree is also a tree (a tree inside a tree).
    
- If a tree has no nodes, it is called an **empty tree**.
    

### Degree of a Node

- The **degree** of a node means the number of children it has.
    
- A node with **degree 0** is called a **leaf node**.
    
- A node with **degree 1** is called a **single-child node**.
    
- A node with **degree 2** is a node with two children.
    

---

### Important Binary Tree Properties

- **Number of nodes = Number of edges + 1**
    
- **Maximum number of nodes at level _i_** = 2^i
    
- **Maximum number of nodes in a binary tree of height _h_** = 2^(h + 1) − 1
    
- **Minimum number of nodes in a binary tree of height _h_** = h + 1
    
- **Number of leaf nodes = Number of degree‑2 nodes + 1**
    

---

### Explanation

Every time there is a node with **two children**, it creates **two new branches**.  
But every branch must eventually end at a leaf node.  
So, the tree will always end up having **one more leaf node** than the number of nodes that have **two children**.

# Representation of Binary Tree

### Linear or sequential Representation

- In this representation of  Binary tree a block of memory is allocated for the array
- once the memory is allocated the size of the tree is fixed
- In this representation the  nodes are stored level by level starting from zero where only the root node is present
*The root node will be at index 0*
*For parent node its `(i-1)/2`*
*Left child its `2i+1`*
*Right child its `2i+2`*

#### Advantages of Array representation

- Any can be accessed by calculating the index value
- Fast searing 
- can be used in  programming language where dynamic memory allocation is not possible
- Good for complete binary tree
- Data  can be stored with out any pointers 

#### Disadvantages of Array representation

- If the binary tree is not complete then a lot of memory is wasted
- Dynamic memory allocation is not possible 

## Linked or pointer Representation

- Tree can be defined  as a collection of finite nodes and each node contains 3 parts  data part left link and Right link

**Operations on binary Tree**
	insertion
	deletion
	Traversal

### Insertion 

- Most common method is to insert the new element into the First Available position  It is find through Level order traversal or Breadth-First-Search 
- Traverse the tree level by level
- find the node that has its left or right child which is empty (Null)
- insert the new value as the missing child
### Deletion
- Start at the Root and traverse Till the deepest and the right most node and the node we want to delete 
- replace the value of the Deepest right most  node with the node to be deleted 
- then delete the Deepest right most node
### Traversal 
*  Traversal means visiting all the elements in the tree exactly once 
* There are mainly 3 types of traversal
		in-order traversal
* In-order traversal first visits the left subtree then visits the root then visits the right subtree
		pre-order traversal
* In pre-order traversal first visits the root then Left sub tree then Right sub tree
		post-order traversal
* Post order first visits left then right sub tree then visits the root







