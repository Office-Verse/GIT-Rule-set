# 🧠 Office Metaverse – Git Workflow Guide

Welcome to the Git workflow guide for our development team. This document will help you set up Git, follow best practices, and collaborate efficiently using GitHub.

---

## 🛠️ 1. Set Up Git Globally

In your terminal, configure your identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Optional (recommended):

```bash
git config --global core.editor "code --wait"     # Set VS Code as Git editor
git config --global init.defaultBranch main        # Set default branch as main
```

Check your settings:

```bash
git config --list
```

---

## ⬇️ 2. Clone Repository and Add Remotes

```bash
git clone https://github.com/Office-Verse/Office-Metaverse.git
cd Office-Metaverse
```

Check remote:

```bash
git remote -v
```

If you're working on a fork:

```bash
git remote add upstream https://github.com/Office-Verse/Office-Metaverse.git
```

---

## 🌱 3. Creating Feature Branches (The Right Way)

🚨 **Always branch from the latest main**:

```bash
git checkout main
git pull origin main
git checkout -b feature/your-task-name
```

Push your branch (first time only):

```bash
git push --set-upstream origin feature/your-task-name
```

---

## 🔁 4. Staying Synced with `main`

Before opening or merging a PR:

### Option 1: Rebase (cleaner history)

```bash
git fetch origin
git rebase origin/main
```

### Option 2: Merge (safer for beginners)

```bash
git fetch origin
git merge origin/main
```

Resolve conflicts if needed, then push:

```bash
git push
```

---

## 🔃 5. Pull Request Flow (PR)

1. Create a **pull request (PR)** from your branch to `main`
2. Get required approvals (1 required)
3. GitHub will **block merge** unless:
   - All required reviewers approved
   - All GitHub Actions/tests pass
   - Branch is up-to-date with `main`

---

## 🧼 6. Cleaning Up Old Branches

After a PR is merged:

```bash
git checkout main
git pull origin main
git branch -d feature/your-task-name
git push origin --delete feature/your-task-name  # Optional
```

---

## ✅ 7. Best Practices

- Use meaningful commit messages
- Small, focused PRs are better than huge ones
- Use `feature/`, `bugfix/`, `hotfix/`, `doc/` prefix in branch names
- Never push directly to `main`
- Use draft PRs if your feature is still in progress

---

## ⚡ 8. Optional Git Aliases (Productivity Boost)

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.st status
git config --global alias.lg "log --oneline --graph --all"
```

Then you can do:

```bash
git co main
git lg
```

---

## 📌 Reference Commands

```bash
# Create branch from main
git checkout main
git pull origin main
git checkout -b feature/name

# Push
git push --set-upstream origin feature/name

# Rebase or Merge
git fetch origin
git rebase origin/main  # or: git merge origin/main

# Create PR → Get review → Merge
```

---

Happy collaborating! 👨‍💻👩‍💻  
For help, contact your GitHub lead or open a discussion in the repository.

# Issue Setup

This video highlights how you are going to work with github Issues

https://www.youtube.com/watch?v=TKJ4RdhyB5Y


