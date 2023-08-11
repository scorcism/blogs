Remember how our filesystem is comprised of all our actual files and a database that manages these files? 

The database is known as the **inode table**.

## **What is an inode?**  

**An inode (index node) is an entry in this table and there is one for every file.**

It describes everything about the file, such as:

```
File type - regular file, directory, character device, etc  
Owner  
Group  
Access permissions  
Timestamps - mtime (time of last file modification), ctime (time of last attribute change), atime (time of last access)  
Number of hardlinks to the file  
Size of the file  
Number of blocks allocated to the file  
Pointers to the data blocks of the file - most important!
```
**Inodes store everything about the file, except the filename and the file itself!**

## **How do inodes locate files?**

We know our data is out there on the disk somewhere, unfortunately, it probably wasn't stored sequentially, so we have to use inodes.

Inodes point to the actual data blocks of your files.

In a typical filesystem (not all work the same), each inode contains 15 pointers, and the first 12 pointers point directly to the data blocks. The 13th pointer points to a block containing pointers to more blocks, the 14th pointer points to another nested block of pointers, and the 15th pointer points yet again to another block of pointers!

Confusing, I know!

The reason this is done this way is to keep the inode structure the same for every inode but be able to reference files of different sizes. If you had a small file, you could find it quicker with the first 12 direct pointers, larger files can be found with the nests of pointers.

Either way, the structure of the inode is the same

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/) and [GitHub](https://github.com/scorcism).
