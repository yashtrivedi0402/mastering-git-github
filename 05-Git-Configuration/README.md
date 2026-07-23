# Git Configuration

## 📖 Introduction

After installing Git, the next step is to configure it.

Before Git starts tracking your work, it needs to know **who is making the changes**. Every commit in Git contains information about its author, making it easy to identify who created or modified the code.

Git stores this information using **configuration settings**.

---

# 🤔 What is Git Configuration?

Git Configuration is the process of setting up Git with your personal information and preferences.

The two most important configuration settings are:

* **User Name**
* **Email Address**

Whenever you create a commit, Git automatically records:

* Author Name
* Author Email
* Date & Time
* Commit Message
* Commit ID (SHA)

This information becomes part of the project's history.

---

# 🌍 Real-World Analogy

Imagine you're writing a book.

Every chapter includes the author's name.

Without the author's name, no one knows who wrote it.

Similarly, every Git commit stores the author's identity so that anyone viewing the project history knows who made each change.

---

# ⚙️ Git Configuration Levels

Git supports three configuration levels.

## 1️⃣ System Configuration

Applies to **every user** on the computer.

Location:

```text
/etc/gitconfig
```

Command:

```bash
git config --system
```

This level is generally managed by system administrators.

---

## 2️⃣ Global Configuration

Applies to **all repositories** of the current user.

Location:

```text
~/.gitconfig
```

Command:

```bash
git config --global
```

This is the most commonly used configuration level.

When learning Git, you'll mostly use the **Global** configuration.

---

## 3️⃣ Local Configuration

Applies **only to the current repository**.

Location:

```text
<repository>/.git/config
```

Command:

```bash
git config --local
```

Local settings override Global settings for that specific repository.

---

# 📝 Configure Your Username

Set your Git username:

```bash
git config --global user.name "Your Name"
```

Example:

```bash
git config --global user.name "Yash Trivedi"
```

---

# 📧 Configure Your Email

Set your Git email:

```bash
git config --global user.email "your-email@example.com"
```

Example:

```bash
git config --global user.email "yashtrivedi@gmail.com"
```

It is recommended to use the same email address associated with your GitHub account so that your commits are linked to your GitHub profile.

---

# 🔍 Verify Your Configuration

Display your configured username:

```bash
git config --global user.name
```

Display your configured email:

```bash
git config --global user.email
```

Display all Git configuration settings:

```bash
git config --list
```

Example output:

```text
user.name=Yash Trivedi
user.email=yashtrivedi@gmail.com
core.editor=code
init.defaultbranch=main
```

---

# ⚖️ System vs Global vs Local

| Configuration | Scope             | Common Use                       |
| ------------- | ----------------- | -------------------------------- |
| System        | Entire computer   | Managed by system administrators |
| Global        | Current user      | Personal Git configuration       |
| Local         | Single repository | Project-specific configuration   |

---

# 💡 Best Practices

* Configure Git immediately after installation.
* Use your real name for professional projects.
* Use the same email address linked to your GitHub account.
* Prefer **Global** configuration unless a project requires different settings.
* Verify your configuration before creating your first commit.

---

# 🎯 Interview Questions

### Q1. Why do we configure `user.name` and `user.email`?

**Answer:**

Git records the author's name and email in every commit. This helps identify who made a particular change and is especially important when multiple developers collaborate on the same repository.

---

### Q2. What are the three Git configuration levels?

**Answer:**

* System
* Global
* Local

---

### Q3. Which configuration level is most commonly used?

**Answer:**

The **Global** configuration is the most commonly used because it applies to all repositories owned by the current user.

---

### Q4. Which command displays all Git configuration settings?

**Answer:**

```bash
git config --list
```

---

# 📌 Key Takeaways

* Git Configuration tells Git who you are.
* Every commit stores the author's name and email.
* Git provides three configuration levels: **System**, **Global**, and **Local**.
* Global configuration is the most commonly used.
* You can verify your settings using `git config --list`.

---

## 🚀 What's Next?

Now that Git is installed and configured, it's time to create your first Git repository.

In the next chapter, we'll understand **Git Architecture & Workflow**, including the **Working Directory**, **Staging Area**, **Local Repository**, and **Remote Repository**, and learn how code flows through each stage before reaching GitHub.
