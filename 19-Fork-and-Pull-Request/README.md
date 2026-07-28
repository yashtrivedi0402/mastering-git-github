# Git Fork & Pull Request

## 📖 Introduction

Modern software development is built around collaboration. Developers often contribute to projects that they do not own, especially in **open-source communities** and large organizations.

Since contributors usually don't have direct write access to the original repository, GitHub provides a workflow based on **Forks** and **Pull Requests (PRs)**.

A **Fork** allows you to create your own copy of a repository, while a **Pull Request** lets you propose your changes to the original project for review and possible merging.

This workflow is widely used by companies like Google, Microsoft, Meta, and thousands of open-source projects on GitHub.

---

# 🤔 What is a Fork?

A **Fork** is your personal copy of someone else's GitHub repository.

It creates a completely separate repository under your GitHub account.

Once forked, you can:

* Make changes freely
* Create branches
* Commit code
* Push changes
* Experiment without affecting the original repository

The original repository remains unchanged until your changes are accepted through a Pull Request.

---

# 🌍 Real-World Analogy

Imagine your teacher shares an assignment template with the class.

Instead of editing the teacher's original file, each student makes their own copy.

Students complete their work independently and then submit it for review.

Git Fork works exactly the same way.

* Teacher's file → Original Repository
* Student's copy → Forked Repository
* Assignment submission → Pull Request

---

# 🤔 Why Do We Use Forks?

Forks allow developers to:

* Contribute to open-source projects
* Experiment safely
* Work without direct repository access
* Build personal versions of projects
* Submit improvements for review

---

# 🏗️ How Forking Works

```text id="p6r2yn"
          Original Repository
          (Project Owner)
                  │
                  ▼
              Fork Repository
           (Your GitHub Account)
                  │
                  ▼
          Clone to Local Machine
                  │
                  ▼
            Create Feature Branch
                  │
                  ▼
              Make Changes
                  │
                  ▼
              Commit Changes
                  │
                  ▼
              Push to Fork
                  │
                  ▼
          Create Pull Request
                  │
                  ▼
          Project Owner Reviews
                  │
                  ▼
          Merge or Reject Changes
```

---

# 🚀 Step 1: Fork a Repository

1. Open the GitHub repository.
2. Click the **Fork** button.
3. GitHub creates a copy of the repository under your account.

Example:

```text id="rzk9jh"
Original

github.com/company/project

↓

Fork

github.com/your-username/project
```

Now you own your fork and can modify it freely.

---

# 🚀 Step 2: Clone Your Fork

Clone the forked repository to your local machine.

```bash id="6yl9ux"
git clone git@github.com:your-username/project.git
```

Move into the project directory.

```bash id="l43v4i"
cd project
```

---

# 🚀 Step 3: Create a Feature Branch

Never work directly on the default branch.

Create a new feature branch.

```bash id="jy1rza"
git switch -c feature-login
```

---

# 🚀 Step 4: Make Changes

Modify the project files.

Example:

```text id="ud6sqs"
Added Login Page

Fixed Bug

Improved Documentation
```

---

# 🚀 Step 5: Commit Changes

Stage the files.

```bash id="ycn9gc"
git add .
```

Create a commit.

```bash id="4d4bnr"
git commit -m "Add login feature"
```

---

# 🚀 Step 6: Push to Your Fork

Push your feature branch.

```bash id="1g7i2k"
git push origin feature-login
```

Your changes are now available on your GitHub fork.

---

# 🚀 Step 7: Create a Pull Request

Open your fork on GitHub.

GitHub will display:

```text id="ngnkdu"
Compare & Pull Request
```

Click it.

Provide:

* Title
* Description
* Screenshots (if required)
* Testing details

Submit the Pull Request.

---

# 📨 What is a Pull Request?

A **Pull Request (PR)** is a request asking the project owner to review and merge your changes into the original repository.

A Pull Request does **not** automatically merge your code.

Instead, it starts a discussion where maintainers can:

* Review code
* Suggest improvements
* Request changes
* Approve changes
* Merge the Pull Request

---

# 🏗️ Pull Request Workflow

```text id="mtrfq4"
Fork Repository
       │
       ▼
Clone Repository
       │
       ▼
Create Branch
       │
       ▼
Develop Feature
       │
       ▼
Commit Changes
       │
       ▼
Push Branch
       │
       ▼
Open Pull Request
       │
       ▼
Code Review
       │
       ▼
Approve
       │
       ▼
Merge
```

---

