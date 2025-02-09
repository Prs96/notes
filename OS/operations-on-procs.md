The system provides mechanism for:

- Creating a process
- Terminating a process

# Process Creation

- A process is created by calling the `fork()` system call.
- It can create a child process or a new process.
- Generally a process is identified by its process ID (PID).
- Resource sharing options:
  - Parent and child share the same resources.
  - Child share subset of resources with parent.
- Execution:
  - Parent and child executes in parallel.
  - Parent waits for child to terminate.
- Address space:
  - Child process is a duplicate of parent process.
  - Child has a new program loaded into it
- fork() system creates a new process and returns the PID of the new process to the parent process.
- exec() is called after fork to replace the proxess memory space with the new program.

```
          +---------+
          | fork()  |
          +---------+
              |
    +---------+---------+
    |                   |
+---------+       +---------+
| exec()  |       | wait()  |
+---------+       +---------+
    |                   |
+---------+       +---------+
| exit()  |       | resumes |
+---------+       +---------+

```

# Process Termination

- `wait()` is used to wait for a child process to terminate.
- `wait()` is called by the parent process to wait for the child process to terminate- `exit()` is used to tell the OS to delete the process
- When a parent creats a child, the identity of child is passed to the parent as a return value of `fork()`.
- A parent may terminate a child for:
  - Child has exceeded resource limits.
  - No longer needed.
  - Parent is exiting (no child without parent "cascading termination").
