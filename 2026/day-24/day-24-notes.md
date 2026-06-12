# Day 24 – Advanced Git: Merge, Rebase, Stash & Cherry Pick

## Task

### Task 1: Git Merge — Hands-On
**What is a fast-forward merge?**
- A fast-forward merge happens when the target branch has no new commits since the feature branch was created.

Instead of creating a new merge commit, Git simply moves the branch pointer forward.

**When does Git create a merge commit instead?**

- Git creates a merge commit when both branches have new commits and Git cannot simply move the branch pointer forward.

A new merge commit (M) is created to combine both histories.

**What is a merge conflict?**

- Merge Conflict occurs when Git cannot automatically merge changes because the same part of a file was modified differently in two branches.

### Task 2: Git Rebase — Hands-On

**What does rebase actually do to your commits?**

- Rebase is a Git operation that moves or reapplies your branch commits on top of another branch's latest commits.

**How is the history different from a merge?**
- Merge combines branches and creates an additional merge commit.
- Rebase rewrites and reapplies commits on top of the target branch, creating a linear history without a merge commit.

Why should you **never rebase commits that have been pushed and shared** with others?
- You should never rebase commits that have already been pushed and shared because rebase rewrites commit history and changes commit IDs, which can cause conflicts and synchronization issues for other developers working on the same branch.

When would you use rebase vs merge?
- **Use Rebase when:**
You want a clean and linear commit history.
You are working on your own feature branch.
You want to bring your branch up to date with the latest changes from main before creating a Pull Request.

**Use Merge when:**
You want to preserve the actual branch history.
You are combining completed work from different branches.
The branch is shared with other developers.

### Task 4: Git Stash — Hands-On

**What is the difference between `git stash pop` and `git stash apply`?**

- **git stash pop** restores changes and removes the stash entry, whereas **git stash apply** restores changes but keeps the stash in the stash list.

When would you use stash in a real-world workflow?
- I use Git Stash when I have uncommitted changes but need to temporarily switch tasks without committing incomplete work.

### Task 5: Cherry Picking

**What does cherry-pick do?**

- git cherry-pick copies a specific commit from one branch and applies it to another branch without merging the entire branch.

- git cherry-pick <commit-id>

**When would you use cherry-pick in a real project?**

- I would use cherry-pick when I need a specific bug fix or feature commit from another branch without merging all the changes from that branch.

**What can go wrong with cherry-picking?**

- Cherry-picking can cause merge conflicts, duplicate commits, and a confusing Git history if the same changes are later merged from the original branch.