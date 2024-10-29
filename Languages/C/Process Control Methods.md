# exec() 
_API family that replaces current process's code and data segments, keeps the same PID._
1. Original program's state is replaced with new given program
2. New program starts executing from its entry point
3. If successful it will never return, -1 if it fails
## Return Value
- no return: if successful
- -1: failure
## Family members
### **int** execl(_"executablePath"_, _"programName"_, _"arg1"_, _"arg2"_, _NULL_)
### **int** execle(_"executablePath"_, _"programName"_, _"arg1"_, _"arg2"_, _NULL_,_environmentVariables\[ ]_)
### **int** execv(_"executablePath"_, _arguments\[arg1, arg2, NULL]_)
### **int** execve(_"programName"_, _arguments\[arg1, arg2, NULL]_)
### **int** execvp(_"programName"_, _arguments\[arg1, arg2, NULL]_)
### **int** execvpe(_"programName"_, _arguments\[arg1, arg2, NULL]_, _environmentVars\[ ]_)

---
# exit()
_exit(int status): void_
Terminates the current process immediately
## Operation
Before termination, function call performs several clean-up activities
- Flushes and closes all open output streams
- Invokes the functions registered with atexit()
- Releases resources allocated by the program
## Exit Status
- Exit status can be retrieved by the parent process using [[wait()]] or `waitpid()`
## Return to OS
- After the process is terminated, control is returned to the operating system, which can then handle the exit status appropriately

---
# fork()
_fork(): void_
This is an API used to create child processes from a parent process
## Operation
1. Creates new process
	this 'child' process is a copy of the 'parent' process
2. Returns Process IDs
	in the parent process it returns the 'child' process PID
3. Process States
	- Both the parent and child processes will have their own separate memory spaces
	- They start executing from the point where `fork()` was called.
		- Child process inherits a copy:
			- process’s address space
			- file descriptors
			- other attributes
## Use Cases:
- **Parallel Processing**: where different processes execute concurrently
- **Daemon Processes**: processes that run in the background
## Returns
8-bit integer
- -1: system call has failed
- 0: this process is inside the child now
- positive value: this is the PID of the child process

---
# wait()
_wait()_
## Operation
blocks until one of its child processes exits or a signal is received
## Status Information
- Can optionally provide status information about the terminated child process using an integer pointer
- Pass a pointer to an integer Wait(`int status`) to receive termination information
## Multiple Child Processes
- Will return only for one child
- Handle multiple children, you can call `wait()` in a loop.
## waitpid()
- It can wait for a specific child process or allow for non-blocking waits
## Return Value
- Process ID of the terminated child
- -1: no child processes and sets `errno` to `ECHILD`
- -1: error sets `errno` to an appropriate error code