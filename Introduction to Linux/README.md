# 🐧 What is Linux?

*  **Linux is technically a **kernel** — not a full operating system.**
* The **Linux kernel** is the **core program** that talks directly to the hardware and manages CPU, Memory, devices, and system calls. 
* Created by Linus Torvalds in 1991

However..

* When people say **"Linux" in everyday usage** they usaually mean a **Linux-based-operating system** (like Ubuntu, Debian, centOS, RHEL, Kali, Arch etc.).
* These are called **Linux distributions (distros)** and they include:
  
  * **The linux-kernel** 
  * **GNU sysytem utilities and libraries** (shell, compiler, file tools, etc.)
  * Package managers
  * Desktop environments or srvers
  * Other software

## 🧠What is a Kernel?
<img src="https://github.com/gauthamr58/Linux-Foundations-to-Mastery/blob/main/images/kernel.webp" alt="Banner" />

* The **kernel is the core part of an operating system (OS)** It acts as a **bridge between hardware and software**, managinh how the applications use computers resources.

You can think of it as the **"brain" or "heart" of the OS.**

---

## ⚙️ Main Responsibilities of a Kernel

 1. **Process Management**
      
      * The kernel is responsible for creating, executing, and terminating processes (running programs).

      * Scheduling: Since a CPU can only do a few things at once, the kernel uses a     scheduler to decide which process gets to use the CPU and for how long.

      * Inter-Process Communication (IPC): it provides the "pipes" and signals that allow different programs to talk to each other.

 2. **Memory Management**

      * Allocates and deallocates RAM to processes.
      * Keeps processes isolated so they don’t overwrite each other’s memory.
      * Manages paging, swapping (moving memory to disk if run out of RAM), and the page cache

 3. **Device Management**

      * Provides drivers and handles communication between hardware devices (disk, network, keyboard, etc.) and software.

 4. **File System Management**

      * Manages files on storage (reading, writing, permissions, directory structure).

 5. **System Calls / Interface**

      * Provides an API (system calls) for user programs to request services from the OS.

 6. **Networking**

      * manages the entire Network Stack. It handles incoming and outgoing data packets, routing them to the correct application, and managing protocols like TCP/IP and UDP.