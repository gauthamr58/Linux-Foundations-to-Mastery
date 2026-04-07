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
      
      *  Creates, Schedules, and terminates processes.
      * Decides which process runs on the CPU and for how long.
      * Handles inter-process communication .

 2. **Memory Management**

      * Allocates and deallocates RAM to processes.
      * Keeps processes isolated so they don’t overwrite each other’s memory.
      * Manages paging, swapping (moving memory to disk), and the page cache

 3. **Device Management**

      * Provides drivers and handles communication between hardware devices (disk, network, keyboard, etc.) and software.

 4. **File System Management**

      * Manages files on storage (reading, writing, permissions, directory structure).

 5. **System Calls / Interface**

      * Provides an API (system calls) for user programs to request services from the OS.

 6. **Networking**

      * Implements the full TCP/IP stack
      * Manages network interfaces, routing, firewalling .
  
---

## 🧩 Types of Kernels

| Type            | Description                                                      | Examples          |
| --------------- | ---------------------------------------------------------------- | ----------------- |
| **Monolithic**  | All services run in a single large block of code in kernel space | Linux, Unix       |
| **Microkernel** | Minimal core in kernel space; most services run in user space    | Minix, QNX        |
| **Hybrid**      | Mix of both monolithic and microkernel designs                   | Windows NT, macOS |
| **Exokernel**   | Very small kernel giving apps direct hardware access             | Experimental OSs  |

---

## 📌 So, to summarize:

| Term                              | Description                                                                            |
| --------------------------------- | -------------------------------------------------------------------------------------- |
| **Linux (Kernel)**                | The core of the OS, manages hardware, processes, memory.                               |
| **Linux-based OS (Distribution)** | A complete operating system built using the Linux kernel + GNU tools + other software. |

**Example distributions:** Ubuntu, Fedora, Debian, Arch, RHEL, openSUSE

---

## 📦 Structure of a Linux-based OS

```
+-----------------------------------+
|  User Applications                |
+-----------------------------------+
|  GNU Utilities / System Libraries |
+-----------------------------------+
|  Linux Kernel                     |
+-----------------------------------+
|  Hardware (CPU, RAM, Disk, etc.)  |
+-----------------------------------+
```

---

✅ **Bottom line:**

* **Linux = kernel.**
* **Ubuntu/Fedora/Debian/etc. = full OS (built on Linux kernel).**

---

## ✅ Advantages of Linux

### 1. **Open Source**

* Source code is publicly available.
* Anyone can view, modify, and redistribute it.
* Encourages learning and innovation.

---

### 2. **Free of Cost**

* Most Linux distributions are completely free.
* No license fees or activation keys required.

---

### 3. **High Security**

* Strong user permission model and file ownership system.
* Regular security updates from the community.
* Far less prone to viruses and malware compared to Windows.

---

### 4. **Stability and Reliability**

* Rarely crashes or slows down over time.
* Can run for months or even years without reboot.
* Ideal for servers and critical systems.

---

### 5. **Lightweight and Efficient**

* Can run on old or low-spec hardware.
* Many lightweight distributions (like Lubuntu, Puppy Linux) use very little memory.

---

### 6. **Highly Customizable**

* Everything from the kernel to the desktop environment can be modified.
* Users can choose window managers, themes, shells, etc.

---

### 7. **Excellent Community Support**

* Large community forums, documentation, and tutorials.
* Quick help available for almost every issue.

---

### 8. **Variety of Distributions**

* Many Linux distributions available for different needs (Ubuntu for beginners, CentOS/RHEL for servers, Kali for security, Arch for advanced users).

---

### 9. **Better Performance and Resource Usage**

* Efficient use of CPU and RAM.
* No bloatware or heavy background processes by default.

---

### 10. **Ideal for Developers and DevOps**

* Comes with powerful command-line tools.
* Native support for scripting, programming languages, and servers.