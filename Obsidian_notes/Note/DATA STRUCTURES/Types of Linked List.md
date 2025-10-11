[[DSA]]
- **Linear Singly-Linked List (Linear List)** - The pointer points to the next node
- **Circular Linked List** - The pointer of the last element points to the first Element
- **Doubly Linked List**  - Two pointers are used to track of the list **head** and **tail**  List can be Traversed either backward or forward

### Singly Linked List
- *In this types of Linked List  a single node will only contains one link pointing to the next node in the list*
- The First node will always  pointed by a pointer called the head
- *If the link of the node points to null that indicated the end of the list*
- In this Linked list we can one Traverse in one direction hence called one-way list

### Representation of Linked List in memory

- Static representation using array
- Dynamic representation using free pool storage


#### Static Representation using arrays

*Two arrays are used to represent static linked list on array1 The actual data is been stored while on the array2 The pointer to the next node is stored*


| **Array1** | **Array2**                 |
| ---------- | -------------------------- |
| Data0      | Index of Data 1 `array[1]` |
| Data1      | Index of Data 2 `array[2]` |
| Data2      | Index of Data 3 `array[3]` |
| Data3      | Index of Data 4 `array[4]` |
| Data4      | null (-1)                  |

### Dynamic Representation

- The Dynamic representation is done using the free pool storage
- `memory bank: collection of free memory space`
- `memory manager: a program that Allocated and frees memory Dynamicallt while the program is running`
- When ever a node is required the request is placed to the memory manager It will search the memory bank for the block if found it will be granted 
- `Garbage collector: Another program that returns the unused node to the memory bank`
**Working of memory manager**
- The memory manager keep track of the free memory blocks in the system where nodes can be saved , there will be a pointer to this list called avail
- when you need a new node the system looks inside avail to find a free block big enough to store the node 
`If no blocks are found then the memory manager decedies wether to create a new block or throw an error`
- when a suitable block is found the memory manager gives you the address of that block 
- you can then insert the new node and connect it anywhere in your linked list by adjusting the pointers of the previous nodes 


