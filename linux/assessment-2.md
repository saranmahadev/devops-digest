##### Self Assessment

+ Must Read +

  Read the Assessment *[or]* Try to Answer the Questions without Opening the Accordion.

+ What is chroot? In what scenarios would you consider using it? +

  chroot is a tool that allows you to create a virtual environment in which you can run commands on a system.
  It is useful for running commands that require root privileges, but without having to run them as root.

+ What is SELiunx? +

  SELinux is a Linux security framework that provides a layer of security between the kernel and applications.
  It is a mandatory part of the Linux kernel, and is used to protect the system from malicious software.

+ What is Kerberos? +

  Kerberos is a security framework that allows you to securely authenticate users and other entities.
  It is used to authenticate users and other entities on a network.

+ What is nftables? +

  nftables is a Linux firewall that provides a layer of security between the kernel and applications.
  It is a mandatory part of the Linux kernel, and is used to protect the system from malicious software.

+ What firewalld daemon is responsible for? +

  firewalld is a Linux firewall that provides a layer of security between the kernel and applications.
  It is a mandatory part of the Linux kernel, and is used to protect the system from malicious software.

+ Do you have experience with hardening servers? Can you describe the process? +

  Yes. To harden a server, you need to do the following:
  1. Manage Server Access
  2. Minmize the External Footprint
  3. Patch the Server
  4. Minimize Attack Surface
  5. Restrict Admin Access
  6. Know What's Happening
  7. Minimize User Access Permissions
  8. Establish Communications Security
  9. and more...

+ How to list all the interfaces? +

  ```
  ip link show
  ```


+ What is the loopback (lo) interface? +

  The loopback interface is a special, virtual network interface that your computer uses to communicate with itself. It is used mainly for diagnostics and troubleshooting, and to connect to servers running on the local machine.


+ What the following commands are used for: ip addr, ip route, ip link, ping, netstat, traceroute +

  - ip addr: To display the IP address of the interface.
  - ip route: To display the routing table.
  - ip link: To display the network interfaces.
  - ping: To ping a host.
  - netstat: To display the network status.
  - traceroute: To trace the route to a host.

+ What is a network namespace? What is it used for? +

  A network namespace is a virtual network interface that is created for each process.
  It is used to isolate network traffic from other processes.

+ How to check if a certain port is being used? +

  One of the following would work:

  ```
  netstat -tnlp | grep <port_number>
  lsof -i -n -P | grep <port_number>
  ```

+ How can you turn your Linux server into a router? +

  ```
  sudo sysctl -w net.ipv4.ip_forward=1
  ```

+ What is a virtual IP? In what situation would you use it? +

  A virtual IP is a virtual IP address that is assigned to a network interface.
  It is used to isolate network traffic from other processes.

+ True or False? The MAC address of an interface is assigned/set by the OS +

  False


+ Can you have more than one default gateway in a given system? +

  Yes. You can have more than one default gateway.

+ What is telnet and why is it a bad idea to use it in production? (or at all) +

  Telnet is a type of client-server protocol that can be used to open a command line on a remote computer, typically a server.By default, all the data sent and received via telnet is transmitted in clear/plain text, therefore it should not be used as it does not encrypt any data between the client and the server.

+ What is the routing table? How do you view it? +

  The routing table is a table that contains the routing information for each network interface.
  It is used to determine the next hop for a given destination. To view the routing table, run the following command:`ip route`

+ How can you send an HTTP request from your shell? +

  ```
  curl -X GET http://<url>
  ```

+ What are packet sniffers? Have you used one in the past? If yes, which packet sniffers have you used and for what purpose? +

  It is a network utility that analyses and may inject tasks into the data-stream travelling over the targeted network.

+ How to list active connections? +

  ```
  netstat -tulpn
  ```

+ How to trigger neighbor discovery in IPv6? +

  One way would be `ping6 ff02::1`


+ What is network interface bonding and do you know how it's performed in Linux? +

  Network interface bonding is a method of combining multiple network interfaces into a single interface.
  It is used to improve the performance of a network by combining multiple interfaces into a single interface.

