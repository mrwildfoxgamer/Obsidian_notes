[[Unit_2]]
#### Creating Thread by extending Thread class

- thread can be created by extending the java.lang.Thread class
- When a class is created that extend  to java.lang.Thread the class becomes a thread 
- The code inside the `run()` method is the code that should be executed when the thread is running
- To start the thread create an object of your class and call `start()`
`the thread runs in the background separately from the main program The start()    calls run() and run the thread on a new thread but if run () is called explicitly it runs like a normal method no a string`

*through the class all the [[Methods for threads]] can be called to modify the threads*


#### Over-Ridding The Run method

The run method is like the main method in java it is where the execution begins 
when `start()` is called java creates a new thread of execution
That new thread automatically calls  `run()` method of our class
The first statement in `run()` is the 1st thing that runs 


- *A thread is considered alive between the moment just before `run()` starts and the the moment `run()` finishes*
- once `Run()` is complete the thread is considered as dead and cannot be restarted


#### Invoke the start() method

- *After start method is called the thread will not start running it will be schedules the thread and when the cpu scheduler picks this thread for execution the jvm calls `run()` method and actually starts the execution the `start()` can only be called once per thread in a program*

#### Implementation of runnable interface
Create a class that implements the interface and override the `run()` method

create an object of the class

create a thread object

start execution of the thread using `start()`


| Thread class                                                             | Runnable interface                                                        |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| you can directly create a thread class be extending thread               | Class can still extend another class because you are not extending thread |
| you can oveeride the run() method                                        | Runnable is just a talk and thread is the executor                        |
| If class extence thread then the class cannot extend any <br>other class | Separation of concerns                                                    |

