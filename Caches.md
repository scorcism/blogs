
## What are chaches ?

Caching is like having a quick-access memory for information, so you don't have to fetch it from the original source every time you need it. 
  
It's like keeping your favourite apps on the home screen so you don't have to scroll or search for them.

There are different types of caches that help make things faster in different situations:

1. **Hardware Level Caches**
2. **OS Level Caches** 
3. **Network Level Caches**

Let's Deep dive into each of them

### Hardware Level Caches

Hardware-level caches are an essential component of modern computer architectures, designed to improve data access speeds and overall system performance. 

Here are the primary types of hardware-level caches commonly found in computers:

1.  **L1 Cache (Level 1 Cache):**
    
    -   Located closest to the CPU cores.
    -   Divided into separate instruction cache (L1i) and data cache (L1d).
    -   Provides extremely fast access to frequently used instructions and data.
2.  **L2 Cache (Level 2 Cache):**
    
    -   Positioned between L1 cache and main memory.
    -   Larger in size compared to L1 cache.
    -   Helps reduce memory latency by storing additional data.
3.  **L3 Cache (Level 3 Cache):**
    
    -   Shared among multiple CPU cores.
    -   Larger capacity than L2 cache.
    -   Enhances data sharing and synchronization between cores.

4. **Translation Lookaside Buffer (TLB) Cache:**

	-   Facilitates virtual-to-physical memory address translation.
	-   Accelerates memory access by storing frequently used address translations.
	- Store virtual physical address.
5.  **Disk Controller Cache:**
    
    -   Found in storage devices like hard drives and SSDs.
    -   Temporarily stores read and write operations to enhance I/O performance.
6.  **GPU Cache:**
    
    -   Specific to graphics processing units (GPUs).
    -   Stores texture data and intermediate calculations for faster graphics rendering.
7.  **Memory Cache:**
    
    -   Temporarily stores frequently accessed data from main memory (RAM).
    -   Reduces memory access latency and enhances system responsiveness.
8.  **Disk Cache:**
    
    -   Temporarily stores frequently accessed data from disk drives.
    -   Improves read and write performance by minimizing disk access.

There are many others types of harware caches but these are the imp ones.

> Now moving to **OS Level Caches**

### OS Level Caches
Operating system-level caches play a crucial role in enhancing overall system performance and responsiveness by storing frequently accessed data and instructions. 

Here are some common types of OS-level caches:

1.  **File System Cache:**
    
    -   Caches recently accessed file data in memory.
    -   Improves file read and write operations by reducing disk access.
    -   Enhances overall file system performance.
    
2.  **Memory Cache (Page Cache):**
    
    -   Caches portions of the main memory (RAM) for faster data retrieval.
    -   Reduces the need to access data directly from slower storage devices.

3.  **Directory Cache (Dentry Cache):**
    
    -   Stores recently accessed directory and file entry data.
    -   Speeds up directory navigation and file path resolution.
4.  **Inode Cache:**
    
    -   Caches metadata of recently accessed files, such as permissions and timestamps.
    -   Improves file system navigation and reduces metadata lookups.
5.  **Translation Lookaside Buffer (TLB):**
    
    -   Caches virtual-to-physical memory address translations.
    -   Accelerates memory access by avoiding repeated translation table lookups.
     
6.  **Kernel Caches:**
    
    -   Caches portions of the kernel code and data structures.
    -   Enhances system responsiveness and reduces kernel access latency.
7.  **DNS Cache:**
    
	-   Stores recently resolved domain names and their corresponding IP addresses.
	  -   Reduces the need for repeated DNS lookups, improving network performance.
    
8.  **IPC (Inter-Process Communication) Caches:**
    
	   -   Caches communication-related data between processes.
	   -   Enhances efficiency in data sharing and communication.
 
	There are other OS Level caches such as **Metadata Cache** ( which store metadata about file, directories and resouces ), **Package Caches** ( Caches software package information and installation files ), **Executable Caches** (Stores copies of recently executed programs or executable files).

> Now moving to **Network Level Cache**

### Network Level Caches

Network caching plays a crucial role in optimizing data transmission and reducing latency in network communication. 

Here are some common types of network caches:

1.  **Web Browser Cache:**
    
    -   Caches web page resources (HTML, CSS, JavaScript, images) locally.
    -   Speeds up subsequent visits to websites by avoiding repeated downloads.
2.  **Content Delivery Network (CDN) Cache:**
    
    -   Caches copies of web content on distributed servers closer to users.
    -   Improves content delivery and reduces latency for geographically dispersed users.
3.  **Proxy Server Cache:**
    
    -   Caches frequently requested web pages and resources on a proxy server.
    -   Reduces the load on the origin server and improves response times.
4.  **Gateway Cache:**
    
    -   Caches data between a client and a remote server.
    -   Enhances data transmission efficiency and reduces network congestion.
5.  **DNS Cache:**
    
    -   Stores recently resolved domain names and their corresponding IP addresses.
    -   Speeds up domain name resolution and reduces DNS lookup times.
6.  **Router Cache:**
    
    -   Caches routing information and network paths for faster data forwarding.
    -   Improves router performance and reduces network delays.
7.  **Streaming Cache:**
    
    -   Caches streaming media content, such as videos and audio.
    -   Reduces buffering and improves playback quality for online streaming services.
8.  **Database Query Cache:**
    
    -   Caches frequently executed database queries and their results.
    -   Accelerates database query response times and reduces database load.
9.  **Message Broker Cache:**
    
    -   Caches frequently published or subscribed messages in a message broker.
    -   Optimizes message delivery and reduces redundant data transmission.
10.  **API Cache:**
    
	   -   Caches responses from API endpoints to reduce redundant API requests.
	   -   Enhances API performance and conserves network resources.
	   
13.  **Load Balancer Cache:**
    
	   -   Caches data on load balancers to improve distribution efficiency.
	   -   Reduces the load on backend servers and enhances request handling.
	   
14.  **Gateway Cache:**
    
	   -   Caches data between different network segments or protocols.
	   -   Enhances data transfer between heterogeneous networks.


  
I know this is a lot, but for learning, you can remember the gist of that, and these are very simple to remember, but the cache is that you must remember the name, so to make the other lines.

---

If you have interest in **open source** you can contribue to my projects 
1. [One Liner](https://github.com/asPerReqirements/oneliner)
2. [Click Counter](https://github.com/asPerReqirements/click-counter)

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**






