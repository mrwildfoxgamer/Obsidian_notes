[[DSA]]
* Data Structures is a specialized format for organizing and storing data It enables efficient access and modification 
### Primitive Data Types 

`intiger Float char boolean`
### Non - Primitive Data Types
*Linear data structure*
data elements are arranged sequentially
`Array,Linked list,Stack,Queue`
- Array - *fixed collection of same types of data*
- Linked List - *Nodes with data and a reference to the next node*
- Stack - *LIFO Structure*
- Queue - *FIFO* Structure

*Non Linear data structure*
Data elements are not arranged sequentially
`Tree,Graph`

- Tree - *Hierarchical Structure*
- Graph - *set of nodes connected by edges*
### Abstract data types (ADT)

*ADT's Defines what operations can be performed on a data type but not how those operations are implemented*

Adt's are used to separate logic from implementation and to make the code base more modular and re-usable thus making it easy to maintain   ADT's also makes the code encapsulated 

**OPERATIONS**
`push(x)` - Add element x on top
`pop()` - remove and return the top element
`Peek()` - return the top element without deleting it 


### Static Vs Dynamic Data Structures
#### Static Data Structures 
*The size if fixed at the time of declaration and cannot be changed at runtime*
- Memory is allocated during compilation
- values can be accessed faster
- the size cannot be alterd
`Static stack , static queue`

#### Dynamic Data Structures
*The size can be changed during runtime*
- memory is allocated during runtime 
- Accessing the contants is slower compared to static DSA
`Linked List` `Dynamic stack` `Dynamic Queue` `Tree` `Graph`

### Homogeneous Vs Heterogeneous Data 

- Homogeneous - *all the elements are of the same type*
- Heterogeneous - *Elements can be of different types*

### Operations in Data structures 
- *Traversal* 
- *Search*
- *Insertion*
- *Deletion*
- *Sorting*
- *Merging*

### Static and Dynamic Memory Allocation
`Compile time or static memeory allocation`
`Run-Time or Dynamic memeory Allocation`



| Static Memory Allocation                                                                                                                                           | Dynamic memory allocation                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| The memory for a variable is allocated During the compilation and is allocated permanently till the program execution is complete or the function call is finished | The memory allocation is handled by the programmer during the runtime memory gets allocated with malloc() and is de-allocated with free() |
| It uses stack for managing static allocation of memory                                                                                                             | It uses heap of memory for managing the memory allocation                                                                                 |
| less efficient                                                                                                                                                     | more efficiant                                                                                                                            |
| There is no memory re-usability                                                                                                                                    | There memory re-usability , memory can be freed when not required                                                                         |
| Once the memory is allocated the memory size cannot be changed                                                                                                     | After memory allocation the memory size can be changed                                                                                    |
| execution is faster                                                                                                                                                | execution is slower                                                                                                                       |

