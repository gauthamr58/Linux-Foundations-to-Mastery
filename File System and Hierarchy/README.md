Linux File System
=================

## 📌 What is a Filesystem?

The Linux file system is the method that the operating system uses to control how data is stored, organized, and retrieved on a storage device such as a hard disk, SSD, or USB drive.

**Key goals:**

* Locate and retrieve data efficiently
* Keep data organized and secure
* Track metadata (permissions, timestamps, ownership)
* Prevent corruption (journaling)

---

## 🧩 Components of a Linux Filesystem

**1. Superblock**

* Contains global metadata about the filesystem
* Located at a fixed position on disk
* Stores:

  * Filesystem type (ext4, xfs, btrfs…)
  * Total blocks, free blocks
  * Block size
  * Mount info
  * State (clean or needs fsck)

**2. Inodes (Index Nodes)**

* Every file/directory has an inode
* Stores metadata about the file **except the name**

  * File type (regular, directory, symlink…)
  * Permissions (rwx)
  * UID, GID
  * Size, timestamps (atime, mtime, ctime)
  * Pointers to data blocks

**3. Data Blocks**

* Store the **actual contents** of the file
* Inodes point to these blocks

**4. Directory Entries**

* Special files that map **filenames → inode numbers**

---

# Linux File System Hierarchy
Linux follows the **Filesystem Hierarchy Standard (FHS)**, which organizes files in a **tree starting at / (root)**.

## 📁 Important Directories and Their Purpose

| Directory        | Description                                              |
| ---------------- | -------------------------------------------------------- |
| `/`              | Root directory, starting point of all filesystems        |
| `/bin`           | Essential user binaries (ls, cp, mv, cat)                |
| `/sbin`          | Essential system binaries (fsck, reboot)                 |
| `/boot`          | Bootloader files, kernel (`vmlinuz`), initrd             |
| `/dev`           | Device files (disks, terminals, etc.)                    |
| `/etc`           | System configuration files (passwd, fstab, sshd\_config) |
| `/home`          | Home directories for normal users                        |
| `/root`          | Home directory of root user                              |
| `/lib`, `/lib64` | Shared libraries and kernel modules                      |
| `/media`         | Mount points for removable media (USB, CD)               |
| `/mnt`           | Temporary mount point for admins                         |
| `/opt`           | Optional third-party application software                |
| `/srv`           | Data served by services (like web or ftp)                |
| `/tmp`           | Temporary files, cleared on reboot                       |
| `/usr`           | User applications, binaries, libraries, documentation    |
| `/var`           | Variable data (logs, mail, spool, cache)                 |
| `/proc`          | Virtual FS with process/kernel info                      |
| `/sys`           | Virtual FS with hardware/kernel info                     |
| `/run`           | Runtime transient data (PID files, sockets)              |

---

## 🌳 Linux Directory Tree Example 🗂️

  ```plaintext

/                     
├── bin              
├── boot             
├── dev             
├── etc              
├── home             
│   ├── gautham        
│   └── user2         
├── lib              
├── lib64            
├── media           
├── mnt              
├── opt              
├── proc            
├── root             
├── run              
├── sbin             
├── srv              
├── sys              
├── tmp              
├── usr              
│   ├── bin          
│   ├── lib          
│   ├── local        
│   └── share        
└── var              
    ├── log         
    ├── spool        
    └── cache        

```

---


## 💽 Common Linux Filesystem Types

| File system          | Description                                             |
| -------------------  |---------------------------------------------------------|
|   **ext4**           | Default on many distros,large file support,journaling   |
| **XFS**              | High-performance, great for large files                 |
| **Btrfs**            | Modern, snapshots, checksumming, pooling                |
| **F2FS**             | Optimized for flash storage                             |
| **vfat/exFAT**       | Cross platform, improved version of FAT32               |
| **tmpfs**            | RAM-based, temporary, runtime data                      |
| **procfs (`/proc`)** | Virtual, exposes process/kernel info                    |
| **sysfs (`/sys`)**   | Virtual, exposes device/kernel data                     |

---

## ⚡ Journaling

* Modern filesystems (ext4, xfs, btrfs) use **journaling**: technique used to prevent data corruption if your system crashes (power cut, kernel panic, etc.).

  * Changes are first written to a journal
  * After a crash, journal is replayed to recover
* Improves reliability and consistency

---

## ⚙️ Mounting Filesystems

* Linux uses a **single-rooted tree** structure.
* A **mount point** is a directory where another filesystem is attached.
* Mounting links physical devices into this tree.

```bash
mount /dev/sdb1 /mnt
umount /mnt
df -h      # check mounted filesystems
lsblk      # list block devices
```