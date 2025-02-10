# Scheduling Criteria

## Cpu utilization

-Need to keep the CPU busy

## Throughput

- Work is being done if CPU is busy
- N/o of instructions executed per unit time is throughput

## Turnaround time

- We need to know how long it takes to complete a task
- The intervel between the start and end of a task
- It is the sum of time spent:
  - Waiting to get into the CPU
    Waiting in ready queue
    Executing the task
    doing I/O

## Waiting time

- Time spent waiting for the CPU to become free

## Response time

- Time taken to get the response from the server

[!Note]

- Maximize CPU utilization and throughput
- Minimize waiting time, response time and turnaround time

# Scheduling Algorithms

- Deciding which process to run from ready queue

**1.** First come first served (FCFS)

- Processes are served in the order they arrive
- Implementation of FIFO is easily managed using FIFO queue

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1      | 0            | 5          |
| P2      | 1            | 3          |
| P3      | 2            | 8          |
| P4      | 3            | 6          |

- Gantt chart

| P1  | P2  | P3  | P4  |
| --- | --- | --- | --- |

`0     5     8     16    22`

[!Note]
TAT = CT - AT
WT = TAT - BT

**2.** Shortest Job First (SJF) - Non preemptive

- Here when CPU is available it is given to the process with the shortest burst time
- If same burst time then it is given to the process with the shortest arrival time

| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1      | 0            | 5          |
| P2      | 1            | 3          |
| P3      | 2            | 2          |
| P4      | 3            | 1          |

- Gantt chart
  | P1 | P4 | P3 | P2 |
  |-----|-----|-----|-----|

` 0     5     6     16    22`

**3.** Shortest Job First (SJF) - Preemptive

-Here CPU is given to the process with the shortest burst time
| Process | Arrival Time | Burst Time |
| ------- | ------------ | ---------- |
| P1 | 0 | 8 |
| P2 | 1 | 1 |
| P3 | 2 | 3 |
| P4 | 3 | 2 |
| P5 | 4 | 6 |

- Gantt chart

| P1  | P2  | P3  | P4  | P5  | P1  |
| --- | --- | --- | --- | --- | --- |

`0     1     2     5     7     13    20`

**4.** Priority Scheduling

- Here CPU is given to the process with the highest priority
- It has both preemptive and non preemptive version

**5.** Round Robin Scheduling

- Here CPU is given to the process in a round robin fashion
- There is a quantum of time between each process
- Therefore all processes are given the same amount of time and weightage
