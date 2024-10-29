# Process Scheduling
_The organizing of when to execute which processes._
- **Multiprogramming**: Maximizing the CPU utilization, by having some process running at all times.
- **Time Sharing**: Switching between processes so frequently so users can interact with each of the programs that are running.
- **Starvation**: This is often due to not being prioritized by the scheduling algorithm.
## Scheduling Queues
_An order of processes organized by._
- **Job Queues**: When a process enters the system it gets placed here, contains all processes in the system.
- **Ready Queue**: These processes are ready to be executed, and reside in the main memory.
- **Device Queue**: Contains processes that are waiting for a specific I/O device to become available.
## Context Switching
_Switching between processes to ensure all of them complete their tasks._
When an interrupt occurs the system saves the current context of the process that is currently running, so it can restore that context when the interrupting process is done.

---
# Process Scheduling Algorithms
## First Come, First Served
_First process to arrive will be the first one to be completed._
## Shortest Job First
_Whichever process has the smallest burst time is run first._
- Non-Preemptive: Once a process starts executing, it runs to completion.
- Preemptive: While a process is running it can be replaced with another that arrives with a shorter burst time.
## Priority Scheduling
_Processes are given operating time based on their designated priority levels._
These processes run until they complete, or are usurped by a higher level priority process. 
- Preemptive: Higher priority processes usurp current running processes. 
- Non-Preemptive: Once a process starts executing, it runs to completion unless it voluntarily relinquishes the CPU.
## Round Robin (with time quantum)
_Every process will be touched because they only have as much time to operate as the quantum._
Each process is assigned a fixed time slice (quantum) this is the maximum amount of time that process can run before being usurped.
## Multilevel Queue
The ready queue will contain separate queues, each representing different priority levels or types of processes. Each queue can have its own scheduling algorithm.

---
# Burst Time
## Prediction of Burst Time
_Guessing a Process's Burst Time based on previous behavior_
Burst times are not always known in advance.
Operating systems may use historical data or heuristics to predict future burst times based on past behavior.

---
# Gantt Chart
``` ASCII
   p1     p2    p3      p4
[■■■■■■|■■■■■■|■■■■|■■■■■■■■■■]
0      2      4    5          9
```
