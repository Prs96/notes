Os services are provided by the operating system and are used to run programs and applications.

# Program Excecution

- System must be able to load programs into memory and execute them.
- Program must be able to end its execution either normally or abnormally.

# I/O Operations

- A running program may read or write data to/from a device.
- This I/O involve a file or a device.
- For efficiency and protection the user cannot directly access the device.
- Os provides a mechanism to access the device.

# File System Manipulation

- Programs need to read and write data to/from files.
  - Program needs to create, delete, rename, move, copy, and list files.

# Communication

- One proccess needs to communicate with another process.
- Communication can occur in 2 ways
  - In the same computer b/w processes
  - Over the network
- Communication is implemented by shared memory or message passing in packets of information moved through processes by the os

# Error detection and resource allocation

- The os must be able to detect errors and allocate resources.
- Error can occur in the following ways
  - CPU error
  - Memory hardware error
  - I/O error
  - Program error
- For each error the os must be able to take appropriate action to ensure correct and consistent computation.
- when multiple users and programs are running on a computer, the os must be able to allocate resources to each program.

# Accounting and Protection

- The os must be able to keep track of the resources used by each user
- It is saved inorder for accounting or accumulating usage statistics.
- Protection involves ensuring all access to resources is controlled.
- Security is done by authenticating the user and ensuring that the user has the right to access the resource by passwords or other means
