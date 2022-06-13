```
title = "Partitioning a Disk for a Filesystem with fdisk"
date = "2022-06-07"
author = "deamonctl@mcp"
```

# Partition a disk with fdisk
man pages (short for manual page) are a form of software documentation usually found on a Unix or Unix-like operating systems. 
```bash
# man fdisk 

FDISK(8)                                    System Administration                                    FDISK(8)

NAME
       fdisk - manipulate disk partition table

SYNOPSIS
       fdisk [options] device

       fdisk -l [device...]

DESCRIPTION
       fdisk  is  a  dialog-driven program for creation and manipulation of partition tables.  It understands
       GPT, MBR, Sun, SGI and BSD partition tables.
       .
       .
```

```bash
# fdisk -l

Disk /dev/nvme0n1: 476.94 GiB, 512110190592 bytes, 1000215216 sectors
Disk model: INTEL SSDPEKKW512G7                     
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: <redacted>

Device           Start        End   Sectors   Size Type
/dev/nvme0n1p1    2048    1230847   1228800   600M EFI System
/dev/nvme0n1p2 1230848    3327999   2097152     1G Linux filesystem
/dev/nvme0n1p3 3328000 1000214527 996886528 475.4G Linux filesystem


Disk /dev/zram0: 8 GiB, 8589934592 bytes, 2097152 sectors
Units: sectors of 1 * 4096 = 4096 bytes
Sector size (logical/physical): 4096 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes

```


## Disk, Partitions, and Filesystems. 
### Disk
todo

### Partition
- [disk partitioning](https://en.wikipedia.org/wiki/Disk_partitioning)

### Filesystem
A filesystem is the methods and data structures that an operating system uses to keep track of files on a disk or partition. that is, the way the files are organized on the disk. 

The difference between a disk and partition and the filesystem it contains are important. A few programs operate directly on the raw sections of a disk or partition; if there is an existing file system there it will be destroyed or seriously corrupted. Most programs operate on a filesystem, and therefore won't work on a partition that doesn't contain one.

The central concepts of UNIX filesystems types are as follows:
- superblock: contains information about the filesystem as a whole, such as its size (exact information depends on the filesystem)
- inode: contains all information about a file, excepts its name. The name is stored in directory, together with the number of the inode. A directory entry consists of a filename and the number of the inode which represents the file. The inode contains the numbers of several data blocks
- datablock: stores the data in the file. There is space only for a few data block numbers in the inode, however, and if more are needed, more space for pointers to the data blocks is allocated dynamically. 
- directory block:
- indirectiion block: 

#### types of filesystems
- [ext4](https://en.wikipedia.org/wiki/Ext4): fourth extended filesystem is a journaling filesystem for Linux, developed as the successor to ext3. 

#### Resizing the Parition 
