# Installation and Setup

## 📖 Introduction

Before we start using Git, we need to install it on our system.

Git is available for all major operating systems, including **Windows**, **Linux**, and **macOS**. Once installed, it can be accessed through the command line, integrated into code editors like Visual Studio Code, or used with graphical tools such as GitHub Desktop.

---

# 💻 Ways to Use Git

There are several ways to work with Git depending on your preference.

## 1️⃣ Git Command Line Interface (CLI)

The Command Line Interface (CLI) is the most powerful and commonly used way to interact with Git.

It provides complete access to all Git features and is the preferred method used by professional developers and DevOps engineers.

---

## 2️⃣ Visual Studio Code

Visual Studio Code includes built-in Git support.

Using VS Code, you can:

* View file changes
* Stage files
* Create commits
* View commit history
* Synchronize with GitHub

without leaving the editor.

---

## 3️⃣ GitHub Desktop

GitHub Desktop is a graphical user interface (GUI) for Git.

It is beginner-friendly and allows users to perform common Git operations without using terminal commands.

---

# 🖥️ Installing Git

## Windows

### Step 1

Visit the official Git website:

```text
https://git-scm.com
```

### Step 2

Download the latest version for Windows.

### Step 3

Run the installer.

### Step 4

Keep the default installation settings (recommended for beginners).

### Step 5

Finish the installation.

---

## Linux (Ubuntu/Debian)

Update the package list:

```bash
sudo apt update
```

Install Git:

```bash
sudo apt install git -y
```

---

## macOS

If Homebrew is installed:

```bash
brew install git
```

Or download Git directly from:

```text
https://git-scm.com
```

---

# ✅ Verify the Installation

After installing Git, verify that it has been installed successfully.

Run the following command:

```bash
git --version
```

Example output:

```text
git version 2.43.0
```

If Git displays its version number, the installation was successful.

---

# 🌍 Real-World Analogy

Installing Git is similar to installing Microsoft Word on your computer.

Until Microsoft Word is installed, you cannot create or edit Word documents.

Similarly, until Git is installed, your computer cannot perform Git operations such as creating repositories, tracking changes, or managing project history.

Installation prepares your system to use Git.

---

# 💡 Best Practices

* Always download Git from the official website or your operating system's package manager.
* Keep Git updated to the latest stable version.
* Verify the installation before creating your first repository.
* Use the Git CLI while learning, as it helps you understand Git commands more deeply.

---

# 🎯 Interview Questions

### Q1. How do you check whether Git is installed?

**Answer**

```bash
git --version
```

---

### Q2. Which operating systems support Git?

**Answer**

Git supports all major operating systems, including:

* Windows
* Linux
* macOS

---

### Q3. Which method is most commonly used by professional developers to work with Git?

**Answer**

The **Git Command Line Interface (CLI)** is the most widely used method because it provides complete access to all Git features.

---

# 📌 Key Takeaways

* Git must be installed before it can be used.
* Git is available for Windows, Linux, and macOS.
* Git can be used through the CLI, Visual Studio Code, or GitHub Desktop.
* Verify the installation using `git --version`.
* Learning Git through the command line provides the strongest foundation.

---

## 🚀 What's Next?

Now that Git is installed, the next step is to configure it with your identity.

In the next chapter, we'll learn how to configure Git using `git config`, set up your username and email, understand the different configuration levels (**System**, **Global**, and **Local**), and see how Git uses this information to identify the author of every commit.
