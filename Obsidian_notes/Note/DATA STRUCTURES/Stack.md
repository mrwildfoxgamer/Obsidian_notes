[[DSA]]
- A stack is a abstract data type (ADT)
- Stack follows First in first out principle FIFO
- insertion is called push and deletion is called pop
- Stack can be implemented with the help of array ,structures,linked list pointers etc
- A stack can be either dynamic or fixed size

### Basic operations on Stack

- push()-adding an element to the stack
- pop()- accessing and removing an element from the stack
- peek()-accessing the top element of the stack with out removing it
- Isempty()-check if the stack is empty
- isFull()-Check if the stack is full
`A pointer is set to point to the last puhed elemnt to the stack so that the value of the top element can be accessd with out removing it`
`This pointer is called TOP`

##### Push ()
The process of inserting an element into the stack is called push

to push an element into the stack 
1. checks if the stack is full
2. If the stack is full returns error
3. else increase the top so that it points to the next empty space
4. adds the element to the top position where the **Top** is pointed
5. return sucess
`refer program`

##### Pop()

The process of accessing an element and removing it from the stack is known as pop()
`In array representation the element is not removed The top is just decremented but in linked-list representation the  top element is removed and de-allocated `

To Pop an element from the stack
1. check if the stack is empty 
2. if its empty then returns error
3. else if the stack is not empty then access the element 
4. decrease the Top to point to the next element 
5. return success
`refer program`










