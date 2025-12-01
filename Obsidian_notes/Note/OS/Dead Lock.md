[[Os Unit 3]]


*Deadlock is a situation in an operating system where two or more processes get stuck forever because each process is waiting for a resource that another program is holding*

### Request
The process ask for a resource 
- If the resource is free, it gets it immediately
- If the resource is busy, the process must wait

### Use
After getting the resource, the process uses it 

### Release
When done the process release the resource 

### Deadlock Characterization

1. Mutual exclusion - At least one resource must be non-shareable, only one process can use that resource at a time 
2. Hold and wait - The process is holding one resource and is waiting for another resource.
3. The process cannot be forcefully taken away from a process
4. Circular wait - p 1 waiting for p 2, p 2⇾p 3, p 3⇾p 1

### Methods for Handling Deadlocks

- Deadlock prevention - The OS make sure that at least one of the 4 deadlock conditions never occurs 
- Deadlock Avoidance - The OS checks each resource and decide is it safe to give resource now and will it remain in a safe state
	- To make a decision the OS need extra information like
		- Max resource the process may need in the future
		- Current allocation
		- Resource available 


## Deadlock prevention 

1. Request all resource at once - Before execution, the process requests all the resources it will need 
	-  **Benefit**

- It **never holds one resource while waiting for another** → Hold and Wait condition is eliminated.
    

	- **Drawback**

- Not practical: processes **can’t predict** all future needs.
    
- Leads to **low resource utilization** (resources stay idle). 

2. Eliminating No preemption
	-  This prevents deadlock by allowing the OS to take resource forcibly 
	- Useful when it is possible to safely interrupt a process
3. Eliminating Circular Wait
	-  Give each resource a **number/priority**.
	- Processes must request resources **in increasing (or decreasing) order**.

### Deadlock Avoidance

- The system must know the maximum resource needed for each process in advance 
- The OS checks:

- Available resources
    
- Allocated resources
    
- Maximum demands
    

Then it grants the request **only if the system stays in a safe state**.

This is done dynamically using:

- **Resource Allocation Graph** (single instance)
    
- **Banker’s Algorithm** (multiple instances)

### Deadlock Direction 

Single instance it is used when each resource has only one instance (`1 printer,1 scanner etc`)
We use a weight for graph a wight for graph is created by removing resource block from Resource allocation graph
If the wight for graph contains a cycle then it forms a deadlock

### Multiple Instance Resources

This is used when **each resource type has several instances** (like 3 printers, 2 scanners, 4 tapes, etc.)

This algorithm is **similar to Banker's Algorithm**, but simpler because it's not about avoiding deadlocks — only detecting them.
- **Available[m]**  
    Number of free instances of each resource type.
    
- **Allocation[n][m]**  
    How many resources each process currently holds.
    
- **Request[n][m]**  
    How many more resources each process _still needs_ to complete.
    
- **Finish[n]**  
    Used only during algorithm.  
    Initialize:
    
    - Finish[i] = false if process still needs resources
        
    - Finish[i] = true if process needs nothing (Request = 0)


## Deadlock Recovery

**How the OS breaks a deadlock _after_ it has already occurred** (after detection).

There are **3 main methods**:

1. **Process termination**
    
2. **Resource preemption**
    
3. **Rollback (used in databases)**

# **Process Termination**

The OS kills one or more processes to break the cycle.

There are two ways:

---

## **A. Abort ALL deadlocked processes**

Very simple  
 Guaranteed to break the deadlock  
 Huge loss of work

Used rarely because it's too destructive.

---

## **B. Abort ONE process at a time**

Kill processes _one by one_ until the deadlock cycle breaks.

### How to choose which process to kill?

OS looks at:

- Process priority
    
- How much work it has done
    
- How many resources it holds
    
- How many more resources it needs
    
- Whether it is interactive or batch process
    
- Cost of restarting the process


# **Resource Preemption**

Instead of killing processes, OS **takes resources away** from some processes and gives them to others.

Steps:

1. **Select a victim process**  
    Whose resources should be taken?
    
2. **Rollback that process**  
    Restore it to a safe state (checkpoint).
    
3. **Restart the process later**  
    After deadlock is broken.

### Problems in resource preemption:

- **Starvation**: same process may always lose its resources
    
- **Rollback cost**: need checkpoints
    
- **Choosing a victim** is complex
# **Rollback (transaction systems)**

Mainly in **databases**.

- Each process periodically saves its state → **checkpoint**
    
- If deadlock happens, system rolls back some processes to an earlier checkpoint
    
- Then retry again