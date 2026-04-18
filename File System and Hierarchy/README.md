Linux File System
=================

## 📌 What is a Filesystem?

The Linux file system is the method that the operating system uses to control how data is stored, organized, and retrieved on a storage device such as a hard disk, SSD, or USB drive.

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

| File system        | Description                                                |
| -------------------|----------------------------------------------------------  |
|   **ext4**         | Default on many distros,large file support,journaling      |
|   **XFS**          |                                                            |