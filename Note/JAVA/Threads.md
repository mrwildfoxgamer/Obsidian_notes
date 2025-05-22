[[Unit_2]]

*A thread is the smallest part of a process than allows a program to run efficiently by running multiple tasks simultaneously*
- **with threads you can do multiple tasks at the same time and make programs run faster and more responsive**
#### Advantages of using thread

- If an error or exception occurred on a thread it will not affect other thread or the execution of the program
- All the thread shares a common memory
- each thread has its own stack local variables and program counters 
- you can run multiple threads in parallel its called multi-threading
`The life cycle of a thread is handiled by the jvm in java`


[[Thread states]]
$New$ - Thread is created but hasn't started `new thread()`
$Runnable$ - `start()` when called the thread is started and is waiting to run
$Running$ - The thread is actively executing its task inside the `run()` method
$NON-Runnable(Blocked)$ - The thread is temporally paused or waiting for conditions to satisfy to run 
$Terminated$ - The thread has completed execution or it is stopped


