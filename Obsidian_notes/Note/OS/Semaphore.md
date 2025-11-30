[[OS UNIT 2]]

Semaphore is a Special integer variable used to control access to shared resources in concurrent process 
`IT is a   counter that controls how many process can access a resoruce or when they should wait`

- It is used to avoid race condition 
- IT uses two atomic operations `wait ()` -> `p()` and `signal()` ->  `v()` these signals can be called by any process unlike mutex where only  process in the critical section can make a call
There are two types of semaphores 

1. Binary semaphores
	- Values is either  0 or  1 
	- Works exactly like mutex
	- Only one process is allowed at a time
2. Counting semaphore
	- Value can be any integer
	- Allows n number of processes to access shared memory at the same time 

## Readers-writers problem
- Readers can read simultaneously 
- Writes need exclusive permission
- Only allows multiple reading 

### Dining philosophers Problem

- 5 Philosophers siting around  a table 
- Each need two forks 
- If all of them pic the left fork deadlock occurs
**Solution**
* Let the Odd Philosophers pic Right fork fist
* Even philosophers pic Left fork first