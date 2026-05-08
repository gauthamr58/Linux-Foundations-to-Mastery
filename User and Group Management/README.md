
# 🧑‍💻 Linux User Management – Core Commands

Managing users is a key part of system administration.
These commands help you **view user info, create users, and manage their credentials**.

---

## 1. 🧠 `whoami`

**Purpose:** Shows the **currently logged-in username.** 

**Usage:**

```bash
whoami
```

**Example Output:**

```
user
```

✅ Useful in scripts to know which user is running them.

---

## 2. 🪪 `id`

**Purpose:** Displays the **user ID (UID), group ID (GID), and group memberships** of a user.

**Usage**

```bash
id          # current user
id username # specific user
```

**Example Output:**

```
uid=1000(ubuntu) gid=1000(ubuntu) groups=1000(ubuntu),4(adm),24(cdrom),27(sudo),30(dip),102(lxd)
```

---

## 3. 👥 `who`

**Purpose:** Shows **who is logged in to the system** currently.

**Usage:**

```bash
who
```

**Example Output:**

```
user1     tty1         2025-09-11 09:12
admin    pts/0        2025-09-11 10:01 (192.168.1.5)
```

---

## 4. 👤 `users`

**Purpose:** Displays a **short list of all currently logged-in users (only usernames)**.

**Usage:**

```bash
users
```

**Example Output:**

```
user admin root
```

---

## 5. ➕ `adduser`

**Purpose:** Interactively **create a new user** (recommended, user-friendly).
It also creates the user’s home directory.

**Usage:**

```bash
sudo adduser john
```

**Steps shown during execution:**

* Creates user
* Asks for password
* Sets user info (name, room, phone, etc.)

---

## 6. ➕ `useradd`

**Purpose:** **Create a user (low-level)** — faster but needs options.
**Usage:**

```bash
sudo useradd -m john
sudo passwd john
```

* `-m` → creates home directory
* Needs `passwd` to set a password after creation

**Difference from `adduser`:**
`adduser` is more user-friendly, `useradd` is more basic and script-friendly.

---

## 7. 🔐 `passwd`

**Purpose:** Sets or changes a user’s password.

**Usage:**

```bash
passwd            # change own password
sudo passwd john  # change password of another user
```

**Extra:** Also can **lock or unlock** an account:

```bash
sudo passwd -l john   # lock
sudo passwd -u john   # unlock
```

---

## 8. 📇 `getent passwd`

**Purpose:** Retrieves **user account info from system databases (like `/etc/passwd` or LDAP)**.

**Usage:**

```bash
getent passwd john
```

**Example Output:**

```
john:x:1001:1001:John Doe,,,:/home/john:/bin/bash
```

This is better than `cat /etc/passwd` because it also works with network user directories (LDAP, NIS, etc.).

---

## 9. 📁 `cat /etc/passwd`

**Purpose:** Shows **all local user accounts** on the system.

**Usage:**

```bash
cat /etc/passwd
```
**Example Line:**

```
gautham:x:1002:1002:,,,:/home/gautham:/bin/bash
```

**Fields (colon-separated):**

```
username : x : UID : GID : comment : home directory : login shell
```

---

## 👥 Users in Linux

Linux has **two types of users**:

| Type                     | UID Range                         | Purpose                                                                               |
| ------------------------ | --------------------------------- | ------------------------------------------------------------------------------------- |
| **System users**         | 0–999                             | Created by the system or packages to run services (e.g. `mysql`, `nginx`, `www-data`)   |
| **Normal (human) users** | 1000+                             | Created manually for real people                                                         |

> `root` always has UID `0`.

---

## 📋 How to List All Users

All local user accounts are stored in:

```
/etc/passwd
```

**Command:**

```bash
cat /etc/passwd
```

Example line:

```
gautham:x:1002:1002:gauthamr58:/home/gautham:/bin/bash
```

---

## 🧮 Filter Based on UID

### 🔹 List all system users (UID < 1000)

```bash
awk -F: '$3 < 1000 {print $1, $3}' /etc/passwd
```

Example output:

```
root 0
daemon 1
mysql 113
nginx 116
```

---

### 🔹 List all normal (human) users (UID ≥ 1000)

```bash
awk -F: '$3 >= 1000 {print $1, $3}' /etc/passwd
```

Example output:

```
nobody 65534
ubuntu 1000
laxu 1001
gautham 1002
```

---

## 💡 Bonus: Using `getent`

If your system uses central authentication (LDAP, NIS, Active Directory), use `getent` instead:

```bash
getent passwd | awk -F: '$3>=1000 {print $1}'
```

This shows all normal users from both local and network databases.

## 📌 Note 

| Type |  Source |
|------|------------|
| Local  | Accounts stored on the machine (/etc/passwd). |
| LDAP  | central user db server ,create once in LDAP, can login to multiple servers with one account |
| Active Directory | Microsoft’s centralized user management system. |
 