# Cpu Scheduling

- CPU scheduler is basis of multiprogrammed OS like Linux, Windows, etc.
- Objective of multiprogramming is to have all processes running at the same time inorder to maximize CPU utilization.
- Several process are kept at memory and when a process is not using the CPU, it is moved into wait queue and CPU is given to another process

- CPU Scheduler

  - Whenever the CPU becomes idle, the OS must select one of the processes in the queue and give it the CPU.
  - Selection is carried out by short term scheduler and long term scheduler.
  - A ready queue may be implemented as FIFO queue, priority queue, a tree, etc.

- Preemptive scheduling

  - CPU scheduling takes place in 4 phases  
    **1.** When a process switches from waiting to ready, it is added to the ready queue.  
    **2.** When a process switches fro ready to waiting, it is removed from the ready queue.  
    **3.** When a process switches from running to waiting  
    **4.** When a process is terminated
  - In 1 & 4 there are no choice in terms of scheduling.
  - In 2 & 3 there are choices :

    - When schedulingh takes place under circumstance 1 and 2, the process is non-preemptive, otherwise preemptive.

  - Non preemptive scheduling

    - The process keeps running until it is terminated.
    - Preemptive scheduling may cause issues as other process may intervine and cause the process to be terminated.

  - Dispatcher
    - Dispatcher gives the control of CPU to the process selected by the scheduler.
    - Invoked during every switch from ready to running state.
    - Time taken by dispatcher to stop a process and start another process is called dispatch latency.