+ What network bonding modes are there? +

  There a couple of modes:

  * balance-rr: round robing bonding
  * active-backup: a fault tolerance mode where only one is active
  * balance-tlb: Adaptive transmit load balancing
  * balance-alb: Adaptive load balancing


+ What is a bridge? How it's added in Linux OS? +

  A bridge is a virtual network interface that is created for each process.
  It is used to isolate network traffic from other processes. It can be added using the following command:
  ```
  brctl addbr br0
  ```

+ How to check what is the hostname of the system? +

  `cat /etc/hostname`

  You can also run `hostnamectl` or `hostname` but that might print only a temporary hostname. The one in the file is the permanent one.


+ What the file `/etc/resolv.conf` is used for? What does it include? +

  The resolv.conf file is used to specify the DNS servers that are used by the system.
  It is used to resolve hostnames to IP addresses.

+ What commands are you using for performing DNS queries (or troubleshoot DNS related issues)? +

  You can use the following commands:
  - `dig`
  - `host`
  - `nslookup`

+ You run `dig saranmahadev.tech` and get the following result: +

  ```
  ANSWER SECTION:
  saranmahadev.tech.      0       IN      A       199.36.158.100
  ```

+ What is the meaning of the number 3515? +

  The number 3515 is the number of seconds that the DNS server will wait for a response from the remote host.


+ Do you have experience with packaging? (as in building packages) Can you explain how does it works? +

  Yes. Packaging is a process of creating a package that can be installed on a computer.
  Packaging is done using the `dpkg` command.

+ How packages installation/removal is performed on the distribution you are using? +

  The answer depends on the distribution being used.

  In Fedora/CentOS/RHEL/Rocky it can be done with `rpm` or `dnf` commands.
  In Ubuntu it can be done with the `apt` command.

+ RPM: explain the spec format (what it should and can include) +

  The spec file is a file that contains the information about the package.
  It is used to specify the package name, version, release, description, etc.
  The spec file is used to create the package.

+ How do you list the content of a package without actually installing it? +

  `apt list <package_name>`

+ How to know to which package a file on the system belongs to? Is it a problem if it doesn't belongs to any package? +

  `apt list <file_name>`

+ Where repositories are stored? (based on the distribution you are using) +
  
  The repositories are stored in the following locations:

  * Fedora/CentOS/RHEL/Rocky: /etc/yum.repos.d
  * Ubuntu: /etc/apt/sources.list.d

+ What is an archive? How do you create one in Linux? +

  An archive is a file that contains a collection of files.
  It is used to store a collection of files in a single file.
  To create an archive, use the following command:
  ```
  tar -cvf <archive_name> <file_name>
  ```

+ How to extract the content of an archive? +

  To extract the content of an archive, use the following command:
  ```
  tar -xvf <archive_name>
  ```

+ Why do we need package managers? Why not simply creating archives and publish them? +

  Package managers allow you to manage packages lifecycle as in installing, removing and updating the packages. In addition, you can specify in a spec how a certain package will be installed - where to copy the files, which commands to run prior to the installation, post the installation, etc.

+ What is DNF? +

  Dandified YUM is a package manager that is used to install packages on Fedora/CentOS/RHEL/Rocky.

