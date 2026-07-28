# Git SSH Authentication

## 📖 Introduction

Whenever you push or pull code from GitHub, your computer must authenticate itself.

There are two common authentication methods:

* **HTTPS Authentication** – Uses your GitHub username and Personal Access Token (PAT).
* **SSH Authentication** – Uses a secure SSH key pair to verify your identity.

For developers and DevOps engineers, **SSH Authentication** is the recommended approach because it is more secure, faster, and eliminates the need to enter credentials repeatedly.

---

# 🤔 What is SSH?

**SSH (Secure Shell)** is a secure network protocol used to establish encrypted communication between two systems.

In the context of GitHub, SSH allows your computer to authenticate itself using cryptographic keys instead of passwords.

---

# 🌍 Real-World Analogy

Imagine your office uses a **smart access card**.

Instead of entering your username and password every time you enter the building, you simply scan your card.

GitHub SSH Authentication works the same way.

* Your **Private Key** stays securely on your computer.
* Your **Public Key** is stored on GitHub.
* When you connect, GitHub verifies the keys and grants access automatically.

---

# 🤔 Why Do We Use SSH?

SSH Authentication provides several benefits:

* Secure authentication
* No need to enter credentials repeatedly
* Faster Git operations
* Encrypted communication
* Preferred for professional development and DevOps workflows

---

# 🏗️ How SSH Authentication Works

```text id="hj2m7a"
          Your Computer
        ┌────────────────┐
        │  Private Key   │
        └───────┬────────┘
                │
      Secure SSH Connection
                │
                ▼
        ┌────────────────┐
        │     GitHub     │
        │   Public Key   │
        └────────────────┘
```

The **Private Key** never leaves your computer.

GitHub stores only the **Public Key**.

Whenever you connect, GitHub verifies that both keys belong together before allowing access.

---

# 🔐 HTTPS vs SSH

| Feature                           | HTTPS                            | SSH          |
| --------------------------------- | -------------------------------- | ------------ |
| Authentication                    | Username + Personal Access Token | SSH Key Pair |
| Password Required                 | Yes (PAT)                        | No           |
| Security                          | High                             | Very High    |
| Developer Convenience             | Good                             | Excellent    |
| Recommended for Daily Development | ❌                                | ✅            |

---

# 🚀 Step 1: Generate an SSH Key Pair

Open your terminal and run:

```bash id="wkh0yf"
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Example:

```bash id="l40s3v"
ssh-keygen -t ed25519 -C "john@example.com"
```

Git will ask where to save the key.

Press **Enter** to accept the default location.

```text id="gsy6z9"
Enter file in which to save the key:
~/.ssh/id_ed25519
```

Git will also ask for a passphrase.

You may:

* Set a passphrase for additional security.
* Press **Enter** to skip it.

---

# 🏗️ Generated Files

After the command completes, Git creates two files.

```text id="8qxt4l"
~/.ssh/

id_ed25519
id_ed25519.pub
```

| File             | Purpose                       |
| ---------------- | ----------------------------- |
| `id_ed25519`     | Private Key (Never share it)  |
| `id_ed25519.pub` | Public Key (Upload to GitHub) |

> **⚠️ Never share your Private Key with anyone.**

---

# 📋 Step 2: Copy the Public Key

### Windows (Git Bash / WSL)

```bash id="cyn3uv"
clip.exe < ~/.ssh/id_ed25519.pub
```

---

### Linux

```bash id="n8xblz"
cat ~/.ssh/id_ed25519.pub
```

Copy the displayed key manually.

---

### macOS

```bash id="6cvjlk"
pbcopy < ~/.ssh/id_ed25519.pub
```

---

# 🌐 Step 3: Add the Public Key to GitHub

1. Open GitHub.
2. Click your **Profile Picture**.
3. Go to **Settings**.
4. Select **SSH and GPG keys**.
5. Click **New SSH key**.
6. Enter a title (e.g., *My Laptop*).
7. Paste the copied Public Key.
8. Click **Add SSH key**.
9. Complete GitHub verification if prompted.

---

# 🧪 Step 4: Test the SSH Connection

Run:

```bash id="d4db5l"
ssh -T git@github.com
```

The first time you connect, you'll see:

```text id="0ys6h9"
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text id="3xn1ui"
yes
```

If everything is configured correctly, GitHub responds:

```text id="57ikrk"
Hi username! You've successfully authenticated,
but GitHub does not provide shell access.
```

This confirms that SSH Authentication is working successfully.

---

# 🔄 Step 5: Clone Using SSH

Instead of cloning with HTTPS:

```text id="j2qv7e"
https://github.com/user/repository.git
```

Use the SSH URL:

```text id="c3xg8w"
git@github.com:user/repository.git
```

Clone the repository:

```bash id="dgm6j1"
git clone git@github.com:user/repository.git
```

---

# 🚀 Step 6: Push Code Without Credentials

Once SSH is configured, pushing code is exactly the same.

```bash id="6bht6k"
git push origin main
```

Git automatically authenticates using your SSH key.

No username or password is required.

---

# 🏗️ Complete SSH Authentication Workflow

```text id="syw7kg"
Generate SSH Key
        │
        ▼
