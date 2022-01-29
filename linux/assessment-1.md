#### Self Assessment

+ Must Read +

  Read the Assessment *[or]* Try to Answer the Questions without Opening the Accordion.

+ Explain what each of the following commands does and give an example on how to use it: touch, ls, rm, cat, cp, mkdir, pwd, cd +

  * touch - update file's timestamp. More commonly used for creating files
  * ls - listing files and directories
  * rm - remove files and directories
  * cat - create, view and concatenate files
  * cp - copy files and directories
  * mkdir - create directories
  * pwd - print current working directory (= at what path the user currently located)
  * cd - change directory


+ What each of the following commands does - `cd /`, `cd ~`,`cd .`, `cd ..` and `cd -`? +

  * cd / -> change to the root directory
  * cd ~ -> change to your home directory
  * cd . -> change to the directory you currently in
  * cd .. -> change to the directory above your current i.e parent directory
  * cd - -> change to the last visited path

+ Some of the commands in the previous question can be run with the -r/-R flag. What does it do? Give an example to when you would use it +

  The -r (or -R in some commands) flag allows the user to run a certain command recursively. For example, listing all the files under the following tree is possible when done recursively (`ls -R`):

  /dir1/
    dir2/
      file1
      file2
    dir3/
      file3

  To list all the files, one can run `ls -R /dir1`


+ Explain each field in the output of `ls -l` command +

  It shows a detailed list of files in a long format. From the left:
  * file permissions, number of links, owner name, owner group, file size, timestamp of last modification and directory/file name

+ What are hidden files/directories? How to list them? +

  These are files directly not displayed after performing a standard ls direct listing. An example of these files are .bashrc which are used to execute some scripts. Some also store configuration about services on your host like .KUBECONFIG. The command used to list them is, `ls -a`


+ What do > and < do in terms of input and output for programs? +
  
  They take in input (<) and output for a given file (>) using stdin and stdout.
  `myProgram < input.txt > executionOutput.txt`


+ Explain what each of the following commands does and give an example on how to use it: grep, sed, cut, sort, uniq, wc, tr, awk +

  - grep - search for a pattern in a file
    - Example: `grep -i "hello" myFile.txt`
  - sed - search and replace a pattern in a file
    - Example: `sed -i "s/hello/goodbye/g" myFile.txt`
  - cur - cut a part of a file
    - Example: `cut -d " " -f 1 myFile.txt`
  - sort - sort a file
    - Example: `sort myFile.txt`
  - unip - remove duplicate lines in a file
    - Example: `uniq myFile.txt`
  - wc - count the number of lines, words and characters in a file
    - Example: `wc myFile.txt`
  - tr - translate characters in a file
    - Example: `tr "a-z" "A-Z" myFile.txt`
  - awk - filter lines in a file
    - Example: `awk '{print $1}' myFile.txt`

+ How to rename the name of a file or a directory? +

  Using the `mv` command.

+ Specify which command would you use (and how) for each of the following scenarios - Remove a directory with files, Display the content of a file, Provides access to the file /tmp/x for everyone, Change working directory to user home directory, Replace every occurrence of the word "good" with "great" in the file /tmp/y +

  - `rm -rf dir`
  - `cat or less`
  - `chmod 777 /tmp/x`
  - `cd ~`
  - `sed -i s/good/great/g /tmp/y`


+ How can you check what is the path of a certain command? +

  * whereis
  * which


+ What is the difference between these two commands `echo hello world` and `echo "hello world"`? Will it result in the same output? +

  The echo command receives two separate arguments in the first execution and in the second execution it gets one argument which is the string "hello world". The output will be the same.


+ Explain piping. How do you perform piping? +

  Using a pipe in Linux, allows you to send the output of one command to the input of another command. For example: `cat /etc/services | wc -l`


+ Fix the following commands: `sed "s/1/2/g' /tmp/myFile` and `find . -iname \*.yaml -exec sed -i "s/1/2/g" {} ;` +

  ```
  sed 's/1/2/g' /tmp/myFile  # sed "s/1/2/g" is also fine
  find . -iname "*.yaml" -exec sed -i "s/1/2/g" {} \;
  ```

+ How to check which commands you executed in the past? +

  history command or .bash_history file


