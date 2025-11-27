# Git Branching, Merge, Rebase, Revert & Reset

Below is a combined and professionally formatted Markdown file containing **all your provided content** + the newly written **Merge & Merge Conflict Explanation**.

---

# Branching Strategies in Git

## Branch Types

### **Dev Branch**

Used by developers to push their daily code changes. Each feature or task is developed here before moving forward.

### **Staging Branch**

A pre-production branch that mirrors the production/master branch. All code is tested here before being released.

### **Production Branch**

The live branch used by end users. Only fully tested and approved code is merged here.

---

## **Hotfix**

A **hotfix** is created when an urgent issue occurs in the production environment.
Hotfix branches contain small but critical fixes and must be merged into:

* Production branch
* Development branch

This keeps all branches synchronized.

---

## CI/CD & Jira Workflow

DevOps engineers automate builds, tests, and deployments using CI/CD tools.
Most companies use **Jira** for:

* Work assignment
* Sprint planning
* Tracking progress
* Ensuring alignment across Dev, QA, and DevOps teams

---

# Understanding Git Merge & Merge Conflicts

## ✅ What is a Merge?

A **merge** in Git combines changes from one branch into another. It is commonly used to bring updates from a feature or development branch into the main branch.

Git automatically merges changes when there is no overlap in modified content. Otherwise, it produces a **merge conflict**.

---

## ❗ What is a Merge Conflict?

A **merge conflict** occurs when:

* The same file exists in two branches
* The same lines in the file were modified differently
* Git cannot automatically decide which version to keep

### Example Scenario

If `test.txt` contains different information in `dev` and `master`, Git will stop the merge and ask for manual resolution.

---

## 🛠 How DevOps Engineers Handle Merge Conflicts

Although developers usually choose the correct code version, DevOps engineers must ensure smooth workflows, avoid pipeline failures, and help maintain merge quality.

### Steps to Resolve a Conflict:

1. Run merge:

```bash
git merge dev
```

2. Git reports conflicts.
3. Open conflicting file to see:

```txt
<<<<<<< HEAD
Your branch changes
=======
Incoming (dev) branch changes
>>>>>>> dev
```

4. Choose:

* Keep HEAD changes
* Keep incoming changes
* Combine both

5. Mark resolved:

```bash
git add <file>
```

6. Commit merge:

```bash
git commit
```

---

# Revert and Reset

## **Revert**

Used to undo a single commit *without* deleting history.

```bash
git log --oneline
git revert <commit-id>
```

Revert creates a *new commit*.

---

## **Reset (Dangerous)**

Used to delete commit history. Common when sensitive data is accidentally committed.

### Types of Reset

#### **Soft Reset**

Keeps changes staged.

```bash
git reset --soft <commit-id>
```

#### **Mixed Reset**

Keeps changes but unstages them.

```bash
git reset --mixed <commit-id>
```

#### **Hard Reset**

Deletes commits *and* local changes.

```bash
git reset --hard <commit-id>
```

---

# Merge and Rebase

## **Merge**

Used to bring changes from one branch into another.

```bash
git checkout master
git merge dev
```

### Merge Behavior

* Preserves complete history
* Creates a **non-linear** commit structure

---

## **Rebase**

Rebase rewrites commit history and creates a **linear** sequence of commits.

Useful when working locally to keep a clean history.

---

# Rebase Visualization

![Rebase Diagram](https://github.com/user-attachments/assets/74f4bb01-9ba3-4457-8e94-67d0bb3d3cfe)

---

# Branching Strategy Diagram

![Branch Strategy](https://github.com/user-attachments/assets/c66ff030-e752-40ef-ad03-0644929b3c0a)

---

# Summary

* **Merge** → safer, preserves full history
* **Rebase** → cleaner, linear history
* **Revert** → undo one commit safely
* **Reset** → deletes history (use with caution)
* **Hotfix** → urgent production fix, merged back to production & dev

---
