# 📌 Git Branching, Collaboration & Stash – Basics

---

## 🔹 1. Git Branching – Overview

**Branching** allows multiple developers to work on different features or fixes without affecting the main codebase.

### 🌳 Branch Structure (Concept)

```
main / master
│
├── feature-login
├── feature-payment
└── bugfix-ui
```

👉 `main` / `master` → stable production-ready code
👉 `feature/*` → new features
👉 `bugfix/*` → fixes

---

## 🔹 2. Basic Branch Commands

### 📍 List branches

```bash
git branch
```

### 📍 Create a new branch

```bash
git branch feature
```

### 📍 Switch to a branch

```bash
git checkout feature
```

---

## 🔹 3. Working on a Feature Branch

### ✏️ Make code changes, then:

```bash
git add .
git commit -m "message"
git push origin feature
```

👉 Changes are pushed **only to the feature branch**, not `main`.

---

## 🔹 4. Collaboration Workflow

### 📥 Clone repository

```bash
git clone https://github.com/atulkamble/myrepo.git
cd myrepo
```

### 🌿 Create your own branch

```bash
git branch atul
git branch
git checkout atul
```

### 📝 Create / edit files

```bash
touch atul.txt
nano atul.txt
cat atul.txt
```

### 📤 Commit and push

```bash
git add .
git commit -m "coded by atul"
git push origin atul
```

---

## 🔹 5. Sync With Remote Repository

### 🔄 Pull latest changes

```bash
git pull
```

### 🌍 List all branches (local + remote)

```bash
git branch -a
```

---

## 🔹 6. Git Logs (History)

### 📜 Detailed log

```bash
git log
```

### 📄 One-line summary

```bash
git log --oneline
```

---

## 🔹 7. Git Stash (Temporary Save)

Used when you want to **save changes without committing**.

### 📝 Modify a file

```bash
nano hello.txt
cat hello.txt
```

### 📦 Stash changes

```bash
git add hello.txt
git stash
```

### 📋 View stash list

```bash
git stash list
```

### 🔄 Apply stash

```bash
git stash apply stash@{0}
cat hello.txt
```

---

## 🔹 8. Cherry-Pick (Selective Commit)

Used to **copy a specific commit** from one branch to another.

```bash
git cherry-pick <commit-id>
```

👉 Helpful when you want **only one commit**, not the full branch.

---

## 🔹 9. Docker Desktop (Tool)

Download Docker Desktop for local container development:

🔗 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

---

## ✅ Key Points to Remember

* Always create a **separate branch** for your work
* Never commit directly to `main`
* Use `stash` for temporary changes
* Use `cherry-pick` for selective commits
* Pull frequently to avoid conflicts

---
