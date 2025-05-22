[[Unit_2]] [[Threads]]

#### New Thread 

*When a thread is created The thread is in a new state where the thread has not yet started to run*

#### Runnable state 

*A thread that is ready to run in moved to a runnable state In this state the thread might be ready to run at any instance and its the responsibility of the thread scheduler to give time to the thread to run*

#### Multi Threaded program

*In a multi threaded program each thread is allocated a fixed amount of time every thread runs for a short period of time and then pauses for other threads in a Runnable state waiting for a $CPU$*  

#### Blocked

*A Blocked thread is a Thread that wants to run but is waiting to access a resource like an Object or a lock which another thread is using*

#### Waiting state: 

*The waiting state in java is a situation in which a thread is paused and waiting for an other thread to perform specific action before it can be processed When a thread is in waiting state it does not consume any cpu cycle*
*A thread goes to waiting state when a method that cause the thread to wait till another thread signals it to continue*

#### Timed waiting
*A thread is in a timed waiting state when a method with a time-out condition is called The thread lies in this condition until the time-out completes or until a notification is received*

#### Terminated state

*A thread is in terminated state when the code is completely executed by the program or when an error or an un-handled exception has occurred*

` To create a new thread, your program will either extend Thread or implement the Runnable interface.`