+ How to look for a package that provides the command /usr/bin/git? (the package isn't necessarily installed) +

  dnf provides /usr/bin/git

+ What can you find in /etc/services? +

  The /etc/services file contains a list of services and their ports.

+ How to make sure a Service starts automatically after a reboot or crash? +

  Depends on the init system.

  Systemd: ` systemctl enable [service_name] `
  System V: ` update-rc.d [service_name] ` and add this line ` id:5678:respawn:/bin/sh /path/to/app ` to /etc/inittab
  Upstart: add Upstart init script at /etc/init/service.conf

+ You run `ssh 127.0.0.1` but it fails with "connection refused". What could be the problem? +

  1. SSH server is not installed
  2. SSH server is not running

+ How to print the shared libraries required by a certain program? What is it useful for? +

  `ldd <program_name>`

+ What is CUPS? +

  CUPS is a printing system that allows you to print files from your computer.
  It is used to print files from your computer to a printer.

+ What types of web servers are you familiar with? +

  Nginx, Apache httpd.

+ What is a "superuser" (or root user)? How is it different from regular users? +

  A superuser is a user with root privileges.
  A regular user is a user without root privileges.

+ How do you create users? Where user information is stored? +

  Command to create users is `useradd`. The user information is stored in the following files:
  ```
  /etc/passwd
  /etc/shadow
  /etc/group
  /etc/gshadow
  ```

+ Which file stores information about groups? +

  `/etc/groups` file stores the group name, group ID, usernames which are in secondary group.


+ How do you change/set the password of a user? +

  `passwd <username>` is the command to set/change password of a user.


+ Which file stores users passwords? Is it visible for everyone? +

  `/etc/shadow` file holds the passwords of the users in encryted format. NO, it is only visble to the `root` user

+ Do you know how to create a new user without using adduser/useradd command? +

  YES, we can create new user by manually adding an entry in the `/etc/passwd` file. 

  For example, if we need to create a user called `john`. 

  Step 1: Add an entry to `/etc/passwd` file, so user gets created.

  `echo "john:x:2001:2001::/home/john:/bin/bash" >> /etc/passwd` 

  Step 2: Add an entry to `/etc/group` file, because every user belong to the primary group that has same name as the username.

  `echo "john:x:2001:" >> /etc/group`

  Step 3: Verify if the user got created

  `id john`


+ What information is stored in /etc/passwd? explain each field +

  `/etc/passwd` is a configuration file, which contains users information. Each entry in this file has, 7 fields,

  `username:password:UID:GID:Comment:home directory:shell`

  `username` - The name of the user.

  `password` - This field is actually a placeholder of the password field. Due to security concerns, this field does not contain the password, just a placeholder (x) to the encrypted password stored in `/etc/shadow` file.

  `UID` - User ID of the user.

  `GID` - Group ID 

  `Comment` - This field is to provide description about the user.

  `home directory` - Abousulte path of the user's home directory. This directory gets created once the user is added.

  `shell` - This field contains the absolute path of the shell that will be used by the respective user.


+ How to add a new user to the system without providing him the ability to log-in into the system? +

  `adduser user_name --shell=/bin/false --no-create-home`
  You can also add a user and then edit /etc/passwd.


+ How to switch to another user? How to switch to the root user? +

  su command.
  Use su - to switch to root


+ What is the UID the root user? What about a regular user? +

  UID of root user is 0

  Default values of UID_MIN and UID_MAX in `/etc/login.defs`
  `UID_MIN` is `1000`
  `UID_MAX` is `60000`

  Actually, we can change this value. But UID < 1000 are reserved for system accounts.
  Therefore, as per the default configuration, for regular user UID starts from `1000`. 


+ What can you do if you lost/forogt the root password? +

  If you lost/forgot the root password, you can use the following command to change the password:
  `passwd`


+ What is /etc/skel? +

  `/etc/skel` is a directory, that contains files or directories, so when a new user is created, these files/directories created under `/etc/skel` will be copied to user's home directory.


+ How to see a list of who logged-in to the system? +

  Using the `last` command.

+ Explain what each of the following commands does: useradd, usermod, whoami,* id +

  `useradd` - Command for creating new users 
  `usermod` - Modify the users setting
  `whoami`  - Outputs, the username that we are currently logged in
  `id`      - Prints the user ID of the user

+ You run `grep $(whoami) /etc/passwd` but the output is empty. What might be a possible reason for that? +

  The user you are using isn't defined locally but originates from services like LDAP.<br>
  You can verify with: `getent passwd`

+ Where can you find information on the processor (like number of CPUs)? +

  /proc/cpuinfo

  You can also use `nproc` for number of processors

+ How can you print information on the BIOS, motherboard, processor and RAM? +

  dmidecoode

+ How can you print all the information on connected block devices in your system? +

  lsblk

+ True or False? In user space, applications don't have full access to hardware resources +

  True. Only in kernel space they have full access to hardware resources.


+ How do you create a private key for a CA (certificate authority)? +

  One way is using openssl this way:
  `openssl genrsa -aes256 -out ca-private-key.pem 4096`


+ How do you create a public key for a CA (certificate authority)? +

  `openssl req -new -x509 -days 730 -key [private key file name] -sha256 -out ca.pem`

  If using the private key from the previous question then the command would be:

  `openssl req -new -x509 -days 730 -key ca-private-key.pem -sha256 -out ca.pem`

+ What types of namespaces are there in Linux? +

  - Process ID namespaces: these namespaces include independent set of process IDs
  - Mount namespaces: Isolation and control of mountpoints
  - Network namespaces: Isolates system networking resources such as routing table, interfaces, ARP table, etc.
  - UTS namespaces: Isolate host and domains
  - IPC namespaces: Isolates interprocess communications
  - User namespaces: Isolate user and group IDs
  - Time namespaces: Isolates time machine

+ True or False? In every PID (Process ID) namespace the first process assigned with the process id number 1 +

  True. Inside the namespace it's PID 1 while to the parent namespace the PID is a different one.


+ True or False? In a child PID namespace all processes are aware of parent PID namespace and processes and the parent PID namespace has no visibility of child PID namespace processes +

  False. The opposite is true. Parent PID namespace is aware and has visibility of processes in child PID namespace and child PID namespace has no visibility as to what is going on in the parent PID namespace.


+ True or False? By default, when creating two separate network namespaces, a ping from one namespace to another will work fine +

  False. Network namespace has its own interfaces and routing table. There is no way (without creating a bridge for example) for one network namespace to reach another.

+ True or False? With UTS namespaces, processes may appear as if they run on different hosts and domains while running on the same host +

  True


+ True or False? It's not possible to have a root user with ID 0 in child user namespaces +

  False. In every child user namespace, it's possible to have a separate root user with uid of 0.


+ What time namespaces are used for? +

  In time namespaces processes can use different system time.


+ What virtualization solutions are available for Linux? +

  * [KVM](https://www.linux-kvm.org/page/Main_Page)
  * [XEN](http://www.xen.org/)
  * [VirtualBox](https://www.virtualbox.org/)
  * [Linux-VServer](http://linux-vserver.org/Welcome_to_Linux-VServer.org)
  * [User-mode Linux](http://user-mode-linux.sourceforge.net/)

+ What is KVM? +

  Is an open source virtualization technology used to operate on x86 hardware. 

  From the official [docs](https://www.linux-kvm.org/page/Main_Page)
  Recommended read:
    * [Red Hat Article - What is KVM?](https://www.redhat.com/en/topics/virtualization/what-is-KVM)

+ What is Libvirt? +

  It's an open source collection of software used to manage virtual machines. It can be used with: KVM, Xen, LXC and others. It's also called Libvirt Virtualization API.

  From the official [docs](https://libvirt.org/)
  Hypervisor supported [docs](https://libvirt.org/drivers.html)


+ What the `awk` command does? Have you used it? What for? +

  - `awk` is a command-line utility for processing text files.

+ How to print the 4th column in a file? +

  `awk '{print $4}' file`


+ How to print every line that is longer than 79 characters? +

  `awk 'length($0) > 79' file`


+ What the `lsof` command does?  +

  - `lsof` is a command that lists open files.

+ What is the difference between find and locate? +

  - `find` is a command-line utility for searching for files and `locate` is a command-line utility for searching for files in a directory tree.
  - We need to use find to find the file in the **current directory** and then use locate to find the file in the **entire system**.

+ How a user process performs a privileged operation, such as reading from the disk? +

  Using system calls

+ What is a system call? What system calls are you familiar with? +

  - A system call is a request to the operating system to perform a specific task.
  - The following are the some system calls:
    * `open`
    * `read`
    * `write`
    * `close`
    * `fork`
    * `exec`
    * `exit`
    * `wait`
    * `pipe`
    * `dup2`
    * `getpid`
    * `getppid`
    * `getuid`
    * `geteuid`
    * `getgid`
    * `getegid`
    * `getgroups`
    * `setuid`
    * `setgid`
    * `setgroups`
    * `chroot`
    * `chdir`
    * `getcwd`
    * `getdents`
    * `getdents64`
    * `mmap`
    * `munmap`
    * `mprotect`
    * `mremap`
    * `msync`
    * `madvise`
    * `shm_open`
    * `shm_unlink`
    * `shmget`
    * `shmat`
    * `shmdt`
    * `shmctl`
    * `gettid`
    * `gettimeofday`
 

+ How a program executes a system call? +

  - A program executes a trap instruction. The instruction jump into the kernel while raising the privileged level to kernel space.
  - Once in kernel space, it can perform any privileged operation
  - Once it's finished, it calls a "return-from-trap" instruction which returns to user space while reducing back the privilege level to user space.


+ Explain the fork() system call +

  fork() is used for creating a new process. It does so by cloning the calling process but the child process has its own PID and any memory locks, I/O operations and semaphores are not inherited.


+ What is the return value of fork()? +

  - On success, the PID of the child process in parent and 0 in child process
  - On error, -1 in the parent


+ Name one reason for fork() to fail +

  Not enough memory to create a new process


+ Why do we need the wait() system call? +

  wait() is used by a parent process to wait for the child process to finish execution.
  If wait is not used by a parent process then a child process might become a zombie process.


+ How the kernel notifies the parent process about child process termination? +

  The kernel notifies the parent by sending the SIGCHLD to the parent.


+ How the waitpid() is different from wait()? +

  The waitpid() is a non-blocking version of the wait() function. It also supports using library routine (e.g. system()) to wait a child process without messing up with other children processes for which the process has not waited.


+ True or False? The wait() system call won't return until the child process has run and exited +

  True in most cases though there are cases where wait() returns before the child exits.


+ Explain the exec() system call +

  It transforms the current running program into another program.Given the name of an executable and some arguments, it loads the code and static data from the specified executable and overwrites its current code segment and current static code data. After initializing its memory space (like stack and heap) the OS runs the program passing any arguments as the argv of that process.


+ True or False? A successful call to exec() never returns +

  True.Since a succesful exec replace the current process, it can't return anything to the process that made the call.


+ What system call is used for listing files? +

  - getdents() is the system call that is used to list files in a directory.

+ What system calls are used for creating a new process? +

  fork(), exec() and the wait() system call is also included in this workflow.

+ What execve() does? +

  Executes a program. The program is passed as a filename (or path) and must be a binary executable or a script.


+ What is the return value of malloc? +

  - On success, the address of the allocated memory is returned.
  - On error, NULL is returned.

+ Explain the pipe() system call. What does it used for? +

  [Unix pipe implementation](https://toroid.org/unix-pipe-implementation)

  "Pipes provide a unidirectional interprocess communication channel. A pipe has a read end and a write end. Data written to the write end of a pipe can be read from the read end of the pipe. A pipe is created using pipe(2), which returns two file descriptors, one referring to the read end of the pipe, the other referring to the write end."

+ What happens when you execute `ls -l`? +

  * Shell reads the input using getline() which reads the input file stream and stores into a buffer as a string
  * The buffer is broken down into tokens and stored in an array this way: {"ls", "-l", "NULL"}
  * Shell checks if an expansion is required (in case of ls *.c)
  * Once the program in memory, its execution starts. First by calling readdir()

  Notes:
  * getline() originates in GNU C library and used to read lines from input stream and stores those lines in the buffer

+ What happens when you execute `ls -l *.log`? +

  - Raise a Issue and Contribute the Answer For the Question.

+ What readdir() system call does? +

  readdir() is used to read the directory entries.

+ What exactly the command `alias x=y` does? +

  - `alias` is a command that creates an alias for a command.
  - `alias x=y` creates an alias for the command `x` to be `y`

+ Why running a new program is done using the fork() and exec() system calls? why a different API wasn't developed where there is one call to run a new program? +

  This way provides a lot of flexibility. It allows the shell for example, to run code after the call to fork() but before the call to exec(). Such code can be used to alter the environment of the program it about to run.

+ Describe shortly what happens when you execute a command in the shell +

  The shell figures out, using the PATH variable, where the executable of the command resides in the filesystem. It then calls fork() to create a new child process for running the command. Once the fork was executed successfully, it calls a variant of exec() to execute the command and finally, waits the command to finish using wait(). When the child completes, the shell returns from wait() and prints out the prompt again.


+ How to create a file of a certain size? +

  There are a couple of ways to do that:

    * dd if=/dev/urandom of=new_file.txt bs=2MB count=1
    * truncate -s 2M new_file.txt
    * fallocate -l 2097152 new_file.txt

<!-- tabs:start -->

#### **Question**

What does the following block do?:

  ```
  open("/my/file") = 5
  read(5, "file content")
  ```

#### **Answer**

These system calls are reading the file `/my/file` and 5 is the file descriptor number.

<!-- tabs:end -->

+ Describe three different ways to remove a file (or its content) +

  - unlink()
  - rm()
  - rm -rf

+ What is the difference between a process and a thread? +

  A process is a single program that is running on a single machine. A thread is a single program that is running on a single machine.

+ What is context switch? +

  From [wikipedia](https://en.wikipedia.org/wiki/Context_switch): a context switch is the process of storing the state of a process or thread, so that it can be restored and resume execution at a later point


+ You found there is a server with high CPU load but you didn't find a process with high CPU. How is that possible? +

  - It is possible for the following reasons:
    - The server is lacking Updated Drivers
    - Malicious software is installed on the server
    - Power supply is not sufficient 

+ When you run `ip a` you see there is a device called 'lo'. What is it and why do we need it? +

  - The loopback device is a virtual device that is used to connect the host to the network. It is used to send and receive packets that are not destined for other hosts.
  - It is used to send and receive packets that are not destined for other hosts.

+ What the `traceroute` command does? How does it works? +

  `trace route` is a command that is used to trace the route of a packet. It works by sending a packet to a destination and then tracing the route of the packet.

+ What is network bonding? What types are you familiar with? +

  - Network bonding is a technique that allows multiple network interfaces to share the same network.
  - Types of network bonding:
    - Active-Active
    - Active-Passive
    - Load-Balancing
  
+ How to link two separate network namespaces so you can ping an interface on one namespace from the second one? +

  - `ip link set dev eth0 netns ns1`
  - `ip netns exec ns1 ping`

+ What are cgroups? +

  cgroups is a hierarchical system that allows you to control the resources of a process.

+ Explain Process Descriptor and Task Structure +

  - Process Descriptor is a structure that contains information about a process.
  - Task Structure is a structure that contains information about a task.

+ What are the differences between threads and processes? +

  - Threads are lightweight processes that can be scheduled on different CPUs.
  - Processes are heavyweight processes that can be scheduled on different CPUs.

+ Explain Kernel Threads +

  - A kernel thread is the schedulable entity, which means that the system scheduler handles kernel threads. These threads, known by the system scheduler, are strongly implementation-dependent.

+ What happens when socket system call is used? +

  - The socket system call creates a socket.
  - The socket system call returns a file descriptor.
  
+ You executed a script and while still running, it got accidentally removed. Is it possible to restore the script while it's still running? +

  - Yes, you can use the `exec` system call to restore the script.

+ What is the difference between MemFree and MemAvailable in /proc/meminfo? +

  MemFree - The amount of unused physical RAM in your system
  MemAvailable - The amount of available memory for new workloads (without pushing system to use swap) based on MemFree, Active(file), Inactive(file), and SReclaimable.

+ What is the difference between swapping and paging? +

  | Paging                                                                                                                                     | Swapping                                                                                                                     |
  |--------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
  | Paging is a memory management technique in which computer stores and retrieves data from the secondary storage for use in the main memory. | Swapping is a technique that is used to temporarily remove the inactive programs from the main memory of the computer system |
  | This technique allows more processes to reside in the main memory                                                                          | Swapping allows fewer processes to reside in the main memory.                                                                |
  | Paging follows non-contiguous memory management.                                                                                           | Swapping can be done without any memory management technique.                                                                |
  | Paging is more flexible because in this there is the movement of pages of a process.                                                       | Swapping is less flexible as the entire process moves back and forth in the main memory and back store.                      |
  | Paging occurs when some part of the process is transferred to the disk.                                                                    | While Swapping occurs when the whole process is transferred to the disk.                                                     |
  | For medium workloads paging technique is suitable.                                                                                         | For heavy workloads swapping technique is suitable.                                                                          |
  | This technique allows the memory address space of a process to be noncontiguous.                                                           | With the help of Swapping multiple processes can run in parallel in the Operating System                                     |
  | This technique helps to implement virtual memory.                                                                                          | Swapping helps the CPU to access processes faster.                                                                           |



+ Explain what is OOM killer +

  - OOM killer is a daemon that kills processes that are using too much memory.

+ What is a Linux distribution? +

  - A Linux distribution is a collection of software packages that are used to build a computer operating system.

+ What Linux distributions are you familiar with? +

  - Ubuntu
  - Debian
  - CentOS
  - Fedora
  - Arch Linux
  - OpenSUSE
  - Slackware
  - Mandrake
  - Gentoo
  - Slackware
  - Mageia
  - Void Linux
  - Alpine
  - OpenBSD
  - FreeBSD
  - NetBSD

+ What are the components of a Linux distribution? +

  - Kernel
  - Utilities
  - Services
  - Software/Packages Management


+ Using sed, extract the date from the following line: `201.7.19.90 - - [05/Jun/1985:13:42:99 +0000] "GET /site HTTP/1.1" 200 32421` +

  `echo $line | sed 's/.*\[//g;s/].*//g;s/:.*//g'`

+ How to generate a random string? +

  One way is to run the following: `cat /proc/sys/kernel/random/uuid`

+ What is a Linux distribution? +

  * A collection of packages - kernel, GNU, third party apps, ...
  * Sometimes distributions store some information on the distribution in `/etc/*-release` file
  * For example for Red Hat distribution it will be `/etc/redhat-release` and for Amazon it will be `/etc/os-release`
  * `lsb_release` is a common command you can use in multiple different distributions

+ Name 5 commands which are two letters long +

  ps, ip, cp, cd, ls

+ What ways are there for creating a new empty file? +

  * touch new_file
  * echo "" > new_file

+ How `cd -` works? How does it knows the previous location? +

  $OLDPWD

+ List three ways to print all the files in the current directory +

  - ls
  - find .
  - echo *


+ How to count the number of lines in a file? What about words? +

  - `wc -l`
  - `wc -w`

+ You define x=2 in /etc/bashrc and x=6 ~/.bashrc you then login to the system. What would be the value of x? +

  - 6

+ What is the difference between man and info? +

  - `man` command is used to display the user manual of any command that we can run on the terminal.
  - `info` command is used to read multipage documentation and act as help viewer working on a cli.

+ Explain "environment variables". How do you list all environment variables? +
  
  - Environment variables are used to store information about the current environment.
  - `env` command is used to list all environment variables.

+ What is a TTY device? +

  - A terminal device is a device that is used to communicate with the user.

+ How to create your own environment variables? +

  `X=2` for example. But this will persist to new shells. To have it in new shells as well, use `export X=2`


+ What a double dash (--) mean? +

  It's used in commands to mark the end of commands options. One common example is when used with git to discard local changes: `git checkout -- some_file`


+ Wildcards are implemented on user or kernel space? +

  - Kernel space

+ If I plug a new device into a Linux machine, where on the system, a new device entry/file will be created? +

  /dev


+ What is User-mode Linux? +

  - User-mode Linux is a Linux operating system that runs in user space.

+ Under which license Linux is distributed?  +

  GPL v2