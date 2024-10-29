# Process
_This is a program currently in execution._
A process is comprised of:
- **Code**
- **Data**
- **Files**
- **Threads**
	- Registers
	- Stack
## Children
_A duplicate process created by the Parent._
Parent Processes can create other children Processes.  
The Child Process will be a duplicate of the Parent Process.  
## States
_This is the current activity of a Process._
### New
_A process is being created._
### Running
_Instructions are being executed._
### Waiting
_Process is waiting for some event to occur._
### Ready
_Waiting to be assigned to a processor._
### Terminated
_Process has finished execution._
Once a processes has completed its final statement it will ask to be deleted by the operating system using the `exit()` system call.  
The process may return a status value as integer to its Parent Process using `wait()`.  
All of the Process's resources are deallocated (_physical, virtual memory, open files, I/O buffers_) by the operating system.  
System calls to `kill()` a process can only be called by its Parent Process.  
If the Parent Process is terminated, the Child Process is not allowed to continue.  
![](Screenshot%202024-10-08%20at%205.24.15%20PM.png)
## PID
_A unique number that identifies a process_
Process's identification number as a unique integer.
The identification number can be recycled once a processes has ended.
## Threads
_A unit of execution within a Process._
**Allows for:**
- Parallel execution of code within a single process.
- Handling multiple user requests.
- Background computations.
- Concurrent operations.
**Shares:**
- Process’s code.
- Data.
- Open files.
**Individual**
- Execution stack.
- Program counter.
- Local variables.
### Multithreading
_Using multiple threads to perform different tasks within a single process._
This helps make better use of CPU resources and improve application performance.
### Thread Management
_Management of threads is important for CPU efficiency._
Operating systems often provide mechanisms for creating, scheduling, and terminating threads.
