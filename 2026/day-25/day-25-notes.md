# Day 25 – Git Reset vs Revert & Branching Strategies

## Task

### Task 1: Git Reset — Hands-On









### Task 3: Reset vs Revert — Summary

|Feature	|git reset	|git revert|
| :---------| :-------  | :------- |
|What it does|	Moves the branch pointer to an earlier commit and can remove commits from history.	|Creates a new commit that undoes the changes of a previous commit.|
|Removes commit from history?|	Yes|No|
|Safe for shared/pushed branches?|	No	|Yes|
|When to use|	When working on local/private commits that haven't been shared.|When you need to undo a commit that has already been pushed or shared with others.|


### Task 4: Branching Strategie
**GitFlow**

How it works

- GitFlow uses multiple long-lived branches such as main and develop, along with temporary feature, release, and hotfix branches.

**Fow Diagram**
```text
main
  |
  +---- hotfix/*
  |
develop
  |
  +---- feature/*
  |
  +---- release/*
  ```
**Branch Purpose**
- main → Production-ready code
- develop → Integration branch for ongoing development
- feature/* → New features
- release/* → Prepare releases
- hotfix/* → Emergency production fixes

**When/Where Used**
- Large teams
- Enterprise projects
- Applications with scheduled releases

**Pros**
- Clear separation of development and production
- Well-structured release process
- Good for large teams

**Cons**
- Complex workflow
- Too many branches
- Slower development cycle

2. GitHub Flow

How it works

- A lightweight workflow with a single main branch and short-lived feature branches.

**Flow Diagram**

```text
main
 |
 +---- feature-login
 |
 +---- feature-profile
 |
 +---- bugfix-auth
```

**Workflow:**

- Create a feature branch from main
- Make changes
- Open Pull Request
- Review and merge into main
- Deploy

**When/Where Used**

- Small to medium teams
- Continuous Deployment (CD)
- Web applications

**Pros**
- Simple and easy to learn
- Fast development cycle
- Works well with CI/CD
**Cons**
- Less control over release management
- Not ideal for multiple production versions

3. Trunk-Based Development

How it works

- Developers commit directly to main (trunk) or use very short-lived branches that are merged quickly.

**Flow Diagram**
```text
main (trunk)
 |
 +-- small branch --> merge quickly
 |
 +-- small branch --> merge quickly
 |
 +-- small branch --> merge quickly
```

**Workflow**

- Create a short-lived branch (optional)
- Make small changes
- Merge to main within hours or a few days
- Deploy frequently

**When/Where Used**

- DevOps teams
- High-frequency deployments
- Cloud-native and Agile environments

**Pros**
- Minimal merge conflicts
- Fast delivery
- Supports Continuous Integration and Continuous Deployment
**Cons**
- Requires strong automated testing
- Poor testing can break main
- Needs disciplined development practices