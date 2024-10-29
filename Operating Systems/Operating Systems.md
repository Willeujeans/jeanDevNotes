# Operating Systems
_A layer that sits above the hardware abstracting hardware interactions for applications._
Normally a program written in the C coding language, do to its abstraction but low level access.
### What does it do?
- Process and Thread Management
- Concurrency
	Doing many things simultaneously
	several users doing work at the same time
	Many threads being active at a time
- I/O devices
	Lets the CPU work while a SLOW i/o device is working
- Memory Management
	coordinate allocation of memory, moving data between disk and main memory
- Files
	how disk space is used for files
- Distributed Systems & networks
	allowing GROUPS of machines to work together 
### Kernel Mode VS User Mode
A status bit that is flipped back and fourth
This distinction is used for security purposes
When the OS needs to do something it will do it in Kernel mode
When an application needs something done it will be done in User mode
This way users cannot run a program that has the authority of the kernel
### System Calls
OS procedure that executes privileged instructions
- causes a trap which 'vectors' (jumps) to the trap handler in the OS kernel
- User process makes a system call, this activates a trap, which the OS will take in enter kernel mode and complete the task that was requested
### Memory Protection
Hardware check
- use base and limit registers
- Base register, it says where the valid memory location starts
- limit register, it says where the valid memory location ends
- so it will check each instruction and checks which memory addresses it has access to between the bases and limits
Process layout in memory
- Address (hex): FFFF
Segments
- Stack
- Gap
- Data
- Text
### Rings of permissions

Memory Management 
IO management
Runs programs 
schedules programs

DO NOT crash the kernel

Program lives on disk
Run it, now its a process
Process must have a thread
Thread is a list of instructions

Thread pool
# Kernel
*core component responsible managing system resources & communication*
## Responsibilities
### Process Management
Creation, scheduling, and termination of processes (process is an instance of a program in execution)
### Memory Management
including allocating and deallocating memory space to processes
### Device Management
communications with hardware devices via device drivers
### File System Management
Manages files on disk drives: including file creation, deletion, and access permissions, and directory structures
### System Calls
Provides a set of system calls that programs use to request services from the operating system
### Security and Access Control
Enforces security policies and access controls

