# Inter Process Communication

- Inter Process Communication (IPC) is the process of exchanging data between two or more processes.
- Two types of IPC are:
  - Shared Memory IPC
  - Message Passing IPC

## Shared Memory System

- A Shared memory is a region of memory that can be accessed by multiple processes.
- The memory is shared between the processes, so they can read and write to it.
- Communication is in user control

## Message Passing System

- Message passing is a method of inter-process communication in which processes communicate by sending messages to each other.
- To send message a communication channel is used.

### Naming

- Processes must have a way to refer to each other.
- The process name is a unique identifier for a process.
- `send(P,message)` sends a message to process P.
- `receive(P,message)` receives a message from process P.
- Symmetry in addressing is having name for send and recieve.
- Assymetry in addressing is having name for send and not recieve.
- In indirect communication message can be sent to port.

### Synchronisation

- Message sending may be synchronous or asynchronous.
  - Blocking send
    - Sending a message blocked until the message is received.
  - Non blocking send
    - Sending a message does not block the sender.
  - Blocking receive
    - Receiving a message blocked until a message is sent.
  - Non blocking receive
    - Receiver retrieves either a valid message or null

### Buffering

- Messages are buffered in the sender and receiver.
- Exchanged via temporary queue
  - Zero capacity queue
    - Queue has no capacity
    - Sender blocks until receiver receives a message
  - Bounded capacity queue
    - Queue has a capacity
  - Unbounded capacity queue
    - Queue has unlimited capacity
    - Sender blocks until receiver receives a message
