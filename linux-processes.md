Lets us understand, what the output is when we run `ps` command
```bash
ps
```
![ps output](https://imgur.com/eapEquZ.png)

we have,
**PID**: Process ID
**TTY**: Controlling terminal associated with the process
**STAT**: Process status code
**TIME**: Total CPU usage time
**CMD**: Name of executable/command

```bash
ps aux
```
![ps aux command](https://imgur.com/wk9WiE1.png)

The `a`	 displays all processes running, including the ones being ran by other users. 
The `u` shows more details about the processes. 
and finally the `x` lists all processes

**USER**: The effeictive user
**PID**: Process ID
**%CPU**: CPU time used divided by the time the process has been running
**%MEM**: Ratio of the process's resident set size to the physical memory on the machine
**VSZ**: Virtual memory usage of the entire process
**RSS**: Resident set size, the non-swapped physical memory that a task has used
**TTY**: Controlling terminal associated with the process (TTY is the terminal that executed the command.)
**STAT**: Process status code
**START**: Start time of the process
**TIME**: Total CPU usage time
**COMMAND**: Name of executable/command

## Process states

In the **STAT** column, you'll see lots of values. A linux process can be in a number of different states.

 The most common state codes are:

**R**: running or runnable, it is just waiting for the CPU to process it
**S**: Interruptible sleep, waiting for an event to complete, such as input from the terminal
**D**: Uninterruptible sleep, processes that cannot be killed or interrupted with a signal, usually to make them go away you have to reboot or fix the issue
**Z**: Zombie, we discussed in a previous lesson that zombies are terminated processes that are waiting to have their statuses collected
**T**: Stopped, a process that has been suspended/stopped

## /proc filesystem
Remember everything in Linux is a file, even **processes**. Process information is stored in a special filesystem known as the **/proc** filesystem.
```bash
ls /proc
```
![proc file system](https://imgur.com/ORevY3K.png)
You should see multiple values in here, there are sub-directories for every PID. 
If you looked at a PID in the ps output, you would be able to find it in the /proc directory.

**Inside the process**

```bash
cat /proc/1/status
```

![](https://imgur.com/GcXcrPb.png)

You should see process state information and well as more detailed information.

**The /proc directory is how the kernel is views the system, so there is a lot more information here than what you would see in ps**.


If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/) and [GitHub](https://github.com/scorcism).
