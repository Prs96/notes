# What is an Operating System?

- An Os is a program that acts as an interface between the user and the computer hardware.

- It is a program that manages the resources of the computer and provides a way for the user to interact with the computer.

- Os is a system software that provides a platform for running other programs.

## Functions of an Operating System

- Memory Management

  - Allocating and deallocating memory
  - Managing memory
  - Keeping track of memory usage
  - Os decides which program to run and how much memory to allocate to it
  - Allocates memory only to program when it requests it
  - Deallocates memory when program is finished

- Process Management

  - Creating and terminating processes
  - Managing processes
  - Scheduling processes
  - Keeps track of running processes
  - Allocates CPU time to processes
  - Deallocates CPU time when process is finished

- File Management

  - Creating and deleting files
  - Managing files
  - Keeping track of files
  - Decides who gets resource
  - File access is controlled by permissions

- Device Management

  - Managing devices
  - Keeping track of devices
  - Allocates devices in a way that is efficient
  - Deallocates devices when they are no longer needed

- Security & Protection

  - Ensuring security and protection of the system by means of passwords, encryption, firewalls, etc to prevent access to unauthorised programs and data

- Job Accounting

  - Keeping track of the usage of resources
  - Reporting usage to the system administrator

- Error Handling
  - Handling errors and exceptions
  - Reporting errors to the system administrator

### Types of Operating Systems

**1.** Batch Operating System

- The users of batch operating system do not interact with the computer directly.
- They submit a job to the operating system and the operating system manages the resources of the computer.
- To speed up proccessing, jobs with similar tasks are grouped together and run in parallel.

- Problems:
  - Lack of user interaction
  - CPU is often idle because of I/O devices is slower than CPU
  - Difficult to provide the desired priority to jobs

**2.** Multiprogrammed Operating System

- Increases the number of programs that can be run on the computer.
- Single user cannot keep either cpu or I/O devices busy.
- Os keeps several jobs in memory simultaneously.
- This set of job is subset of jobs kept in job pool
- Os pics job from memory and runs it.

| **OS** |
| ------ |
| Job 1  |
| Job 2  |
| Job 3  |
| Job 4  |
| Job 5  |

| **Job Pool** |
| ------------ |
| Job 1        |
| Job 2        |
| Job 3        |
| Job 4        |
| Job 5        |
| .....        |
| Job n        |

| **Memory** |
| ---------- |
| Job 1      |
| Job 2      |

- When a job may have to wait for I/O devices, the cpu is idle as it is a non programmed system.
- Multiprogramming is the first instance where the os takes decision for the user.
- All jobs that enter the system are put in the job pool.
- If not enough space in memory, the job is put in the queue and the system must determine what to run
  - This is called job scheduling
- If several jobs are ready to run , the system must decide which one to run.
  - This is called CPU scheduling

**3.** Multiproccess Operating System

- Multiprocessor system are also called parallel systems.
- It has more than one processor.

- Advantages:
  - More throughput:
    - By increasing the number of processors, the system can perform more tasks in parallel.
  - Economy of scale:
    - Multiproccessor shares pheripheral, mass storage & power among the processors.
  - Increased reliability:
    - If functions can be properly divided among the processors, the system is more reliable.
    - The system can be more reliable because the failure of one processor does not affect the others.
    - This ability to provide service propotional to the level of surviving hardware is called graceful degradation.

**4.** Time sharing Operating System

- Major disadvantage of batch os and multiprogramming os is that the user is not able to interact with the system.
- Time sharing is a logical extension of multiprogramming.
- In time sharing cpu executes process by switching between them.
- It switches over so fast that the user cannot tell which process is running.
- Each process is assigned a time slice.

**5.** Real time Operating System

- A real time system is a system taht uses rigid time requirements.
- It is a system that must meet the deadlines or it will fail
- It comes in 2 flavours :
  - Hard real time
  - Soft real time
    - Hard real time guarentees that the system will meet the deadlines.
    - Soft real time critical real-time tasks get priority over other tasks.

**6.** Distributed Operating System

- A distributed operating system is a system that is composed of multiple cpu
- The processors communicate with each other through various connection lines.These are referred as loosely coupled systems.

- Advantages:
  - with resoure sharing facility, a user may be able to use resources avialable to other users.
  - The system may be more reliable because the failure of one processor does not affect the others.
  - Better service to customers
  - Reduction of load
  - Reduction of delay in data processing

[!Note]

- Batch Operating System
- Multiprogrammed Operating System
- Multiproccess Operating System
- Time sharing Operating System
- Real time Operating System
- Distributed Operating System
