# System Calls
_A Call to the operating system to accomplish a task that needs higher permissions_
When a Process makes a System Call, this will trigger a Trap which will transition the operating system from User Mode (_a mode with less permissions_) into Kernel Mode (_a mode with high level privileges_).
## Trap
_An interruption used to transfer control from User Mode to Kernel Mode._
1. Trigger
    - Running program makes a system call or throws an exception
2. Switching Mode
    - CPU saves the current process state (program counter, registers, etc.)
    - CPU switches from user mode to kernel mode
3. Locate the Trap Handler
    - OS maintains a **trap table** (or interrupt vector) that maps trap types to their corresponding handlers (functions)
    - Each trap has a specific number (or code) that the CPU uses to look up the correct handler in the trap table
4. Executing the Trap Handler
    - For system calls, the handler performs the requested service
    - For exceptions, it will log the error and terminate the process or notify the user
1. Restoring the State
    - OS prepares to return control to the original process
    - restores the saved state (registers, program counter) and switches the CPU back to user mode
2. Continuing Execution
    - Process resumes execution where it left off