# 📋 Common Git Commands

| Command                        | Purpose                                       |
| ------------------------------ | --------------------------------------------- |
| `git clone <repository-url>`   | Clone your fork                               |
| `git switch -c feature-name`   | Create a feature branch                       |
| `git add .`                    | Stage changes                                 |
| `git commit -m "message"`      | Save changes                                  |
| `git push origin feature-name` | Push your branch                              |
| `git fetch upstream`           | Download updates from the original repository |
| `git merge upstream/main`      | Sync your fork with the original repository   |

---

# 🔄 Keeping Your Fork Updated

The original repository continues to receive updates.

To keep your fork synchronized, first add the original repository as an **upstream remote**.

```bash id="2grqun"
git remote add upstream git@github.com:owner/project.git
```

Verify your remotes.

```bash id="wzl9d8"
git remote -v
```

Example:

```text id="pr4uof"
origin    git@github.com:your-username/project.git
upstream  git@github.com:owner/project.git
```

Fetch the latest changes.

```bash id="lfd1om"
git fetch upstream
```

Switch to the main branch.

```bash id="xxw4k5"
git switch main
```

Merge the latest updates.

```bash id="6cz3kk"
git merge upstream/main
```

Push the updated branch to your fork.

```bash id="qb4rqz"
git push origin main
```

---

# 📊 Clone vs Fork

| Feature                                    | Clone | Fork |
| ------------------------------------------ | ----- | ---- |
| Creates a local copy                       | ✅     | ❌    |
| Creates a GitHub repository                | ❌     | ✅    |
| Used for personal development              | ✅     | ✅    |
| Used for contributing without write access | ❌     | ✅    |

---

# 📊 Merge vs Pull Request

| Merge                       | Pull Request                    |
| --------------------------- | ------------------------------- |
| Git command                 | GitHub feature                  |
| Combines branches           | Requests code review            |
| Happens locally or remotely | Happens on GitHub               |
| No review required          | Usually reviewed before merging |

---

# 💡 Best Practices

* Always create a feature branch for your work.
* Keep commits small and meaningful.
* Write a clear Pull Request title and description.
* Sync your fork regularly with the upstream repository.
* Address review comments before requesting another review.

---

# ❌ Common Mistakes

| Mistake                                       | Better Practice                                      |
| --------------------------------------------- | ---------------------------------------------------- |
| Working directly on the main branch           | Create a feature branch                              |
| Opening a Pull Request with unrelated changes | Keep each PR focused on one feature or fix           |
| Forgetting to sync your fork                  | Fetch updates from the upstream repository regularly |
| Creating huge Pull Requests                   | Submit smaller, easier-to-review PRs                 |
| Ignoring review comments                      | Resolve requested changes before merging             |

---

# 🎯 Interview Questions

### Q1. What is a Git Fork?

**Answer:**

A Fork is a personal copy of another user's GitHub repository that allows you to make changes independently without affecting the original project.

---

### Q2. What is a Pull Request?

**Answer:**

A Pull Request is a request to merge your changes from one branch or fork into another repository after code review.

---

### Q3. What is the difference between Fork and Clone?

**Answer:**

A Fork creates a copy of a repository on GitHub, while Clone downloads a repository from GitHub to your local machine.

---

### Q4. What is the purpose of the upstream remote?

**Answer:**

The upstream remote points to the original repository, allowing you to fetch and synchronize the latest changes into your fork.

---

### Q5. Which command adds the original repository as an upstream remote?

```bash id="63ccjq"
git remote add upstream git@github.com:owner/project.git
```

---

### Q6. Why should you create a feature branch before making changes?

**Answer:**

A feature branch keeps your work isolated, makes code reviews easier, and prevents accidental changes to the main branch.

---

# 📌 Key Takeaways

* A Fork creates your own copy of another repository on GitHub.
* A Clone downloads a repository to your local machine.
* Pull Requests are used to propose changes for review and merging.
* The upstream remote helps keep your fork synchronized with the original repository.
* The Fork → Clone → Branch → Commit → Push → Pull Request workflow is the standard contribution process used in open-source and enterprise development.

---

## 🚀 What's Next?

Now that you know how to contribute to repositories using Forks and Pull Requests, it's time to understand how teams collaborate on shared repositories in day-to-day development.

In the next chapter, you'll learn the **GitHub Collaboration Workflow**, including branch strategies, feature-based development, code reviews, approvals, and the complete workflow followed by professional software engineering and DevOps teams.
