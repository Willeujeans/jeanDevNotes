# Interprocess communication
_Mechanisms that allows processes to communicate with each other._
If multiple processes are running at the same time, they need to be able to communicate with each other. If a Process is tasked with moving boxes, it needs to know if another Process has changed the location of those boxes.
## Independent Processes
_Processes that cannot affect or be affected by other processes executing in the system._
## Cooperating Processes
_Processes that can affected by other Processes in the system._
Processes that are cooperating need mechanisms to allow the processes to communicate with each other, because they can affect each others data.
### Producer Consumer Problem
_An issue that deals with the synchronization of processes that share resources._
- **Producers** must wait if the buffer is full to avoid overwriting existing data.
- **Consumers** must wait if the buffer is empty to avoid consuming non-existent data.
# Solutions
_Ways we can fix the producer consumer problem found within Cooperating Processes._
## Shared Memory
_Processes exchange information by reading and writing data to a shared region of memory._
``` ASCII Extended
┌───────────────────────┐  
│      Process A        ├─┐
├───────────────────────┤ │
│                       │◄┘
│ Shared Memory Segment │  
│                       ├─┐
├───────────────────────┤ │
│      Process B        │◄┘
├───────────────────────┤  
│                       │  
│                       │  
├───────────────────────┤  
│        Kernel         │  
└───────────────────────┘  
```
### Unbounded Buffer
_A buffer with no size limit._
The Producer can always produce more items.
The Consumer must wait when the buffer is empty.
### Bounded Buffer
_A buffer with a limited size._
The Producer must wait if the buffer is full.
The Consumer must wait if the buffer is empty.

The address space of this shared-memory region is the same as the process that created it.
When `ProcessA` wants to _communicate_ with `ProcessB` `ProcessA` will create a shared memory region that resides in the address space of `ProcessA`

The other process must _attach_ this region onto its own address space: attaching will _map_ the shared memory segment into the process's address space, allowing it to _read_ from and _write_ to the shared memory as if it were regular memory.

**Mapping**: When a shared memory segment is attached, the OS updates the process's page table to include the shared memory segment, allowing access through virtual addresses.

Both processes must remove the restriction of not being able to access other processes memory.

Unbounded Buffer: There is no limit to the size of the buffer. Consumer has to _wait_ for new items, the producer can always _produce_ items.

Bounded Buffer: Assumes a fixed buffer size, Consumer must wait until the buffer is empty, Producer must _wait_ for the buffer to be full
### Steps
1. ProcessA creates a shared region
2. ProcessB attaches the shared region to is address
3. Both processes allow other processes to access their memory
### Code
``` c
#define SHM_SIZE 256  // Size of the shared memory segment

int main() {
    int shmid;
    char *shared_memory;

    // Create a unique key
    key_t key = ftok("shmfile", 65);
    
    // Create shared memory segment
    shmid = shmget(key, SHM_SIZE, 0666 | IPC_CREAT);
    if (shmid < 0) {
        perror("shmget");
        exit(1);
    }

    // Attach to the shared memory
    shared_memory = shmat(shmid, NULL, 0);
    if (shared_memory == (char *)(-1)) {
        perror("shmat");
        exit(1);
    }

    // Write to shared memory
    printf("Process 1: Writing to shared memory...\n");
    sprintf(shared_memory, "Hello from Process 1!");

    // Detach from shared memory
    shmdt(shared_memory);

    return 0;
}

```
## Message Passing Systems
_A mechanism that allows Processes to communicate without sharing the same address space._
``` ASCII Extended
┌──────────────────────┐     
│      Process A       ├────┐
├──────────────────────┤    │
│      Process B       │◄─┐ │
├──────────────────────┤  │ │
│                      │  │ │
├──────────────────────┤  │ │
│                      │  │ │
├──────────────────────┤  │ │
│                      ├──┘ │
│        Kernel        │    │
│                      │◄───┘
└──────────────────────┘     
```
### Fixed Size Messages
_The length of the messages are always a fixed size._
System level implementation become easy, because the messages are always the same size.  
This will make programming more difficult, because messages must always be the same size.  
### Variable Size Messages
_The length of messages can be any size._
System level implementation becomes difficult, because you need to account for many size messages.  
Programming becomes easy because messages can be any size.  
### Link
_The connection allowing messages to be sent between Processes._ 

