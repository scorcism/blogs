The Linux boot process can be broken down into 4 simple stages:

1) BIOS


The BIOS (stands for "Basic Input/Output System") initializes the hardware and makes sure with a Power-on self-test (POST) that all the hardware is good to go. The main job of the BIOS is to load up the bootloader.

2) Bootloader


The bootloader loads the kernel into memory and then starts the kernel with a set of kernel parameters. One of the most common bootloaders is GRUB, which is a universal Linux standard.

3) Kernel


When the kernel is loaded, it immediately initializes devices and memory. The main job of the kernel is to load up the init process.

4) Init


Remember the init process is the first process that gets started, init starts and stops essential service process on the system. There are three major implementations of init in Linux distributions. We will go over them briefly and then dive into them in another course.

There it is, the (very) simple explanation of the Linux boot process.

---

🙂 If the article helps you, leave a like, follow, or anything.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/) and [GitHub](https://github.com/scorcism).
