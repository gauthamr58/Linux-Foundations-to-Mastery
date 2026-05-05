
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


 