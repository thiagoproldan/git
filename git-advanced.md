# 🚀 **Git Advanced**

This section explores advanced Git concepts, focusing on powerful operations like stashing, resetting, rebasing, tagging, and troubleshooting. These commands help you manage complex workflows, recover from mistakes, and optimize your version control processes.

## 📚 **Table of Contents**
1. 🌿 [**Branching and Merging**](#-branching-and-merging)
2. 🔗 [**Working with Remotes**](#-working-with-remotes)
3. 🗃️ [**Advanced Git Operations**](#-advanced-git-operations)
4. ⚙️ [**Reverting and Resetting Commits**](#-reverting-and-resetting-commits)
5. 🧩 [**Rebasing**](#-rebasing)
6. 🏷️ [**Tagging and Releases**](#-tagging-and-releases)
7. 🛠️ [**Troubleshooting and Tips**](#-troubleshooting-and-tips)
8. 🔍 [**Investigating Changes**](#-investigating-changes)
9. 🛡️ [**Restoring and Reverting**](#-restoring-and-reverting)
10. 🌐 [**References and Resources**](#-references-and-resources)

## 🌿 **Branching and Merging**

### 🌱 **Managing Branches**
- Rename the current branch to `main`:
```
git branch -M main
```
- List all local branches:
```
git branch
```
- Rename a branch:
```
git branch -m <old-branch-name> <new-branch-name>
```
- Create a new branch:
```
git branch <new-branch>
```
- Switch to a specific branch:
```
git switch <branch>
```
- Create and switch to a new branch:
```
git switch -c <new-branch>
```

### 🔄 **Merging Changes**
- Merge changes from a specific branch into the current branch:
```
git merge <branch>
```

### 🗑️ **Deleting Branches**
- Delete a branch:
```
git branch -d <branch>
```
- Force delete a branch (even if unmerged):
```
git branch -D <branch>
```

## 🔗 **Working with Remotes**

### 🌍 **Remote Repository**
- Display URLs of remote repositories:
```
git remote -v
```
- Add a remote repository:
```
git remote add origin <repository-url>
```
- Rename a remote repository:
```
git remote rename <old-name> <new-name>
```
- List remote repositories:
```
git remote
```

### ⬆️ **Pushing and Pulling Changes**
- Fetch and integrate changes from the remote repository:
```
git pull
```
- Push the current branch to the remote repository:
```
git push
```
- Delete a remote branch:
```
git push origin --delete <branch>
```

## 🗃️ **Advanced Git Operations**

### 📦 **Stashing Changes**
- Temporarily save changes:
```
git stash
```
- List all stashes:
```
git stash list
```
- Apply and remove the latest stash:
```
git stash pop
```
- Apply a specific stash:
```
git stash apply <stash@{index}>
```
- Clear all stashes:
```
git stash clear
```

## ⚙️ **Reverting and Resetting Commits**
- Reset to a commit (keep changes):
```
git reset --soft <commit-id>
```
- Reset to a commit (discard changes):
```
git reset --hard <commit-id>
```
- Undo changes with a new commit:
```
git revert <commit-id>
```

## 🧩 **Rebasing**
- Reapply commits on top of another branch:
```
git rebase <branch>
```

## 🏷️ **Tagging and Releases**
- List all tags:
```
git tag
```
- Create an annotated tag:
```
git tag -a <tag-name> -m "Tag message"
```
- Push tags to remote:
```
git push origin --tags
```
   
## 🛠️ **Troubleshooting and Tips**
- View status of changes:
```
git status
```
- Show changes between commits:
```
git diff <commit-id>..<commit-id>
```

## 🔍 **Investigating Changes**
- Apply changes from a specific commit:
```
git cherry-pick <commit-id>
```
- Show who modified each line of a file:
```
git blame <file>
```
- Display commit details:
```
git show <commit-id>
```

## 🛡️ **Restoring and Reverting**
- Restore files to the last committed state:
```
git restore <file>
```
- Unstage a file but keep changes:
```
git restore --staged <file>
```

---

## 🌐 **References and Resources**
- [Visualizing Git](https://git-school.github.io/visualizing-git/)
- [gitignore.io](https://gitignore.io)
- [GitHub Docs](https://docs.github.com/en)
- [Git Official Documentation](https://git-scm.com/doc)