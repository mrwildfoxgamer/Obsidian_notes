[[OS UNIT 2]]

*Process is a program under execution*
*A process need Cpu time,memory,files etc to complete execution*
*These resources are allocated during the creation or execution of the program*

#### Process state
- *The process state means the current activity of the process*
- New state *the process is being created*
- Ready *The process is waiting to be assigned to a processor*
- Running *Instructions are being executed*
- Waiting *The process is waiting for some signal to occur*
- Terminated *The process has finished execution*

![[Pasted image 20251014194816.png]]

**New State
* The new state is the initial state of a process
* When the process is in the secondary memory and is ready for execution the process is said to be in new state
**Ready State
- When the process is loaded into the main memory and is prepared for execution it transitions from new state to ready state
**Run State
* Once the Cpu is allocated the Process is transited to Run state
**Terminate State
* After the execution is complete The process changes from run state to terminate state
* When in terminate state processes is killed and pcb is deleted
	`Process control block (PCB)`
- The resource allocated will be released or de-allocated 
**Block or Wait State
- If the process require an I/O operation or a blocked resource during execution It transitions from run to block or Wait state
- The process stays in the main memory and does not use the cpu
- once the I/O operation is complete or the resource is available it changes back to run state 
