[[OS UNIT 2]]

Mutex is a Binary semaphore it can have can have the values 0 and 1
- `1` → available (unlocked)
    
- `0` → not available (locked)

It is used to make sure that at a time only one process or thread can enter a critical section at a time 

`critical section is a part of the coode where shared resoruce are accessd`

**Initial condition**
- `mutex=1`

- When a process wants to enter Critical section it performs `wait(mutex)` 
- This checks if `mutex>0`
- If `mutex == 1`  
- the process enters critical section 
- and `mutex--`
* When the process leaves the critical section it performs `signal (mutex)`
* That will increase the mutex value by one `mutex++` and make it available for the next process 