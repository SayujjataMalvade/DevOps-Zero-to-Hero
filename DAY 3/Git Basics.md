# Git Basics

## 1. What is Git?

Git is a distributed version control system (VCS) used to track changes
in source code. It allows multiple developers to collaborate on the same
project while maintaining a complete history of changes. Each developer
works on their own copy of the project, and Git ensures all versions are
managed efficiently.

## 2. Difference Between `main` and `master`

-   **master** was the default branch name in Git for many years.
-   **main** is now the new default branch name recommended by GitHub
    and most modern repositories.

Both branches serve the same purpose --- they represent the primary
development branch of your project. There is no functional difference;
the naming convention has simply evolved.

## 3. What is HEAD in Git?

`HEAD` is a pointer that represents the current commit or the current
branch you are working on.

-   When you are on a branch, `HEAD` points to the latest commit of that
    branch.
-   When you switch branches, `HEAD` moves to that branch.
-   When you check out a specific commit, Git enters a *detached HEAD
    state*.

In simple terms: **HEAD tells Git where you currently are in the
project's commit history.**

## 4. How to Push Local Code to a Remote Repository

Follow these steps to push your local project (e.g., the `master`
branch) to GitHub:

### Step 1: Initialize Git

``` bash
git init
```

### Step 2: Add your files

``` bash
git add .
```

### Step 3: Commit the changes

``` bash
git commit -m "Initial commit"
```

### Step 4: Add the remote repository URL

``` bash
git remote add origin https://github.com/<your-username>/<your-repo>.git
```

### Step 5: Push the local branch to GitHub

``` bash
git push -u origin master
```

## 5. Git Workflow Diagram (Simple)

``` mermaid
graph TD;
  A[Working Directory] --> B[Staging Area];
  B --> C[Local Repository];
  C --> D[Remote Repository];
```

## 6. Branching Strategy Diagram (Feature Branch Workflow)

``` mermaid
graph TD;
  M[main] --> F1[feature/login];
  M --> F2[feature/api];
  F1 --> PR1[Pull Request to main];
  F2 --> PR2[Pull Request to main];
  PR1 --> M;
  PR2 --> M;
```
