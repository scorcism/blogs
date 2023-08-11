The most basic level is hardware, which includes our CPU, memory, hard disks, networking ports, etc. The physical layer computes what our machine is doing.

The next level is the **kernel**, which handles process and memory management, device communication, system calls, sets up our filesystem, etc. 

The kernel's job is to talk to the hardware to make sure it does what we want our processes to do.

And the level that you are familiar with is the user space, the user space includes the shell, the programs that you run, the graphics, etc.

In **kernel mode**, the kernel has complete access to the hardware, it controls everything.

In user space mode, there is a very small amount of safe memory and CPU that you are allowed to access.

When we want to do anything that involves hardware, reading data from our disks, writing data to our disks, controlling our network, etc, it is all done in kernel mode.

**Why is this necessary?**

Imagine if your machine was infected with spyware, you wouldn't want it to be able to have direct access to your system's hardware. It can access all your data, your webcam, etc. and that's no good.

**The Protection Rings:**
![protection ring](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Priv_rings.svg/300px-Priv_rings.svg.png)

The innermost ring corresponds to the highest privilege level.

There are two main levels or modes in an x86 computer architecture.

**Ring #3** is the privilege that user-mode applications run in,

**Ring #0** is the privilege that the kernel runs in. Ring #0 can execute any system instruction and is given full trust.

**how are we able to write anything to our hardware? Won't we always be in a different mode than the kernel?**

The answer is with system calls, system calls allow us to perform a privileged instruction in kernel mode and then switch back to user mode.
