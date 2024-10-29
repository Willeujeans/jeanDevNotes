# Synchronization
_Coordinating concurrent processes or threads preventing conflicts and ensuring integrity of data._
Due to threads and processes sharing resources, they often run into conflicts.  
Using a Synchronization system will ensure that all resources are being accessed by one thread or process at a time.  
## Race Conditions
_unpredictable behavior caused by multiple entities attempting to access and modify shared data simultaneously._
Multiple threads or processes access a shared resource at the same time.  
Causing the final state of the shared resource to be unpredictable and dependent on the order and timing of the accesses.  
Race conditions often occur in critical sections where shared data is read or modified. This leads to the need for synchronization mechanisms.  
## Critical Sections
_The part of the program where shared resources are accessed._
Synchronization ensures that only one process can execute in its critical section at a time. This prevents race conditions being caused from processes taking/modifying resources others need.
- Every process must make a request using the `entry section` permission to enter its `critical section`
- Critical section is followed by the `exit section`
- The remaining code is the `remainder section`
### Peterson's Solution
_A classic software based solution to the critical section problem (how can processes not try to access or modify data that is shared)._
Requires two data items that are shared between two processes
- P<sub>i</sub> = Process 1
- P<sub>j</sub> = Process 2
- int `turn` = i or j
- boolean `flag[i or j]`
If a process wants to enter into the critical section it will let the other process go first.
Process i structure:
```
do{
	flag[i] = true
	turn = j
	
	while(flag[j] && turn == j); // while true, we do not enter the critical section
	
	critical section
	flag[i] = false
	remainder section
}while(TRUE)
```
## Mechanisms
_Strategies to ensure Process and Thread Synchronization._
### Locks
_Only allow one Process or Thread to access their Critical Section at a time._
Provides mutual exclusion, by restricting all Process's access to their Critical Sections when another Process has accessed their critical section.
### Semaphores
_Synchronization primitives that can be used to control access to shared resources._
- wait(P): decrease the semaphore count, leading to a process sleeping at 0.
- signal(V): increased the semaphore count, leading to a process to wake up.
### Monitors
_Monitors encapsulate shared resources and the methods that operate on them_
Provides mutual exclusion by encapsulating the shared resources, only allowing the monitor's methods to access or modify the shared resources.  
Provides condition synchronization, by allowing the process to wait for specific conditions.  
### Condition Variables
_Allows threads to wait for specific conditions to be met before continuing execution._
### Test and Set Lock
_A low-level atomic operation that sets a lock variable and checks its status._
A hardware solution to the synchronization problem.  
A shared lock variable which can be 0 or 1.  
Before entering into the critical section a process will check the lock (_it will either be 1 or 0_).  
If locked: it waits until it becomes free.
If not locked: it takes the lock and executes the critical section
```
// THIS IS ATOMIC, CANNOT BE INTURRUPTED
boolean TestAndSet(boolean *target){
	boolean rv = *target
	target = TRUE
	return rv
}
```

## Cooperating processes
- Directly share a logical address space (code and data)
- OR
- Allowed to share data through files and messages

---
# Deadlocks
_multi-processing issue where processes are unable to proceed because each is waiting for the other to release a resource._
### Conditions
- **Mutual Exclusion**: At least one resource must be held, unable to be shared.
- **Hold and Wait**: A process holding a resource is waiting to acquire additional resources that are currently being held by other processes.
- **No Preemption**: Resources must be voluntarily released by those holding them.
- **Circular Wait**: A group of processes are each waiting for a resource that is held by another process in the group, forming a closed loop.
## Banker's Algorithm
_Determines if a system can allocate resources to each process without leading to a deadlock._
Five Processes
Resources of type _A, B, C_ 

| Process | Allocation | Max     | Available |
| ------: | ---------- | ------- | --------- |
|         | _A B C_    | _A B C_ | _A B C_   |
|   $P_0$ | 0 1 0      | 7 5 3   | 3 3 2     |
|   $P_1$ | 2 0 0      | 3 2 2   |           |
|   $P_2$ | 3 0 2      | 9 0 2   |           |
|   $P_3$ | 2 1 1      | 2 2 2   |           |
|   $P_4$ | 0 0 2      | 4 3 3   |           |

Need $[i, j]$ = Max $[i, j]$ – Allocation $[i, j]$

| Process | Need    |
| ------: | ------- |
|         | _A B C_ |
|   $P_0$ | 7 4 3   |
|   $P_1$ | 1 2 2   |
|   $P_2$ | 6 0 0   |
|   $P_3$ | 0 1 1   |
|   $P_4$ | 4 3 1   |
