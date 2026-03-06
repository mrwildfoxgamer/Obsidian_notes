[[Full stack]]
*It is an open source cross-platform runtime environment for server side and networking application It provides an event drive 3 n architecture and a non-blocking I/O*
*node.js allows the programmer to use JavaScript on the backed and on the fronted *
Node.js uses v8 engine developed by google with c++ to executes the code 

## Features of Node.js
- **Fast Data Streaming** - Node.js streams to process data in chunks so that the entire thing is not loaded into the memory making it more memory efficient for handling large files and real-time data 
- **Single Threaded** - Node.js runs on a single main thread mainly, but it can handle many requests efficiently using non-blocking operations instead of creating multiple threads
	- Traditional servers create a new thread for each of the new requests eliminating the added difficulty of managing multiple threads 
	- This is possible with the help of Event loop
- **Highly scalable** - Because Node.js uses event driven non-blocking nature it can handle thousands of requests simultaneously with resourceful usage 
- **Event-Driven** - Node.js works by responding to events like requests file reads etc 

+ Node.js Process the data as it arrives it does not weight for the complete data to load with increase the performance and reduces the memory usage
+ **Asynchronous** - Node.js performs time-consuming operations like I/O operations Asynchronously allowing other operations to complete without waiting 


### Single Threaded Event Loop Model

1. Client sends request
2. Event Loop handles it
		→ If the task takes time (like reading a file), Node.js does NOT wait  
		→ It sends the task to the background
3. Node.js Continues working
4. Callback runs when Done


`Libuv handles I/O operations`

## Phases of Event Loop

1. Timers Phase
	- Exicutes callbacks from
		- setTimer()
		- setIntervel()
2. Pending callbacks
	* Executes callbacks for some system operations like TCP errors
3. Idel/Prepare phase
	- Internal phase used by node.js internally
	+ The ideal phase is a period of time which the event loop has nothing to do and can be used to perform background task 
4. Poll Phase
	+ Retrieves new I/O events
	+ executes I/O callbacks
	+ waits for events if queue is empty
5. Check phase
	+ handles closing events like `socket.on(close)`

```
Timers
↓
Pending Callbacks
↓
Idle / Prepare
↓
Poll
↓
Check
↓
Close Callbacks
```