Copy Public Key
        │
        ▼
Add Public Key to GitHub
        │
        ▼
Verify Connection
        │
        ▼
Clone Repository Using SSH
        │
        ▼
Push & Pull Code Securely
```

---

# 📋 Common SSH Commands

| Command                                        | Purpose                        |
| ---------------------------------------------- | ------------------------------ |
| `ssh-keygen -t ed25519 -C "email"`             | Generate an SSH key pair       |
| `clip.exe < ~/.ssh/id_ed25519.pub`             | Copy the public key (Windows)  |
| `cat ~/.ssh/id_ed25519.pub`                    | Display the public key (Linux) |
| `pbcopy < ~/.ssh/id_ed25519.pub`               | Copy the public key (macOS)    |
| `ssh -T git@github.com`                        | Test the SSH connection        |
| `git clone git@github.com:user/repository.git` | Clone a repository using SSH   |

---

# 💡 Best Practices

* Keep your **Private Key** secure and never share it.
* Upload only the **Public Key** to GitHub.
* Protect your SSH key with a passphrase whenever possible.
* Use SSH instead of HTTPS for daily development.
* Test your SSH connection after adding the key to GitHub.

---

# ❌ Common Mistakes

| Mistake                                  | Better Practice                         |
| ---------------------------------------- | --------------------------------------- |
| Uploading the Private Key to GitHub      | Upload only the Public Key (`.pub`)     |
| Sharing the Private Key                  | Keep it private and secure              |
| Cloning with HTTPS after configuring SSH | Use the SSH repository URL              |
| Forgetting to test the connection        | Run `ssh -T git@github.com` after setup |

---

# 🎯 Interview Questions

### Q1. What is SSH?

**Answer:**

SSH (Secure Shell) is a secure protocol that allows encrypted communication and authentication between two systems using cryptographic keys.

---

### Q2. Why is SSH preferred over HTTPS?

**Answer:**

SSH provides secure, password-free authentication using key pairs, making Git operations faster and more convenient.

---

### Q3. Which command generates an SSH key pair?

```bash id="t2ebwh"
ssh-keygen -t ed25519 -C "your_email@example.com"
```

---

### Q4. Which key should be uploaded to GitHub?

**Answer:**

The **Public Key** (`id_ed25519.pub`).

---

### Q5. Which command tests the SSH connection?

```bash id="ojzy8r"
ssh -T git@github.com
```

---

### Q6. Can the Private Key be shared?

**Answer:**

No. The Private Key must always remain secret and should never be shared with anyone.

---

# 📌 Key Takeaways

* SSH provides secure authentication using a Public/Private Key pair.
* The Private Key remains on your computer, while the Public Key is uploaded to GitHub.
* SSH eliminates the need to enter credentials for every Git operation.
* Always use the SSH repository URL after configuring SSH.
* Test your connection before pushing or pulling code.

---

## 🚀 What's Next?

Now that you've securely connected your local machine to GitHub using SSH, it's time to learn how developers contribute to projects they don't own.

In the next chapter, you'll explore **Forks and Pull Requests**—how to create your own copy of a repository, make changes independently, push your updates, and submit a Pull Request for review and collaboration in open-source and team-based projects.
