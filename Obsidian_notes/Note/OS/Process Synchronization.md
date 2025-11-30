[[OS UNIT 2]]

*Process synchronization is the Coordination of executing multiple process in a multi process system ensuring all the processes are accessing shared data in a controlled and predictable manner*
*In multi processing system Process Synchronization is important to ensure data consistency and integrity*

`Process Synchronization can be achived by using` [[MUTEX]]

## Race Condition

- Race condition is when two processes/thread access the same shared data at the same time and the output depends on who access the data first 
### Critical Section

- Critical Section is  a part of the program where a  process access a shared resource 
- If multiple process enters Critical section at the same time it creates race condition
#### Solution to prevent race condition 
- Mutual Exclusion - If one process has entered critical section then no other process should be allowed to enter critical section at the same time 
- If none of the process is currently in critical section then one of the waiting process should enter critical section 
- Bounded  waiting - When a process wants to enter critical section it should only wait for a finite amount of  time it should not wait forever There must be a limit on how many other processes can go inside before its turn comes 

### Methods

1. [[Semaphore]] 
2. Mutex Locks
3. Monitors/Condition variables

