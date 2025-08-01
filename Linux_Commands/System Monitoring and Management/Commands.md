

## 1.Top

 top command provides real-time information about running processes, CPU, memory, and other system resources.

input

```bash
 top
```
Output

```text
 top - 14:22:37 up 1 day, 12:34,  0 users,  load average: 0.00, 0.01, 0.05
Tasks: 101 total,   1 running,  99 sleeping,   1 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   1992.0 total,   1537.0 free,    235.0 used,    220.0 buff/cache
MiB Swap:   2047.9 total,   2047.9 free,      0.0 used.   1555.3 avail Mem

   PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
     1 root      20   0    8788   5688   3828 S   0.0   0.3   0:02.14 systemd
     2 root      20   0       0      0      0 S   0.0   0.0   0:00.01 kthreadd
     3 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
     4 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp
     5 root      20   0       0      0      0 I   0.0   0.0   0:00.00 slub_flushwq
```  

You can customize the top command's output by pressing various keys, such as:

h: Display the help menu

1: Toggle between per-CPU and aggregate CPU utilization

f: Manage the columns displayed

o: Customize the sort order

u: Filter processes by a specific user

Some of the commonly used options include:

-d: Set the delay between updates (default is 3 seconds)

-n: Specify the number of iterations (default is unlimited)

-p: Monitor specific process IDs

-u: Display processes owned by a specific user

-o: Sort the process list by a specific column

```bash
top -o %MEM -n 5
```
to display the top 5 processes sorted by memory usage, you can run
  
## 2.Ps

ps command is a fundamental tool for system administrators and developers, providing detailed information about the processes currently running, including their process ID, user, CPU and memory usage, and more. 

Input

```bash
  ps
```
Output

```text
    PID TTY          TIME CMD
 1234 pts/0    00:00:00 bash
 5678 pts/0    00:00:00 ps
```
The -e option displays all processes

The -f option provides a full-format listing, including the user ID (UID), process ID (PID), parent process ID (PPID), CPU usage (C), start time (STIME), terminal (TTY), CPU time (TIME), and the command (CMD).

The -u or --user  allows you to display processes owned by a specific user.

```bash
  ps -u labex
```
to view the CPU and memory usage of all processes, you can use the ps command with the -o option to customize the output:

```bash
ps -eo pid,user,%cpu,%mem,cmd
```

  ## 3.Free
  free command is a useful tool for monitoring the system's memory usage, including both physical memory (RAM) and swap space.


Input
  
```bash
free
```
Output

```text
 total        used        free      shared  buff/cache   available
Mem:        2048236     1023936      368584       72156      655716     1546700
Swap:       1048572           0     1048572
```
  You can also use the following options with the free command to customize the output:

-h: Display the memory size in human-readable format (e.g., MB, GB)

-m: Display the memory size in megabytes

-g: Display the memory size in gigabytes

-t: Display the total for all memory types

## 4.Uptime

  uptime command displays the current time, how long the system has been running, the number of users currently logged in, and the system load averages for the past 1, 5, and 15 minutes.
  
Input
```bash
uptime
```
Output

```text
 15:42:17 up 1 day, 12:34,  0 users,  load average: 0.00, 0.01, 0.05
```
 
  ## 5.Vmstat
  
   vmstat command provides a detailed overview of various system resources, including CPU, memory, and disk I/O.
  Input
  
```bash
vmstat
```
Output

```text
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 1877028  16308 1359812    0    0     0     0    0    0  0  0 100  0  0
```
  

 ## 6.htop

 htop command to monitor and manage your system processes.

 ##  7. Watch
  watch command in Linux, which allows you to repeatedly execute a command and monitor its output.

The watch command is a powerful tool for system monitoring and management. It can be used to track changes in system processes, file modifications, and other real-time events.
  watch [options] <command>

-n, --interval <seconds>: Set the update interval for the command execution (default is 2 seconds).

-d, --difference: Highlight the differences between successive updates.

-t, --no-title: Hide the header showing the current time and the command being executed.
  
