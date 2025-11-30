[[OS UNIT 2]]

*process scheduling maximizes the cpu usage by efficiently switches between processes process scheduler selects the next process for execution and maintain scheduling queues for the processes* 

**Job queue** - set of all processes in the system
**Ready queue** - set of all process in the main memory ready and waiting to execute
**device queue** - set of processes waiting for an I/O operation to complete  


## Different types of Schedulers

1. Short-term Schedulers
	 Select which process should execute next and allocates cpu
	 Some times the only schedulers in cpu these are fast and is invoked frequently
2. Long-team schedulers
	Select which process should be moved into ready queue
	They are invoked infrequently 
	Controls how many processes are in the memory
	Improves cpu and memory utilization by selecting a good mix of both cpu and I/O bound processes 
3. Medium-term schedulers
	Added to decrease the number of process in the memory by moving processes from the memory to disk and back at the time of execution

### Dispatcher
*It is a component of the os which is responsible for giving control of the cpu to the process selected by the short-term scheduler*
* *it is responsible for Context switching switching of user mode*`moves cpu from kernal mode to user mode` begins execution of the selected process




**Scheduling Criteria**

1. Cpu utilization - keeps the cpu busy as possible
2. Throughput - Number of process completed in unit time more the better
3. Turnaround time - Time taken from submission -> completion of a process
4. Waiting time - The time spend waiting in ready queue
5. Response time - Time from request -> first response
6. Fairness - Every process should get a proper amount of the cpu

## Multi level queue

*The ready queue is divided into multiple queue each stores specific types of process*
Each queue has its own algorithams
Every queue is fixed

## Multi level feedback queue

*It is an improved version of multi level queue*
Process can move between queue  based on there behaviors

- Short processes → promoted to higher-priority queues
    
- Long CPU-burst processes → demoted to lower-priority queues
    
- Prevents starvation by periodically raising priority
    

## Inter process communication

*It is a process by which process communicates and share data with each other*
It allows process to
 - Send messages
 - Share information
 - Synchronize their actions

**Why is it important**

Process often depends on each other
They need exchange data
They need to coordinate

## Types of Inter process communication

**Shared Memory
- Two or more process share a common memory area 
- They read and write directly into the memory
- Very fast
**message passing**
- Process send message to each other
- No shared memory
- Slower but safer
## Why is synchronization needed?

When processes communicate, they must coordinate so:

- messages are not lost
    
- shared data is not overwritten
    
- sender/receiver work in correct order


## **Synchronization in Message Passing**

### There are two types:

## Blocking (Synchronous) Communication

- **Sender waits** until receiver receives the message.
    
- **Receiver waits** until a message arrives.
## **Non-Blocking (Asynchronous) Communication**

- Sender sends and **immediately continues**.
    
- Receiver receives or checks later.

# **Buffering in IPC**

When using message passing, messages need a place to wait until the receiver takes them.  
This waiting area is called a **buffer**.

> **Buffer = temporary storage for messages.**

# Types of buffer

## **Zero-Capacity Buffer (No Buffering)**

- Sender and receiver must meet at the same time
    
- Sender **cannot send** until receiver is ready

## **Bounded Buffer (Finite Buffer)**

- Buffer has limited size (e.g., 10 messages)
    
- Sender can send until buffer is full
    
- If full → sender **must wait**
## **Unbounded Buffer (Infinite Buffer)**

- Buffer has no practical limit
    
- Sender never waits
    
- Only receiver needs to catch up


**Producer–Consumer (Bounded Buffer) Problem**


Two processes share a **fixed-size buffer**:

- **Producer** → creates items and puts them into the buffer
    
- **Consumer** → removes items from the buffer
    

### The problem:

- Producer **must not add** when buffer is **full**
    
- Consumer **must not remove** when buffer is **empty**
    
- Both must not access the buffer **at the same time** → avoid race condition
    

We need **synchronization**. 