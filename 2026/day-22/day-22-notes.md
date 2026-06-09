# Day 22 – Introduction to Git: Your First Repository

## Task


![alt text](<git 2.PNG>)

![alt text](<git 1.PNG>)

## Understand the Git Workflow

1. What is the difference between `git add` and `git commit`?

- git add moves changes from the working directory to the staging area, preparing them for a commit.
- git commit saves the staged changes permanently in the Git repository as a new snapshot.

2. What does the **staging area** do? Why doesn't Git just commit directly?

- The staging area is an intermediate area where you collect and review changes before creating a commit. It lets you decide exactly which changes should be included in the next commit.

- Because Git gives you control over what gets committed. You may modify multiple files but want to commit only some of them. The staging area allows you to select and organize changes into meaningful commits.

3. What information does `git log` show you?

- git log shows the commit history of a repository.

**It displays:**

- Commit ID (hash)
- Author name
- Date and time of the commit
- Commit message

4. What is the `.git/` folder and what happens if you delete it?

The .git/ folder is the heart of a Git repository. It stores all Git metadata, including:

- Commit history
- Branch information
- Tags
- Configuration
- Staging area data
- Git objects (snapshots of files)

Without .git/, Git cannot track your project.

**What happens if you delete it?**

If you delete the .git/ folder:

- rm -rf .git

- The project files will remain.
- The entire Git history will be lost.
- All commits, branches, and tags will be gone.
- The folder will no longer be recognized as a Git repository.

5. What is the difference between a **working directory**, **staging area**, and **repository**?

1. Working Directory

- The actual files and folders you see and edit in your project.

2. Staging Area

- A temporary area where you select changes that should go into the next commit.

3. Repository

- The Git database where commits are permanently stored.
