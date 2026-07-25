# .gitignore & .gitkeep

## 📖 Introduction

In every software project, there are certain files and folders that **should not be tracked by Git**.

These files may contain:

* Sensitive information (API keys, passwords, tokens)
* Environment-specific configuration
* Temporary files
* Build artifacts
* Dependency folders
* IDE settings

Tracking these files increases repository size, creates unnecessary conflicts, and may even expose confidential data.

Git provides two special files to solve these problems:

* **`.gitignore`** – Tells Git which files or folders to ignore.
* **`.gitkeep`** – Helps track an otherwise empty directory.

---

# 🤔 What is `.gitignore`?

A **`.gitignore`** file tells Git to ignore specific files and folders so they are **not added, committed, or pushed** to the repository.

Git behaves as if those files don't exist (unless they were already tracked).

---

# 🌍 Real-World Analogy

Imagine you're packing documents before sending them to your manager.

Your folder contains:

* Project Report ✅
* Resume ✅
* Personal Diary ❌
* Bank Details ❌
* Password Notebook ❌

You only send the documents related to the project.

Similarly, **`.gitignore`** tells Git:

> "Ignore these files—they are not meant to be shared."

---

# 💡 Why Do We Use `.gitignore`?

Using `.gitignore` helps to:

* Protect sensitive information
* Reduce repository size
* Avoid uploading temporary files
* Prevent unnecessary merge conflicts
* Keep the repository clean
* Improve collaboration

---

# 📄 Common Files to Ignore

Some files should almost never be committed.

### Environment Variables

```text id="h6k5lm"
.env
.env.local
```

These files usually contain:

* API Keys
* Database Passwords
* Secret Tokens

---

### Dependency Folders

```text id="o2q9nv"
node_modules/
vendor/
```

These folders can be recreated using package managers and are often very large.

---

### Build Files

```text id="p9v3ks"
dist/
build/
target/
```

These are generated automatically during the build process.

---

### IDE Settings

```text id="j5m8wy"
.vscode/
.idea/
```

Editor-specific settings usually don't need to be shared.

---

# 🛠️ Creating a `.gitignore` File

Create the file:

```bash id="n4b2td"
touch .gitignore
```

Add files or folders you want Git to ignore.

Example:

```text id="g7v8la"
.env
node_modules/
dist/
.vscode/
```

Now check the repository status:

```bash id="a8p1dr"
git status
```

Git will ignore the files listed in `.gitignore`.

---

# ⚠️ Important Note

`.gitignore` only affects **untracked files**.

If a file has already been committed, adding it to `.gitignore` will **not** stop Git from tracking it.

To remove it from tracking while keeping it locally:

```bash id="x5k7rn"
git rm --cached <file-name>
```

Then commit the change.

---

# 🤔 What is `.gitkeep`?

Git **does not track empty directories**.

If a folder has no files, Git simply ignores it.

Sometimes, you want to keep an empty folder in the repository because it will store files later.

That's where **`.gitkeep`** is used.

---

# 🌍 Real-World Analogy

Imagine you're constructing a building.

Some rooms are empty today, but they're reserved for future use.

Instead of removing those rooms from the blueprint, you leave a small placeholder to indicate they should exist.

`.gitkeep` works exactly like that placeholder.

---

# 🛠️ Using `.gitkeep`

Suppose you have this structure:

```text id="r3x8wp"
logs/
```

Since `logs/` is empty, Git won't track it.

Create a placeholder:

```bash id="b2j7yu"
touch logs/.gitkeep
```

Now Git tracks the folder because it contains a file.

Repository structure:

```text id="l6f4er"
logs/
└── .gitkeep
```

---

# 🔄 Typical Workflow

```text id="z8w2pm"
Create Project
        │
        ▼
Create .gitignore
        │
        ▼
Add Files to Ignore
        │
        ▼
git status
        │
        ▼
git add .gitignore
        │
        ▼
git commit
        │
        ▼
git push
```

For empty folders:

```text id="y1n9vc"
Create Empty Folder
        │
        ▼
Add .gitkeep
        │
        ▼
git add
        │
        ▼
git commit
```

---

# 💡 Best Practices

* Never commit `.env` files containing secrets.
* Ignore dependency folders like `node_modules/`.
* Ignore generated build artifacts.
* Commit the `.gitignore` file itself.
* Use `.gitkeep` only when an empty directory must exist in the repository.

---

# ❌ Common Mistakes

| Mistake                                     | Better Practice                                                   |
| ------------------------------------------- | ----------------------------------------------------------------- |
| Committing `.env` files                     | Add them to `.gitignore` before the first commit.                 |
| Assuming `.gitignore` removes tracked files | Use `git rm --cached` for already tracked files.                  |
| Committing `node_modules/`                  | Install dependencies using the package manager instead.           |
| Creating empty folders without `.gitkeep`   | Add a `.gitkeep` file if the folder should be version controlled. |

---

# 🎯 Interview Questions

### Q1. What is the purpose of `.gitignore`?

**Answer:**
It tells Git to ignore specific files and directories so they are not tracked or committed.

---

### Q2. Why shouldn't `.env` files be committed?

**Answer:**
Because they often contain sensitive information such as API keys, passwords, tokens, and database credentials.

---

### Q3. Does `.gitignore` affect files that are already tracked?

**Answer:**
No. It only affects untracked files. Already tracked files must first be removed using `git rm --cached`.

---

### Q4. Why is `.gitkeep` used?

**Answer:**
Git does not track empty directories. A `.gitkeep` file acts as a placeholder so the directory can be included in the repository.

---

### Q5. Is `.gitkeep` an official Git feature?

**Answer:**
No. It is a community convention used to keep empty directories under version control.

---

# 📌 Key Takeaways

* `.gitignore` prevents unnecessary or sensitive files from being tracked.
* It helps keep repositories secure, clean, and lightweight.
* `.gitignore` does not untrack files that are already committed.
* `.gitkeep` is a placeholder used to keep empty directories in Git.
* Both files are widely used in professional software development.

---

## 🚀 What's Next?

Now that you know how to control which files Git tracks, it's time to learn how developers work on multiple features simultaneously.

In the next chapter, we'll explore **Branching & Merging**, understand why branches are essential, and learn how Git combines changes safely into the main codebase.