+ Running the command `df` you get "command not found". What could be wrong and how to fix it? +

  Most likely the default/generated $PATH was somehow modified or overridden thus not containing `/bin/` where df would normally go.
  This issue could also happen if bash_profile or any configuration file of your interpreter was wrongly modified, causing erratics behaviours.
  You would solve this by fixing your $PATH variable:

  As to fix it there are several options:

  1. Manually adding what you need to your $PATH `PATH="$PATH":/user/bin:/..etc`
  2. You have your weird env variables backed up.
  3. You would look for your distro default $PATH variable, copy paste using method #1

  Note: There are many ways of getting errors like this: if bash_profile or any configuration file of your interpreter was wrongly modified; causing erratics behaviours,
  permissions issues, bad compiled software (if you compiled it by yourself)... there is no answer that will be true 100% of the time.

+ How do you schedule tasks periodically? +

  You can use the commands `cron` and `at`.
  With cron, tasks are scheduled using the following format:

  `*/30 * * * * bash myscript.sh` Executes the script every 30 minutes.

  <minute> <hour> <day of month> <month> <day of week> <command to execute>

  The tasks are stored in a cron file, you can write in it using `crontab -e`

  Alternatively if you are using a distro with systemd it's recommended to use systemd timers.

+ Explain Linux I/O redirection +

  Linux I/O redirection is used to redirect the output of a command to a file or to the standard output.
  For example, the following command will redirect the output of the command `ls` to the file `/tmp/myFile`:

  `ls > /tmp/myFile`


+ Demonstrate Linux output redirection +

  ls > ls_output.txt


+ Demonstrate Linux stderr output redirection +

  yippiekaiyay 2> ls_output.txt


+ Demonstrate Linux stderr to stdout redirection +

  yippiekaiyay 1>&2 


