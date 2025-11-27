# Global Information Tracker (GIT)

Git is a powerful **distributed version control system (VCS)** used to track changes in your source code, collaborate with teams, and maintain a complete project history.

---

## 🧰 What Git Does
- Tracks code changes over time  
- Allows multiple developers to work simultaneously  
- Maintains versions and history of the entire project  
- Helps sync your local code with remote repositories like GitHub  

---

## 🔁 Git Clone vs Git Fork

### **Git Clone**
Cloning means downloading a remote repository to your **local system**.

```
git clone <repo-url>
```

### **Git Fork**
Forking creates a **copy of someone else's repository into your GitHub account** (remote-to-remote copy).

Useful when:
- You don't have access to the original repo
- You want to contribute via pull requests

---

## 🔗 Git Remote Commands

### **Check existing remotes**
```
git remote -v
```

Shows the remote repository URLs from where your local project is connected.

---

## 🔐 Why Not Use Access Tokens Every Time?
Using personal access tokens manually in the URL:
```
git remote set-url origin https://<token>@github.com/User/repo.git
```
This is considered a **temporary workaround**, not a secure long-term method.

You should NOT keep updating the token in the remote URL every time.  
Instead, use **SSH Authentication**.

---

## 🔑 SSH Authentication (Industry Standard)

SSH provides a secure and password-less way to push code.

### **1. Navigate to SSH Folder**
```
cd ~/.ssh/
```

### **2. Generate SSH Keys**
```
ssh-keygen
```

This creates:
- `id_rsa` → Private Key (keep secure on your machine)
- `id_rsa.pub` → Public Key (uploaded to GitHub)

### **How SSH Works**
- Local system holds **private key**
- GitHub stores your **public key**
- Together they authenticate without password/token

### **Set Remote URL to SSH**
```
git remote set-url origin git@github.com:Username/repo.git
```

Then simply push:
```
git push origin master
```

---

## 🔄 Git Pull (Remote → Local)

To update your local repository with the latest remote changes:
```
git pull origin master
```

---

## 🔍 Difference: Git Clone vs Git Pull

| Action | Purpose | Result |
|--------|---------|--------|
| **clone** | First-time download of repo | Creates a full local copy of the remote repository |
| **pull** | Bring new updates from remote | Only updates changed files |

---

## Summary

- **Clone** = Download entire repo for the first time  
- **Pull** = Fetch updates  
- **SSH** = Secure and professional way for GitHub authentication  
- **Remote URLs** show where your code comes from  
- **Fork** = Copy repo from remote to your GitHub account  

---

Prepared professionally for GitHub documentation.
