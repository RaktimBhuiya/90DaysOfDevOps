# Day 23 – Git Branching & Working with GitHub

## Task

### Task 1: Understanding Branches

1. What is a branch in Git?
- A Git branch is an independent line of development that allows you to work on changes without     affecting the main codebase.

git branch feature-login

2. Why do we use branches instead of committing everything to `main`?
- Branches allow developers to work on features, bug fixes, or experiments independently without affecting the stable code in main. This reduces risk, improves collaboration, and ensures changes can be tested before being merged into the main branch.

3. What is `HEAD` in Git?
- HEAD is a pointer that refers to the current branch or the latest commit you're currently working on.

4. What happens to your files when you switch branches?

- When you switch branches, Git updates the files in your working directory to match the latest commit of the target branch. Files may be added, removed, or have different content depending on what exists in that branch.

**Example:**

main → app.txt contains Version 1
feature → app.txt contains Version 2

**Running:**

- git checkout feature

changes app.txt from Version 1 to Version 2 in the same working directory.