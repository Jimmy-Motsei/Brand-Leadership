# 🚀 Git Cheat Sheet - Complete Reference Guide

*Your comprehensive offline guide to Git commands and workflows*

---

## 📋 Table of Contents
1. [Repository Setup](#-repository-setup)
2. [Checking Status & History](#-checking-status--history)
3. [Making Changes](#-making-changes)
4. [Branching](#-branching)
5. [Sharing & Syncing](#-sharing--syncing)
6. [Undoing Changes](#-undoing-changes)
7. [Viewing & Comparing](#-viewing--comparing)
8. [Tagging](#-tagging)
9. [File Operations](#-file-operations)
10. [Configuration](#-configuration)
11. [Common Workflows](#-common-workflows)
12. [Troubleshooting](#-troubleshooting)

---

## 🏗️ **Repository Setup**

| Command | What it does | Example |
|---------|-------------|---------|
| `git init` | Create new Git repository in current directory | `git init` |
| `git clone [url]` | Copy repository from remote to local | `git clone https://github.com/user/repo.git` |
| `git remote add origin [url]` | Connect local repo to remote repository | `git remote add origin https://github.com/user/repo.git` |
| `git remote -v` | View all remote repositories | `git remote -v` |
| `git remote remove [name]` | Remove a remote repository | `git remote remove origin` |

---

## 📊 **Checking Status & History**

| Command | What it does | Example |
|---------|-------------|---------|
| `git status` | Show current working directory status | `git status` |
| `git log` | Show detailed commit history | `git log` |
| `git log --oneline` | Show compact commit history | `git log --oneline` |
| `git log --graph` | Show commit history with branch graph | `git log --graph --oneline` |
| `git show [commit]` | Show detailed changes in specific commit | `git show abc123` |
| `git diff` | Show unstaged changes in working directory | `git diff` |
| `git diff --staged` | Show staged changes ready for commit | `git diff --staged` |
| `git diff HEAD` | Show all changes since last commit | `git diff HEAD` |

---

## 📝 **Making Changes**

| Command | What it does | Example |
|---------|-------------|---------|
| `git add [file]` | Stage specific file for commit | `git add index.html` |
| `git add .` | Stage all changes in current directory | `git add .` |
| `git add -A` | Stage all changes (including deletions) | `git add -A` |
| `git commit -m "message"` | Commit staged changes with message | `git commit -m "Add new feature"` |
| `git commit -am "message"` | Add & commit all tracked files | `git commit -am "Quick fix"` |
| `git commit --amend` | Modify the last commit | `git commit --amend -m "New message"` |

---

## 🔄 **Branching**

| Command | What it does | Example |
|---------|-------------|---------|
| `git branch` | List all local branches | `git branch` |
| `git branch -a` | List all branches (local + remote) | `git branch -a` |
| `git branch [name]` | Create new branch | `git branch feature` |
| `git checkout [branch]` | Switch to existing branch | `git checkout feature` |
| `git checkout -b [name]` | Create new branch and switch to it | `git checkout -b feature` |
| `git branch -M [name]` | Rename current branch | `git branch -M main` |
| `git branch -d [branch]` | Delete local branch | `git branch -d feature` |
| `git branch -D [branch]` | Force delete local branch | `git branch -D feature` |
| `git merge [branch]` | Merge branch into current branch | `git merge feature` |
| `git merge --abort` | Cancel merge in progress | `git merge --abort` |

---

## 📤 **Sharing & Syncing**

| Command | What it does | Example |
|---------|-------------|---------|
| `git push` | Push commits to remote repository | `git push` |
| `git push -u origin [branch]` | Push & set upstream for tracking | `git push -u origin main` |
| `git push origin [branch]` | Push specific branch to remote | `git push origin feature` |
| `git pull` | Pull and merge changes from remote | `git pull` |
| `git pull origin [branch]` | Pull from specific remote branch | `git pull origin main` |
| `git fetch` | Download changes from remote (no merge) | `git fetch` |
| `git fetch origin` | Fetch from specific remote | `git fetch origin` |

---

## ↩️ **Undoing Changes**

### Safe Methods (Recommended)
| Command | What it does | Example |
|---------|-------------|---------|
| `git revert [commit]` | **Safe**: Undo commit by creating new commit | `git revert abc123` |
| `git revert HEAD` | Revert the last commit | `git revert HEAD` |
| `git checkout -- [file]` | Restore file to last commit state | `git checkout -- index.html` |
| `git restore [file]` | Restore file to last commit (Git 2.23+) | `git restore index.html` |

### Dangerous Methods (Use with caution)
| Command | What it does | Example |
|---------|-------------|---------|
| `git reset --soft [commit]` | Undo commit, keep changes staged | `git reset --soft HEAD~1` |
| `git reset --mixed [commit]` | Undo commit, unstage changes | `git reset --mixed HEAD~1` |
| `git reset --hard [commit]` | **Dangerous**: Undo commit, lose all changes | `git reset --hard HEAD~1` |
| `git reset --hard HEAD` | Reset to last commit, lose all changes | `git reset --hard HEAD` |

---

## 🔍 **Viewing & Comparing**

| Command | What it does | Example |
|---------|-------------|---------|
| `git show [commit]` | Show detailed changes in commit | `git show abc123` |
| `git show [commit]:[file]` | Show file content at specific commit | `git show abc123:index.html` |
| `git diff [commit1] [commit2]` | Compare changes between two commits | `git diff abc123 def456` |
| `git diff HEAD~1` | Compare current with previous commit | `git diff HEAD~1` |
| `git diff [branch1]..[branch2]` | Compare two branches | `git diff main..feature` |
| `git blame [file]` | Show who changed each line in file | `git blame index.html` |

---

## 🏷️ **Tagging**

| Command | What it does | Example |
|---------|-------------|---------|
| `git tag` | List all tags | `git tag` |
| `git tag [name]` | Create lightweight tag | `git tag v1.0` |
| `git tag -a [name] -m "message"` | Create annotated tag with message | `git tag -a v1.0 -m "Version 1.0"` |
| `git tag -d [name]` | Delete local tag | `git tag -d v1.0` |
| `git push origin [tag]` | Push tag to remote | `git push origin v1.0` |
| `git push origin --tags` | Push all tags to remote | `git push origin --tags` |

---

## 📁 **File Operations**

| Command | What it does | Example |
|---------|-------------|---------|
| `git rm [file]` | Remove file from Git tracking | `git rm oldfile.txt` |
| `git rm --cached [file]` | Remove file from Git but keep locally | `git rm --cached file.txt` |
| `git mv [old] [new]` | Rename/move file | `git mv oldname.txt newname.txt` |
| `git ls-files` | List all tracked files | `git ls-files` |
| `git ls-files --others` | List untracked files | `git ls-files --others` |
| `git ls-files --ignored` | List ignored files | `git ls-files --ignored` |

---

## ⚙️ **Configuration**

| Command | What it does | Example |
|---------|-------------|---------|
| `git config --global user.name "Name"` | Set your global username | `git config --global user.name "John Doe"` |
| `git config --global user.email "email"` | Set your global email | `git config --global user.email "john@example.com"` |
| `git config --list` | Show all configuration | `git config --list` |
| `git config --global core.editor "editor"` | Set default editor | `git config --global core.editor "code"` |
| `git config --global init.defaultBranch main` | Set default branch name | `git config --global init.defaultBranch main` |

---

## 🔄 **Common Workflows**

### Daily Development Workflow
```bash
# 1. Check what's changed
git status

# 2. Stage your changes
git add .

# 3. Commit with meaningful message
git commit -m "Add new feature: user authentication"

# 4. Push to remote
git push
```

### Starting a New Feature
```bash
# 1. Create and switch to new branch
git checkout -b feature/user-login

# 2. Make your changes
# ... edit files ...

# 3. Stage and commit
git add .
git commit -m "Add user login functionality"

# 4. Push new branch to remote
git push -u origin feature/user-login
```

### Merging a Feature Branch
```bash
# 1. Switch to main branch
git checkout main

# 2. Pull latest changes
git pull origin main

# 3. Merge feature branch
git merge feature/user-login

# 4. Push merged changes
git push origin main

# 5. Delete feature branch (optional)
git branch -d feature/user-login
git push origin --delete feature/user-login
```

### Undoing Mistakes
```bash
# Undo last commit (safe)
git revert HEAD

# Undo uncommitted changes to a file
git checkout -- filename.txt

# Undo staged changes
git reset HEAD filename.txt

# Completely reset to last commit (dangerous!)
git reset --hard HEAD
```

### Viewing History
```bash
# See recent commits
git log --oneline -10

# See changes in last commit
git show HEAD

# See who changed what in a file
git blame filename.txt

# Compare with previous version
git diff HEAD~1
```

---

## 🚨 **Troubleshooting**

### Common Issues & Solutions

#### "Your branch is ahead of 'origin/main' by X commits"
```bash
# Push your commits to remote
git push origin main
```

#### "Your branch is behind 'origin/main' by X commits"
```bash
# Pull latest changes
git pull origin main
```

#### Merge Conflicts
```bash
# 1. Git will show conflicted files
git status

# 2. Edit conflicted files manually
# 3. Stage resolved files
git add filename.txt

# 4. Complete the merge
git commit
```

#### "Permission denied" when pushing
```bash
# Check your remote URL
git remote -v

# If using HTTPS, you may need to authenticate
# If using SSH, check your SSH keys
```

#### "fatal: refusing to merge unrelated histories"
```bash
# Force merge when histories don't match
git pull origin main --allow-unrelated-histories
```

---

## 💡 **Pro Tips**

1. **Commit Frequently**: Make small, focused commits with clear messages
2. **Use Branches**: Create branches for new features to keep main clean
3. **Write Good Messages**: Use present tense and be descriptive
4. **Pull Before Push**: Always pull latest changes before pushing
5. **Use .gitignore**: Ignore files that shouldn't be tracked
6. **Backup Important Work**: Use `git revert` instead of `git reset` when possible

---

## 📚 **Learning Resources**

- **Official Git Documentation**: https://git-scm.com/doc
- **GitHub Guides**: https://guides.github.com/
- **Git Visualizer**: https://git-school.github.io/visualizing-git/
- **Git Cheat Sheet (GitHub)**: https://education.github.com/git-cheat-sheet-education.pdf

---

*This cheat sheet was created for offline reference. Keep it handy for quick Git command lookups!*

**Last Updated**: August 2025
**Version**: 1.0
