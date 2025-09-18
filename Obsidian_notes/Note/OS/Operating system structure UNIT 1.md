[[Operating System Services]]
[[System calls]]
[[System Programs]]

[[OPERATING SYSTEM]]

*An operating system includes multiple components that manages and controls the hardware and act as a interface between the user and the hardware*

#### Components of Operating system 

1. **Kernel** -  kernel is a core component of an operating system that manages the computer hardware and provide essential services to applications and it acts as bridge between software and hardware - **key functions** 

     -  *Process management*- Handles creation scheduling and termination of processes 
     - *memory management* - Allocate and manages system Ram for programs 
     - *Device management* - provides drives and communications between hardware devices  software
     - *System calls* - kernel offers API's or System calls for user to request OS services   
     - *System file access*  - let applications read and write files on the disk
     - *Security and protection* - Keeps programs from interfering with each other

2. **Shell** - It is the interface between the user and the kernel which allows the user to interact with the system

#### Types of kernels


**Monolithic Kernel**
- All the OS services run in the kernel space Eg: Linux 
- Faster execution speed due to direct communication 
- A bug in the kernel can crash the whole system
**Micro-kernel** 
- Minimal core functions in the kernel space and the rest in user Space Eg: Minix
- Keeping the kernel code small and minimal making it easy to maintain 
- As most of the functions are executed in the user space if an error occurs it is unlikely that it affects the entire system
**Hybrid kernel**
- Combination of both monolithic and micro kernels Eg: windows and Mac
- They tend to provide the performance of monolithic kernel and reliability and molecularity of micro kernel 


### Software

