[[Unit_2]]


#### Thread scheduling

* *It is is the part of jvm that decide which thread should run*
* *The scheduler will randomly choose to run a thread*
* *The scheduler mainly uses preemptive or time slicing scheduling to schedule the threads*
- Java thread scheduling is platform-dependent

`The operating system can interrupt a currently running thread to give cpu time to another thread in preemptive sheduling`

`in Time Silcing cpu time is devided into small slices each thread gets a time slcide`

#### Priority of a Thread 

- Each Thread have a priority represented by a number between 1-10
- In most cases the thread scheduler schedules according to their priority  

```
Public staic int MIN_PRIORTY    values = 1
Public staic int NORM_PRIORTY   values = 5
Public staic int MAX_PRIORITY   values = 10
```

The default priority is 5 (NORM_PRIORITY)
