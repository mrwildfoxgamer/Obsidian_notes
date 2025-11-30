[[DSA]]
`
### Expression tree
*An expression tree is a type of binary tree which is used to express mathematical expressions*

expression tree uses mathematical operation at the top and numbers at the bottem

![[Pasted image 20251119015214.png]]

# Binary search Tree

*It is a type of tree in which it can have at most 2 child nodes and they are stored in such a way that the left child is smaller than the parent and the right node is larger than the parent*

*The value stored by the nodes are called keys and these keys cannot be duplicated in BST*


### Operations on BST

**Searching**

1. starts at the Root
2. Check if the value if equal is yes -> element found else
3. IF value is smaller then go to the left child
4. IF value is bigger then go to the right child
5. IF you reach NULL then -> element not found

   **Insertion**
1. starts at the Root
2. Compare the value
	IF smaller go left 
	IF larger go right
3. Stop when you reach NULL
4. Add the value there

**Deletion**
1. Leaf node 
- Delete the node
2. Node with only one child
- Replace the node with the child 
3. If the node has 2 child
- Find the **inorder successor** (smallest value in right subtree)  
or **inorder predecessor** (largest in left subtree).  
Replace the node with that value, then delete the successor/predecessor.


### Applications

- Helps find the data faster than normal tree
- Helps to store data in a sorted manner
- Building faster database
- memory efficient search 