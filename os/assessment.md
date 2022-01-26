### Self Assessment

+ Must Read +

    Read the Assessment *[or]* Try to Answer the Questions without Opening the Accordion.

+ What is an operating system? +

    From the book "Operating Systems: Three Easy Pieces":

    "responsible for making it easy to run programs (even allowing you to seemingly run many at the same time), allowing programs to share memory, enabling programs to interact with devices, and other fun stuff like that".

+ Can you explain what is a process? +

    A process is a running program. A program is one or more instructions and the program (or process) is executed by the operating system.


+ If you had to design an API for processes in an operating system, what would this API look like? +

    It would support the following:

    * Create - allow to create new processes
    * Delete - allow to remove/destroy processes
    * State - allow to check the state of the process, whether it's running, stopped, waiting, etc.
    * Stop - allow to stop a running process


+ How a process is created? +

  * The OS is reading program's code and any additional relevant data
  * Program's code is loaded into the memory or more specifically, into the address space of the process.
  * Memory is allocated for program's stack (aka run-time stack). The stack also initialized by the OS with data like argv, argc and parameters to main()
  * Memory is allocated for program's heap which is required for dynamically allocated data like the data structures linked lists and hash tables
  * I/O initialization tasks are performed, like in Unix/Linux based systems where each process has 3 file descriptors (input, output and error)
  * OS is running the program, starting from main()


+ True or False? The loading of the program into the memory is done eagerly (all at once) +

    False. It was true in the past but today's operating systems perform lazy loading which means only the relevant pieces required for the process to run are loaded first.


+ What are different states of a process? +

  * Running - it's executing instructions
  * Ready - it's ready to run but for different reasons it's on hold
  * Blocked - it's waiting for some operation to complete. For example I/O disk request


+ What are some reasons for a process to become blocked? +

  - I/O operations (e.g. Reading from a disk)
  - Waiting for a packet from a network


+ What is Inter Process Communication (IPC)? +

    Inter Process Communication (IPC) refers to a mechanism, where the operating systems allow various processes to communicate with each other. This involves synchronizing their actions and managing shared data.

+ What is "time sharing"? +

    Even when using a system with one physical CPU, it's possible to allow multiple users to work on it and run programs. This is possible with time sharing where computing resources are shared in a way it seems to the user the system has multiple CPUs but in fact it's simply one CPU shared by applying multiprogramming and multi-tasking.


+ What is "space sharing"? +

    Somewhat the opposite of time sharing. While in time sharing a resource is used for a while by one entity and then the same resource can be used by another resource, in space sharing the space is shared by multiple entities but in a way where it's not being transferred between them.<br>
    It's used by one entity until this entity decides to get rid of it. Take for example storage. In storage, a file is yours until you decide to delete it.


+ What component determines which process runs at a given moment in time? +

    CPU scheduler

+ What is "virtual memory" and what purpose it serves? +

    Virtual memory is a feature of an operating system that enables a computer to be able to compensate shortages of physical memory by transferring pages of data from random access memory to disk storage

+ What is demand paging? +

    Demand paging is a method of virtual memory management. In a system that uses demand paging, the operating system copies a disk page into physical memory only if an attempt is made to access it and that page is not already in memory.

+ What is copy-on-write or shadowing? +

    Copy-on-write (COW), sometimes referred to as implicit sharing or shadowing, is a resource-management technique used in computer programming to efficiently implement a "duplicate" or "copy" operation on modifiable resources.

+ What is a kernel, and what does it do? +

    The kernel is part of the operating system and is responsible for tasks like:

    * Allocating memory
    * Schedule processes
    * Control CPU


+ True or False? Some pieces of the code in the kernel are loaded into protected areas of the memory so applications can't overwritten them +

    True


+ What is POSIX? +

    POSIX defines both the system- and user-level application programming interfaces (API), along with command line shells and utility interfaces, for software compatibility (portability) with variants of Unix and other operating systems. POSIX is also a trademark of the IEEE.

+ Explain what is Semaphore and what its role in operating systems +
    
    Semaphores are integer variables that are used to solve the critical section problem by using two atomic operations, wait and signal that are used for process synchronization.

+ What is cache? What is buffer? +

    Buffer: Reserved place in RAM which is used to hold data for temporary purposes
    Cache: Cache is usually used when processes reading and writing to the disk to make the process faster by making similar data used by different programs easily accessible.

