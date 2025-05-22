[[Unit_2]]

*Synchronization is the ability of java to control the access of multiple threads to access a shared resource*
- *It is used to prevent Thread interference*
- *To prevent consistency problem*

#### Lock 
Synchronization is built around an internal entity known as the lock or monitor every object has a lock associated with it if a thread need to access an object it has to accrue the object lock and release the lock once its done with it

#### Java Synchronized Method

- *If you declare any method as synchronized it is known as synchronized method*
- It is used to prevent thread interference and memory consistency error when multiple threads are access shared resource 
- when a thread invokes a synchronized method it automatically acquires the lock for that object and releases it when the thread completes its task

#### Synchronized block

- *Synchronized block can be used to synchronized only a block of code not the entire program*
- **Suppose we have 50 lines of code in our method, but we want to synchronize only 5 lines, in such cases, we can use synchronized block.**

#### Static Synchronized 
*If you declare a static method as synchronized the lock will be with the class not the object*