+ What is the result of running the following command? `yippiekaiyay 1>&2 die_hard`` +

  An output similar to: `yippikaiyay: command not found...`<br>
  The file `die_hard` will not be created


+ In Linux FHS (Filesystem Hierarchy Standard) what is the `/`? +

  The root of the filesystem. The beginning of the tree.

<!-- tabs:start -->
#### **Question**
What is stored in each of the following paths?

- /bin, /sbin, /usr/bin and /usr/sbin
- /etc
- /home
- /var
- /tmp 
#### **Answer**
- binaries
- configuration files
- home directories of the different users
- files that tend to change and be modified like logs
- temporary files
<!-- tabs:end -->


+ What is special about the /tmp directory when compared to other directories? +

  `/tmp` folder is cleaned automatically, usually upon reboot.


+ What kind of information one can find in /proc? +

  `/proc` is a directory that contains information about the running processes.

+ What makes /proc different from other filesystems? +

  `/proc` is a virtual filesystem that is not part of the real filesystem.

+ True or False? only root can create files in /proc +

  False. No one can create file in /proc directly (certain operations can lead to files being created in /proc by the kernel).

+ What can be found in /proc/cmdline? +

  The command passed to the boot loader to run the kernel

+ In which path can you find the system devices (e.g. block storage)? +
  
    /dev

+ How to change the permissions of a file? +

  Using the `chmod` command.


+ What does the following permissions mean: 777, 644, 750 ? +

  777 - You give the owner, group and other: Execute (1), Write (2) and Read (4); 4+2+1 = 7.
  644 - Owner has Read (4), Write (2), 4+2 = 6; Group and Other have Read (4).
  750 - Owner has x+r+w, Group has Read (4) and Execute (1); 4+1 = 5. Other have no permissions.

+ What this command does? `chmod +x some_file` +
  
  It adds execute permissions to all sets i.e user, group and others

+ Explain what is setgid and setuid +

  - setgid: The group id of the file is set to the group id of the current user.
  - setuid: The user id of the file is set to the user id of the current user.

+ What is the purpose of sticky bit? +

  Its a bit that only allows the owner or the root user to delete or modify the file.

+ What the following commands do: chmod, chown, chgrp +

  * chmod - changes access permissions to files system objects
  * chown - changes the owner of file system files and directories
  * chgrp - changes the group associated with a file system object

+ What is sudo? How do you set it up? +

  sudo is a program that allows you to run commands as another user.
  To set it up, you need to install the package `sudo` and then add the following line to your `/etc/sudoers` file:

  `root ALL=(ALL) ALL`

+ True or False? In order to install packages on the system one must be the root user or use the sudo command +

  True, you can install packages on the system by using the sudo command.


+ Explain what are ACLs. For what use cases would you recommend to use them? +

  ACLs are a way to control access to files and directories. I would recommend using them for the following use cases:
    - To control access to files and directories that are not owned by the user running the program.

+ You try to create a file but it fails. Name at least three different reason as to why it could happen +

  * No more disk space
  * No more inodes
  * No permissions


+ A user accidentally executed the following `chmod -x $(which chmod)`. How to fix it? +

  You need to change the permissions of the file to 755.


+ What is systemd? +

  Systemd is a daemon (System 'd', d stands for daemon).

  A daemon is a program that runs in the background without direct control of the user, although the user can at any time
  talk to the daemon.

  systemd has many features such as user processes control/tracking, snapshot support, inhibitor locks..

  If we visualize the unix/linux system in layers, systemd would fall directly after the linux kernel.<br>
  Hardware -> Kernel -> <u>Daemons</u>, System Libraries, Server Display.

+ How to start or stop a service? +

  To start a service: `systemctl start <service name>`
  To stop a service: `systemctl stop <service name>`


+ How to check the status of a service? +

  `systemctl status <service name>`


+ On a system which uses systemd, how would you display the logs? +

  `journalctl`


+ Describe how to make a certain process/app a service +

  `systemctl enable <service name>`


+ Where system logs are located? +

  /var/log


+ How to follow file's content as it being appended without opening the file every time? +

  tail -f <file_name>


+ What are you using for troubleshooting and debugging <b>network</b> issues? +

  `dstat -t` is great for identifying network and disk issues.
  `netstat -tnlaup` can be used to see which processes are running on which ports.
  `lsof -i -P` can be used for the same purpose as netstat.
  `ngrep -d any metafilter` for matching regex against payloads of packets.
  `tcpdump` for capturing packets
  `wireshark` same concept as tcpdump but with GUI (optional).


+ What are you using for troubleshooting and debugging <b>disk & file system</b> issues? +

  `dstat -t` is great for identifying network and disk issues.
  `opensnoop` can be used to see which files are being opened on the system (in real time).


+ What are you using for troubleshooting and debugging <b>process</b> issues? +

  `strace` is great for understanding what your program does. It prints every system call your program executed.


+ What are you using for debugging CPU related issues? +

  `top` will show you how much CPU percentage each process consumes
  `perf` is a great choice for sampling profiler and in general, figuring out what your CPU cycles are "wasted" on
  `flamegraphs` is great for CPU consumption visualization (http://www.brendangregg.com/flamegraphs.html)


+ You get a call from someone claiming "my system is SLOW". What do you do? +

  * Check with `top` for anything unusual
  * Run `dstat -t` to check if it's related to disk or network.
  * Check if it's network related with `sar`
  * Check I/O stats with `iostat`


+ Explain iostat output +

  `iostat` is a great tool for monitoring disk and network I/O.

+ How to debug binaries? +

  - To debug binaries, you need to compile them with `gdb` 

+ What is the difference between CPU load and utilization? +

  - **CPU load** is the percentage of CPU time that is used by the system.
  - **CPU utilization** is the percentage of CPU time that is used by the application.

+ How you measure time execution of a program? +

  - `time` command

+ What is a kernel, and what does it do? +

  The kernel is part of the operating system and is responsible for tasks like:

    * Allocating memory
    * Schedule processes
    * Control CPU


+ How do you find out which Kernel version your system is using? +

  `uname -a` command


+ What is a Linux kernel module and how do you load a new module? +

  - A Linux kernel module is a piece of code that is loaded into the kernel.
  - To load a new module, you need to run the following command:
  `sudo insmod <module_name>.ko`

+ Explain user space vs. kernel space +

  The operating system executes the kernel in protected memory to prevent anyone from changing (and risking it crashing). This is what is known as "Kernel space".
  "User space" is where users executes their commands or applications. It's important to create this separation since we can't rely on user applications to not tamper with the kernel, causing it to crash.

  Applications can access system resources and indirectly the kernel space by making what is called "system calls".


+ In what phases of kernel lifecycle, can you change its configuration? +

  * Build time (when it's compiled)
  * Boot time (when it starts)
  * Runtime (once it's already running)


+ Where can you find kernel's configuration? +

  Usually it will reside in `/boot/config-<kernel version>.<os release>.<arch>`


+ Where can you find the file that contains the command passed to the boot loader to run the kernel? +

  `/proc/cmdline`

+ How to list kernel's runtime parameters? +

  `sysctl -a`

+ Will running `sysctl -a` as a regular user vs. root, produce different result? +

  Yes, you might notice that in most systems, when running `systctl -a` with root, you'll get more runtime parameters compared to executing the same command with a regular user.


+ You would like to enable IPv4 forwarding in the kernel, how would you do it? +

  `sudo sysctl net.ipv4.ip_forward=1`

  To make it persistent (applied after reboot for example): insert `net.ipv4.ip_forward = 1` into `/etc/sysctl.conf`

  Another way to is to run `echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward`

+ How `sysctl` applies the changes to kernel's runtime parameters the moment you run sysctl command? +

  If you `strace` the sysctl command you can see it does it by changing the file under /proc/sys/...

  In the past it was done with sysctl system call, but it was deprecated at some point.


+ How changes to kernel runtime parameters persist? (applied even after reboot to the system for example) +

  There is a service called `systemd-sysctl` that takes the content of /etc/sysctl.conf and applies it. This is how changes persist, even after reboot, when they are written in /etc/sysctl.conf

+ Are the changes you make to kernel parameters in a container, affects also the kernel parameters of the host on which the container runs? +

  No. Containers have their own /proc filesystem so any change to kernel parameters inside a container, are not affecting the host or other containers running on that host.


+ What is SSH? How to check if a Linux server is running SSH? +

  [Wikipedia Definition](https://en.wikipedia.org/wiki/SSH_(Secure_Shell)): "SSH or Secure Shell is a cryptographic network protocol for operating network services securely over an unsecured network."

  [Hostinger.com Definition](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work): "SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet."

  An SSH server will have SSH daemon running. Depends on the distribution, you should be able to check whether the service is running (e.g. systemctl status sshd).

+ Why SSH is considered better than telnet? +

  Telnet also allows you to connect to a remote host but as opposed to SSH where the communication is encrypted, in telnet, the data is sent in clear text, so it doesn't considered to be secured because anyone on the network can see what exactly is sent, including passwords.

+ What is stored in `~/.ssh/known_hosts`? +

  This file contains the list of hosts that you have previously connected to.

+ You try to ssh to a server and you get "Host key verification failed". What does it mean? +

  It means that the key of the remote host was changed and doesn't match the one that stored on the machine (in ~/.ssh/known_hosts).

+ What is the difference between SSH and SSL? +

  | SSH | SSL |
  | ---- | ---- |
  | SSH stands for Secure Shell | SSL stands for Secure Sockets Layer |
  | Cryptographic tunneling protocol and has a username/password authentication system | Does not have a username/password authentication system like SSH |
  | Port 22 | Port 443 |
  | Three Stage Authentication | Two Stage Authentication |
  | Appropriate and Effective for securely executing commands across the internet | best suited for securely transferring critical data like in credit cards and banking |


+ What `ssh-keygen` is used for? +

  It is used to generate SSH keys.
  Example: `ssh-keygen -t rsa -b 4096 -C`

+ What is SSH port forwarding? +

  It is a technique to forward a port from one machine to another.
  Example: `ssh -L 8080:localhost:8080 user@server`

+ What is Globbing? +

  It is a technique to match a pattern against a list of files.
  Example: `ls *.txt`

+ What are wildcards? Can you give an example of how to use them? +

  Wilcards are symbols that can be used to match a pattern against a list of files.
  Example: `ls *.txt`

+ Explain what will `ls [XYZ]` match +

  `ls [XYZ]` will match any file that starts with `X` or `Y` or `Z`

+ Explain what will `ls [^XYZ]` match +

  `ls [^XYZ]` will match any file that doesn't start with `X` or `Y` or `Z`

+ Explain what will `ls [0-5]` match +

  `ls [0-5]` will match any file that starts with `0` or `1` or `2` or `3` or `4` or `5`

+ What each of the following matches: `?`, `*` +

  * The ? matches any single character
  * The * matches zero or more characters

<!-- tabs:start -->

#### **Question**

What do we grep for in each of the following commands?:

- `grep '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}' some_file`
- `grep -E "error|failure" some_file`
- `grep '[0-9]$' some_file`

#### **Answer**

1. An IP address
2. The word "error" or "failure"
3. Lines which end with a number

<!-- tabs:end -->

+ Which line numbers will be printed when running `grep '\baaa\b'` on the following content: `aaa`, `bbb`, `ccc.aaa`, `aaaaaa` +

  `grep '\baaa\b'` will print the line numbers of the lines that contain the word `aaa`

  So it will print:
  - `aaa`
  - `ccc.aaa`

+ What is the difference single and double quotes in Linux? +

  **Single Quotes:**
    Enclosing characters in single quotes (') preserves the literal value of each character within the quotes. A single quote may not occur between single quotes, even when preceded by a backslash.

  **Double Quotes:**
    Enclosing characters in double quotes (") preserves the literal value of all characters within the quotes, with the exception of $, \`, \\, and, when history expansion is enabled, ! The characters $ and \` retain their special meaning within double quotes (see Shell Expansions). The backslash retains its special meaning only when followed by one of the following characters: $, `, ", \, or newline. Within double quotes, backslashes that are followed by one of these characters are removed. Backslashes preceding characters without a special meaning are left unmodified. A double quote may be quoted within double quotes by preceding it with a backslash. If enabled, history expansion will be performed unless an ! appearing in double quotes is escaped using a backslash. The backslash preceding the ! is not removed. The special parameters * and @ have special meaning when in double quotes 


