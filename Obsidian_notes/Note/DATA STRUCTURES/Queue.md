*Queue is a leaner data structure that allows insertion at one end and deletion at the other end*
- The end where deletion can take place is called the front and the end where insertion can take place is called rear
- Deletion or insertion can only be taken place at the ends
- 1st element that is to be added is the first element that is removed

*Enqueue - insert an Element at the rear*
*dequeue - delete an Element from the Front*

## Applications 
- resource allocation
- Task scheduling
- Traffic management
- Network protocols

## Algorithm

### Enqueue array
1. Start
2. Declare item
3. Check if rear = size - 1
4. If yes, print "Queue Overflow"
5. If no,
6.     Read the item to be inserted
7.     If front = -1 then set front = 0
8.     Set rear = rear + 1
9.     Set queue[rear] = item
10. Stop


### Dequeue array
1. Start
2. Check if front = -1 OR front > rear
3. If yes, print "Queue Underflow"
4. If no,
5.     item ← queue[front]
6.     front ← front + 1
7.     Return item
8. Stop

### Enqueue Linked list
1. Start
2. Create a new node (NEW)
3. Set NEW->data = item
4. Set NEW->next = NULL
5. If front = NULL
6.        front = rear = NEW
7. Else
8.        rear->next = NEW
9.        rear = NEW
10. Stop

### Dequeue Linked List

1. Start
2. If front = NULL
3.        Print "Queue Underflow"
4. Else
5.        TEMP = front
6.        item = TEMP->data
7.        front = front->next
8.        Free TEMP
9.        If front = NULL
10.             rear = NULL
11.       Return item
12. Stop




## Circular Queue

Circular queue is a extend of the normal queue in which The last element of the queue is connected to the first element of the queue

- When you delete an element from a normal queue The front moves forward  But the space behind cannot be used this means memory is wasted
- In circular queue the front and back are connected so when we delete something the space behind can be used so the memory is not wasted 

## Priority queue
A priority queue is a queue in which all the elements has a priority`
High priority elements are removed 1st and if two elements has the same priority then the one came first is removed 


