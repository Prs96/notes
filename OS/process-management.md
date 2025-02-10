# Process Management

- Process is a program that is running in the operating system.
- Process needs resources like --> CPU, Memory, Disk, Network
- Process are allocated resources only when they are created or executed.

- Process State:

  - When a process is created, it is in the **ready** state.
  - When the process is running, it is in the **running** state.
  - When the process is waiting for an event, it is in the **waiting** state.
  - When the process is blocked, it is in the **blocked** state.
  - When the process is terminated, it is in the **terminated** state.

```
    +---------+
    |  New    |
    +---------+
        |
        v
    +---------+
    | Ready   |<------+
    +---------+       |
       |  ^           |
       |  |           |
       v  |       +---------+
    +---------+   | Waiting |
    | Running | --+---------+
    +---------+
        |
        v
    +----------+
    |Terminated|
    +----------+
```

- New :
  - A process is created when a program is executed.
- Ready :
  - A process is waiting to be assigned to a CPU.
- Running :
  - A process is currently executing.
- Waiting :
  - A process is waiting for an event to occur.
- Blocked :
  - A process is waiting for a resource to become available.
- Terminated :
  - A process has completed its execution.

[!Note]

- Only one process can be assigned to a CPU at a time eventhough there are multiple processes running.

# Process Control Block

- Process Control Block (PCB) is a data structure that contains information about a process.
- PCB is also called task control block (TCB).
- PCB also contains information about the process such as:

  - Process ID
  - Parent Process ID
  - Process State
  - Program counter
  - I/O Status
  - Memory Usage
  - CPU Registers
  - CPU scheduling information
  - Accounting Information

## Process Control Block Visualisation (PCB)

| Attribute              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| **Pointer**            | Points to the next PCB in the queue                      |
| **Process State**      | Current state (New, Ready, Running, Waiting, Terminated) |
| **Process Number**     | Unique identifier for the process                        |
| **Program Counter**    | Address of the next instruction to execute               |
| **Registers**          | Stores CPU register values for the process               |
| **Memory Limits**      | Defines allocated memory boundaries                      |
| **List of Open Files** | Tracks files the process has access to                   |
| **Priority**           | Scheduling priority level                                |
| **Accounting Info**    | CPU usage, execution time, etc.                          |
| **I/O Status**         | Information about I/O requests and devices               |

# Threads

- Process is a program that performs single thread of execution.
- Single thread allows only one task to execute at a time.
- Modern OS have multi-threading support.

# Process Scheduling

- Process scheduling is the process of deciding which process should run on which CPU.

- Scheduling Queue:
  - As a process enters the system they are added to job queue.
  - Queue has all the process
  - Process ready to execute are in the ready queue.
  - Queue is stored as linked list.
  - A ready queue header contains pointer to the first and last PCB in the list.
  - Each PCB contains pointer to the next PCB in the queue.
  - The list of processes waiting for a particular I/O device is called a device queue.

```
         +-------------+
         | Ready Queue |
         +-------------+
                |
                v
        +----------------+
        |      CPU       | -----------------------------
        +----------------+                             |
                |                                      |
     +----------+----------+                           |
     |                     |                           |
+-------------+     +---------------+          +-----------------+
| I/O Request |     | Time slice    |          | Fork a child    |
|             |     | expired       |          +-----------------+
+-------------+     +---------------+                  |
     |                     |                           v
     v                     v                 +-----------------+
+-------------+     +-----------------+      | Child executes  |
| I/O Queue   |     | Back to Ready   |      +-----------------+
+-------------+     | Queue           |                |
     |              +-----------------+                v
     v                                              +-------------------+
+-------------+                                     | Wait for an       |
| I/O Complete|                                     | interrupt         |
+-------------+                                     +-------------------+
       |                                                  |
       |                                                  |
       |                                                  V
       -------------------------------------------->(Back to Ready Queue)


```

- Scheduler:

  - Scheduler is responsible for deciding which process should run on which CPU.
  - Long term scheduler:
    - Selects process from job pool and assigns it to CPU.
  - Short term scheduler:
    - Selects process from ready queue and assigns it to CPU.
  - Primary difference between long term and short term scheduler is their differnce in frequency of scheduling.
  - Short term is fast where as long term is careful
  - Process are mainly 2 types :
    - I/O Bound Process :
      - Process that performs I/O operations.
    - CPU Bound Process :
      - Process that performs CPU intensive operations.
  - Long-Term Scheduler should select a good process from the CPU / I/O bound process.
  - Medium-Term Scheduler removes process from memory and then reduces the degree of multiprogramming - Process are swapped out and swapped in by medium term scheduler.

                       +------------------------------+
        Swap-in  --->  | Partially Executed           |
          ∧            | Swapped-Out Processes        |
          |            +------------------------------+
          |                   |   Swap-out
          |                   v
        +--------------+    +-----+    +--------------------+
        | Ready Queue  | -->| CPU | -->|        End         |
        +--------------+    +-----+    +--------------------+
                |             |
                |             v
        +------+-------------+------+
        ∧                           |
        |                           v
        +--------+             +-------------------+
        | I/O    | <---------- | I/O Waiting Queue |
        +--------+             +-------------------+

- Context Switching:
  - Switching CPU from one process to another requires saving and restoring the state of the older processes, it includes value in cpu register, this process is called Context switching
  - Context of a process is saved in a PCB.
  - it is pure overhead of CPU as there is no useful work while context switching.
