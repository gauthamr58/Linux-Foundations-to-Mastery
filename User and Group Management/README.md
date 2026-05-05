
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

 