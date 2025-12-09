This is one of the tools that I use on a daily basis, and though sometimes I have to Google what these columns mean…
So I thought of creating some notes, but then I am here writing this blog with the help of ~AI, funny :), but it is what it is.
I won’t be going into minor things, as you are smart enough for that…

## Headers

### PID

* ID of the process, like a unique identifier.

### USER

* Which user started the process.
* **root** – system-level
* **daemon, syslog, etc** – service users

### PRI

* Priority.
* Lower number = higher priority.
* Kernel decides who gets CPU time first.

### NI

* Nice value.
* User-assigned priority tweak.
* Range: -20 (very important) to +19 (not so much).
* This exists to help us give priority to the process.

### VIRT

* Virtual Memory.
* Total memory the process can use.
* Includes swapped memory, shared libs, etc.
* In the image above, the numbers are in KB (kilobytes).

### RES

* Resident Memory.
* Actual RAM being used **right now**.
* This is the important one.
* In the image above, the numbers are in KB (kilobytes).

### SHR

* Shared Memory.
* Memory shared with other processes:

  * Shared libs
  * Common system libs
* In the image above, the numbers are in KB (kilobytes).
  So this means **XX KB** of the process’s memory can be shared with others.

### S

* What the process is doing now:

  * **S** → Sleeping
  * **R** → Running
  * **D** → Uninterruptible sleep
  * **Z** → Zombie
* We mostly see **S** because most processes wait for input.

### CPU%

* How much of the CPU the process is using right now.

### MEM%

* How much RAM it uses relative to total system RAM.

### TIME+

* Total CPU time a process has consumed since it started.

### Command

* The actual program that launched the process.

## Why do we have different colors in the USER column?

This comes from `htop` itself.

1. **Green**
   * Normal user processes
   * Custom Python scripts, CLI scripts, etc.

2. **Blue**
   * Low-priority processes

3. **Red/Orange**
   * Kernel threads / High-priority tasks

4. **Cyan / Light Blue**
   * Threads inside a process (e.g., Python worker threads)

5. **Purple**
   * System daemons

6. **Bold Green**
   * Running processes

7. **Dark Gray / Dim**
   * Idle or sleeping processes taking almost 0 CPU