+ What is escaping? What escape character is used for escaping? +

  **Escaping:**
    Escaping is a technique to prevent a command from being interpreted as a shell command.

  **Escape Character:**
    The escape character is used to escape special characters in a command.

  Example: `echo "hello\nworld"`

  The "\n" is used to escape the newline character.


+ What is an exit code? What exit codes are you familiar with? +

  An exit code (or return code) represents the code returned by a child process to its
  parent process.

  0 is an exit code which represents success while anything higher than 1 represents error.
  Each number has different meaning, based on how the application was developed.

  I consider this as a good blog post to read more about it: https://shapeshed.com/unix-exit-codes


+ Tell me everything you know about the Linux boot process +

  Another way to ask this: what happens from the moment you turned on the server until you get a prompt


+ What is GRUB2? +

  GRUB2 is the latest version of GNU GRUB, the GRand Unified Bootloader. A bootloader is the first software program that runs when a computer starts. It is responsible for loading and transferring control to the operating system kernel. In Fedora, the kernel is Linux.

+ What is Secure Boot? +

  Secure Boot is a security feature that prevents the bootloader from being modified by malicious software.

+ What can you find in /boot? +

  /boot is the directory where the bootloader is stored.

+ What's an inode? +

  For each file (and directory) in Linux there is an inode, a data structure which stores meta data related to the file like its size, owner, permissions, etc.

