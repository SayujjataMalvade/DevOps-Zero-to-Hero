# Branching Strategies in Git

## Branch Types

### **Dev Branch**

Used by developers to push their daily code changes. Each feature or
task is developed here before moving forward.

### **Staging Branch**

A pre-production branch that mirrors the production/master branch. All
code is tested here before being released.

### **Production Branch**

The live branch used by end users. Only fully tested and approved code
is merged here.

------------------------------------------------------------------------

## **Hotfix**

A hotfix is created when an urgent issue occurs in the production
environment.
Hotfix branches contain small but critical fixes and must be merged
into: - Production branch - Development branch
This ensures every branch stays in sync.

------------------------------------------------------------------------

## **CI/CD & Jira Workflow**

DevOps engineers automate the build, test, and deployment pipeline using
CI/CD tools.
Most companies use **Jira** for: - Work assignment
- Sprint planning
- Tracking progress
- Ensuring alignment across dev, QA, and DevOps teams

------------------------------------------------------------------------

# Revert and Reset

## **Revert**

Used when a specific commit needs to be undone *without* affecting later
commits.

### **Commands**

``` bash
git log --oneline
git revert <commit-id>
```

This opens the editor (Nano by default) to modify the commit message.

Exit logs using:

    q

Revert creates a *new* commit and does **not** delete commit history.

------------------------------------------------------------------------

## **Reset**

Reset is used to delete commit history --- useful when sensitive data
(like passwords) was committed by mistake.

⚠️ **Dangerous command --- use carefully**

### Types of Reset

#### **1. Soft Reset**

Deletes commit history but keeps your work staged.

``` bash
git reset --soft <commit-id>
```

#### **2. Mixed Reset**

Deletes commit history and unstages files.

``` bash
git reset --mixed <commit-id>
```

#### **3. Hard Reset**

Deletes commits AND local file changes.

``` bash
git reset --hard <commit-id>
```

------------------------------------------------------------------------

# Merge and Rebase

## **Merge**

Used to combine changes from one branch into another.

### Example

``` bash
git checkout master
git merge dev
```

A new merge commit is created.
Merge preserves the full branching history.

### Merge Behavior

-   HEAD pointers remain **equal**
-   History becomes non-linear

------------------------------------------------------------------------

## **Rebase**

Rebase is also used to integrate changes but creates a **linear** commit
history.

Useful when working locally and wanting a clean history.

------------------------------------------------------------------------

## Rebase Visualization

<img width="1776" height="1004" alt="Screenshot 2025-11-18 205221" src="https://github.com/user-attachments/assets/74f4bb01-9ba3-4457-8e94-67d0bb3d3cfe" />

## Branching Strategy Diagram

<img width="765" height="965" alt="Screenshot 2025-11-18 223637" src="https://github.com/user-attachments/assets/c66ff030-e752-40ef-ad03-0644929b3c0a" />

------------------------------------------------------------------------

## Branch Types

### **Dev Branch**

Used by developers to push their daily code changes.

### **Staging Branch**

Pre-production environment mirroring production/master.

### **Production Branch**

Live branch used by end-users.

------------------------------------------------------------------------

## **Hotfix**

Urgent production fix merged back into: - Production - Development To
keep branches in sync.

------------------------------------------------------------------------

# Revert and Reset

## Revert

Undo a single commit without removing history.

``` bash
git log --oneline
git revert <commit-id>
```

------------------------------------------------------------------------

## Reset (Dangerous)

Deletes commit history.

### Types:

#### Soft

``` bash
git reset --soft <commit-id>
```

#### Mixed

``` bash
git reset --mixed <commit-id>
```

#### Hard

``` bash
git reset --hard <commit-id>
```

------------------------------------------------------------------------

# Merge and Rebase

## Merge

``` bash
git checkout master
git merge dev
```

Preserves history (non‑linear).

------------------------------------------------------------------------

## Rebase

Creates a linear history.

------------------------------------------------------------------------




# Summary

-   **Merge** → safer, keeps full history
-   **Rebase** → cleaner, linear history
-   **Revert** → undo a single commit (non-destructive)
-   **Reset** → delete history (dangerous, use carefully)
