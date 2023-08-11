
# /dev directory

When you connect a device to your machine, it generally needs a device driver to function properly. 

You can interact with device drivers through device files or device nodes, these are special files that look like regular files. 

Since these device files are just like regular files, you can use programs such as ls, cat, etc to interact with them. These device files are generally stored in the /dev directory. 

Go ahead and ls the /dev directory on your system, you'll see a large amount of devices files that are on your system.

ls /dev

![ls /dev](https://i.imgur.com/WJvBDyB.png)

c - character -> These devices transfer data, but one a character at a time.

b - block -> These devices transfer data, but in large fixed-sized blocks.

p - pipe -> Named pipes allow two or more processes to communicate with each other, these are similar to character devices, but instead of having output sent to a device, it's sent to another process.

s - socket -> Socket devices facilitate communication between processes, similar to pipe devices but they can communicate with many processes at once.

## Device Names

If you have any sort of mass storage on your machine, chances are it is using the SCSI (pronounced "scuzzy") protocol. 

SCSI stands for Small Computer System Interface, it is a protocol used for allow communication between disks, printers, scanners and other peripherals to your system. 

You may have heard of SCSI devices which aren't actually in use in modern systems, however our Linux systems correspond SCSI disks with hard disk drives in /dev. 

They are represented by a prefix of sd (SCSI disk):

Common SCSI device files:

/dev/sda - First hard disk
/dev/sdb - Second hard disk
/dev/sda3 - Third partition on the first hard disk

**Listing USB Devices**
```bash
lsusb
```

**Listing PCI Devices**
```bash
lspci
```

**Listing SCSI Devices**
```bash
lsscsi
```

## dd

The dd tool is super useful for converting and copying data. 
It reads input from a file or data stream and writes it to a file or data stream.

Consider the following command:

$ dd if=/home/pete/backup.img of=/dev/sdb bs=1024 
This command is copying the contents of backup.img to /dev/sdb. 

It will copy the data in blocks of 1024 bytes until there is no more data to be copied.
eg ls -alshr