---
### Message Issues: Naming
_Processes must have a way to refer to each other if they want to communicate._
#### Direct Communication
A link is established between two process that explicitly name each other as sender and receiver, this is symmetry in addressing.
``` C
send(receiverName, message)
receive(senderName, message)
```
Another variant is when only the sender names the receiver:
``` C
send(receiverName, message)
receive(senderID, message) //senderID will be the process ID of whichever process sent to it.
```
#### Indirect Communication
A link is established between all processes that share mail boxes, messages are placed into mailboxes that have unique identifications.
``` C
send(mailBoxName, message)
receive(mailBoxName, message)
```

---
### Message Issues: Synchronization
#### Synchronous Communication
_A sender waits for the receiver's acknowledgment of receiving the message before continuing execution._
#### Asynchronous Communication
_A sender can send their message and continue execution without needing to wait for the receiver's acknowledgment._

---
### Message Issues: Buffering
#### Automatic Buffering
_The IPC system automatically handles the buffering of messages._
#### Explicit Buffering
_A sender and receiver must explicitly manage the buffer, including its size and how messages are added and removed._

---
## Pipes
_A mechanism allowing Processes a one way communication with each other._
Pipes are a one way directional transfer of data that is larger than the 8-bit exit integer that is returned when a Process terminates.  
Pipes follow a **Producer** and **Consumer** relationship, where the Process on the **write** end of the pipe 'Produces' data in the buffer and the Process on the **read** end 'Consumes' the data from the buffer. 
This 'Consumption' of the data when reading it, means the data no longer exists within the buffer.  
Pipes are data structures maintained by the operating system.  
### Steps
1. ProcessA: **Creates** the pipe.
2. ProcessA: **Creates** Child Process (_the child inherits the Pipe_).
3. ProcessA: **Closes** the Pipe's read end.
4. ProcessB: **Closes** the Pipe's write end.
5. ProcessA: **Write** to the Pipe's buffer.
6. ProcessB: **Read** from the Pipe's buffer.
7. ProcessA: **Closes** the Pipe's write end.
8. ProcessB: **Closes** the Pipe's read end.
### Code
``` C
int main(int argc, char *argv[]){
	int read = 0;
	int write = 1;
	int errorValue = -1;
	int fileDescriptor[2]; // [0]: read, [1]:write
	if(pipe(fileDescriptor) == errorValue){ //pipe(int pipeIDs[2]);
		printf("An Error has occured when opening the pipe");
		return 1;
	}
	
	int id = fork(); // fileDescriptors[] are copied to the Child Process
	if (id == errorValue){
		printf("An Error has occured when trying to fork()");
		return 1;
	}
	
	if (id == 0){ // this is in the Child process
		close(fileDescriptor[0]); // closed the reading, Child will not read
		int inputValue;
		printf("Input a number: ");
		scanf("%d", &inputValue);
		if (write(fileDescriptor[write], &inputValue, sizeof(int)) == errorValue){
			printf("An Error has occured when writing to the pipe");
			return 2;
		}
		close(fileDescriptor[write]);
	} else { // this is in the Parent process
		int valueToRead;
		if (read(fileDescriptor[read], &valueToRead, sizeof(int)) == errorValue){
			printf("An Error has occured when reading from the pipe");
			return 2;
		}
		close(fileDescriptor[read]);
		printf("Got from child Process %d\n", valueToRead);
		wait(NULL);
	}
	
	return 0;
}
```