+ Which of the following is not included in inode: Link count, File size, File name, File timestamp? +

  File name (it's part of the directory file)

+ How to check which disks are currently mounted? +

  Run `mount`

+ You run the `mount` command but you get no output. How would you check what mounts you have on your system? +

  `cat /proc/mounts`

+ What is the difference between a soft link and hard link? +

  - Hard link is the same file, using the same inode.
  - Soft link is a shortcut to another file, using a different inode.

+ True or False? You can create an hard link for a directory +

  False

+ True or False? You can create a soft link between different filesystems +

  True

+ True or False? Directories always have by minimum 2 links +

  True.

+ What happens when you delete the original file in case of soft link and hard link? +

  In soft link, the link is deleted and the file is not deleted.
  In hard link, the file is deleted and the link is not deleted. 

+ Can you check what type of filesystem is used in /home? +

  There are many answers for this question. One way is running `df -T`

+ What is a swap partition? What is it used for? +

  A swap partition is a partition that is used to store temporary data.
  It is used to speed up the boot process by caching data that is not needed for the normal boot process.

+ How to create a new empty file, a file with text (without using text editor), a file with given size +

  - `touch file_name`
  - `echo "Hello World" > file_name`
  - `dd if=/dev/zero of=file_name bs=1M count=10`

+ You are trying to create a new file but you get "File system is full". You check with df for free space and you see you used only 20% of the space. What could be the problem? +

  - The file system is full
  - The disk is full
  - The disk is not formatted

+ How would you check what is the size of a certain directory? +

  `du -sh`

+ What is LVM? +

  Logical Volume Manager is a software package that manages storage volumes.
  It is used to create and manage logical volumes.

+ Explain the following in regards to LVM: PV, VG, LV +

  - PV: Physical Volume are the actual storage devices that are used to create logical volumes.
  - VG: Volume Group is a logical grouping of physical volumes.
  - LV: Logical Volume is a logical partition of a volume group.

+ What is NFS? What is it used for? +

  NFS is a network file system. It is used to share files between different computers.

+ What RAID is used for? Can you explain the differences between RAID 0, 1, 5 and 10? +

  RAID is used to achieve data redundancy to reduce data loss and, in a lot of cases, improve performance.
  | RAID 0 | RAID 1 | RAID 5 | RAID 10 |
  |-------:|-------:|-------:|--------:|
  | Blocks Striped, No Mirror, No Parity | Blocks Mirroed, No Stripe, No Parity | Blocks Striped, Distributed Parity | Blocks Mirrored and Striped |
  | Minimum 2 Disks | Minimum 2 Disks | Minimum 3 Disks | Minimum 4 Disks |
  | Excellent performance | Good performance | Good performance | Excellent performance |
  | No Redundancy | Excellent Redundancy | Good Redundancy | Excellent Redundancy |


+ Describe the process of extending a filesystem disk space +
  
  - Create a new file system on the disk:  `$ sudo resize2fs /dev/sda1`
  - Resize the file system: `$ sudo mount -o remount,size={size} /dev/sda1` 
  > Note: The size is in MB. Replace {size} with the size you want.

+ What is lazy umount? +

  Lazy umount is a feature that allows you to unmount a file system without waiting for all the data to be written to disk.

+ What is tmpfs? +

  tmpfs is a RAM based file system. It is used to create temporary files.

+ What is stored in each of the following logs: `/var/log/messages`, `/var/log/boot.log` +
  
  `/var/log/messages` - contains all the messages that are logged by the kernel.
  `/var/log/boot.log` - contains all the messages that are logged by the kernel during the boot process.

+ True or False? both /tmp and /var/tmp cleared upon system boot +

  False. /tmp is cleared upon system boot while /var/tmp is cleared every a couple of days or not cleared at all (depends on distro).


+ How to check what is the current load average? +

  One can use `uptime` or `top`


+ You know how to see the load average, great. but what each part of it means? for example 1.43, 2.34, 2.78 +

  - 1.43 - 1 minute load average (1 minute, 4.3% CPU usage)
  - 2.34 - 5 minute load average (5 minutes, 7.4% CPU usage)
  - 2.78 - 15 minute load average(15 minutes, 10.8% CPU usage)

+ How to check process usage? +

  pidstat

+ How to check disk I/O? +

  `iostat -xz 1`

+ How to check how much free memory a system has? How to check memory consumption by each process? +

  You can use the commands `top` and `free`


+ How to check TCP stats? +

  sar -n TCP,ETCP 1

+ how to list all the processes running in your system? +

  `ps -ef`

+ How to run a process in the background and why to do that in the first place? +

  You can achieve that by specifying & at the end of the command.As to why, since some commands/processes can take a lot of time to finishexecution or run forever, you may want to run them in the background instead of waiting for them to finish before gaining control again in current session.

+ How can you find how much memory a specific process consumes? +

  `
  mem()
  {                                                                                                      
      ps -eo rss,pid,euser,args:100 --sort %mem | grep -v grep | grep -i $@ | awk '{printf $1/1024 "MB"; $1=""; print }'
  }
  `
  [Source](https://stackoverflow.com/questions/3853655/in-linux-how-to-tell-how-much-memory-processes-are-using)


+ What signal is used by default when you run 'kill *process id*'? +
  
  The default signal is SIGTERM (15). This signal kills process gracefully which means it allows it to save current state configuration.

+ What signals are you familiar with? +

  SIGTERM - default signal for terminating a process
  SIGHUP - common usage is for reloading configuration
  SIGKILL - a signal which cannot caught or ignored

  To view all available signals run `kill -l`


+ What `kill 0` does? +

  `kill 0` is used to check if all the processes are still running.

+ What `kill -0 <PID>` does? +

  `kill -0 <PID>` is used to check if a process is still running.

+ What is a trap? +

  A trap is a signal that is sent to a process when it is about to be terminated.

+ Every couple of days, a certain process stops running. How can you look into why it's happening? +

  `ps -ef`

+ What happens when you press ctrl + c? +

  `kill -SIGINT <PID>`

+ What is a Daemon in Linux? +

  A background process. Most of these processes are waiting for requests or set of conditions to be met before actually running anything.
  Some examples: sshd, crond, rpcbind.


+ What are the possible states of a process in Linux? +

  - Running (R)
  - Uninterruptible Sleep (D) - The process is waiting for I/O
  - Interruptible Sleep (S)
  - Stopped (T)
  - Dead (x)
  - Zombie (z)

+ How do you kill a process in D state? +

  `kill -9 <PID>`

+ What is a zombie process? +

  A process which has finished to run but has not exited.

  One reason it happens is when a parent process is programmed incorrectly. Every parent process should execute wait() to get the exit code from the child process which finished to run. But when the parent isn't checking for the child exit code, the child process can still exists although it finished to run.

+ How to get rid of zombie processes? +

  You can't kill a zombie process the regular way with `kill -9` for example as it's already dead.

  One way to kill zombie process is by sending SIGCHLD to the parent process telling it to terminate its child processes. This might not work if the parent process wasn't programmed properly. The invocation is `kill -s SIGCHLD [parent_pid]`

  You can also try closing/terminating the parent process. This will make the zombie process a child of init (1) which does periodic cleanups and will at some point clean up the zombie process.

+ How to find all the Processes executed/owned by a certain user, Process which are Java processes, Zombie Processes +

  - To find all the processes executed by a certain user: `ps -u <user> -o pid,ppid,cmd`
  - To find all the Java processes: `ps -u <user> -o pid,ppid,cmd | grep java`
  - To find all the zombie processes: `ps -u <user> -o pid,ppid,cmd | grep z`

+ What is the init process? +
  
  It is the first process executed by the kernel during the booting of a system. It is a daemon process which runs till the system is shutdown. That is why, it is the parent of all the processes

+ Can you describe how processes are being created? +

  Processes are created by the kernel. The kernel creates a new process when a process calls exec() or fork() or when a process calls execve() or vfork().

+ How to change the priority of a process? Why would you want to do that? +

  You can use the `nice` command to change the priority of a process. We want to do that because we want to give the process a higher priority than the default priority.

+ Can you explain how network process/connection is established and how it's terminated?> +

  - TCP/IP connection is established when a process calls connect() or accept()
  - TCP/IP connection is terminated when a process calls close()

+ What `strace` does? What about `ltrace`? +

  Both ltrace and strace give you similar information, but with an important difference: **strace** intercepts system calls make by the glibc and other libraries directly into the Linux Kernel. **ltrace** intercepts library calls and system calls made by your application to C libraries such as the glibc.

+ Find all the files which end with '.yml' and replace the number 1 in 2 in each file +

  find /some_dir -iname \*.yml -print0 | xargs -0 -r sed -i "s/1/2/g"


+ You run ls and you get "/lib/ld-linux-armhf.so.3 no such file or directory". What is the problem? +

  The ls executable is built for an incompatible architecture.

+ How would you split a 50 lines file into 2 files of 25 lines each? +

  You can use the `split` command this way: `split -l 25 some_file`


+ What is a file descriptor? What file descriptors are you familiar with? +
  
  Kerberos
  File descriptor, also known as file handler, is a unique number which identifies an open file in the operating system.

  In Linux (and Unix) the first three file descriptors are:

  * 0 - the default data stream for input
  * 1 - the default data stream for output
  * 2 - the default data stream for output related to errors

+ What is NTP? What is it used for? +

  NTP is a network time protocol which is used to synchronize the time of the computer with the time of the internet.

+ Explain Kernel OOM +

  Kernel OOM is a kernel panic which is caused by the kernel not being able to allocate memory to a process.