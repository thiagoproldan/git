# 🚀 **Git Intermediate**

This section provides an in-depth look at intermediate-level Git commands and workflows. It covers topics such as branching, merging, working with remotes, and resolving conflicts, making it easier to collaborate effectively in team environments.

---

## 📚 **Table of Contents**
1. 🌿 [**Branching and Merging**](#-branching-and-merging)
2. 🔗 [**Working with Remotes**](#-working-with-remotes)
3. ⚔️ [**Resolving Merge Conflicts**](#-resolving-merge-conflicts)
4. 🏷️ [**Tagging and Releases**](#-tagging-and-releases)
5. 🍒 [**Cherry-Picking Changes**](#-cherry-picking-changes)
6. 🔍 [**Viewing and Comparing Changes**](#-viewing-and-comparing-changes)

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

- Push and set the upstream branch:
```
git push -u origin <branch>
```

- Delete a remote branch:
```
git push origin --delete <branch>
```

## ⚔️ **Resolving Merge Conflicts**

1. 🕵️ Identify conflicting files using:
```
git status
```

2. 📝 Open and edit the conflicting files to resolve conflicts.

3. ✅ Mark conflicts as resolved:
```
git add <file>
```

4. 📦 Commit the merge:
```
git commit
```

## 🏷️ **Tagging and Releases**

### 🏷️ **Managing Tags**
- List all tags in the repository:
```
git tag
```

- Create a lightweight tag:
```
git tag <tag-name>
```

- Create an annotated tag:
```
git tag -a <tag-name> -m "Tag message"
```

- Delete a local tag:
```
git tag -d <tag-name>
```

- Push a tag to the remote repository:
```
git push origin <tag-name>
```

---

## 🍒 **Cherry-Picking Changes**

- Apply changes from a specific commit to the current branch:
```
git cherry-pick <commit-id>
```

## 🔍 **Viewing and Comparing Changes**

### 🧐 **Viewing Changes**
- Show differences between working directory and staging area:
```
git diff
```

- Show changes between two commits:
```
git diff <commit-id>..<commit-id>
```

### 🔎 **Comparing Changes**
- Display detailed information about a specific commit:
```
git show <commit-id>
```

- Show the last modification for each line of a file:
```
git blame <file>
```

---

This guide provides intermediate Git users with the tools needed to manage branches, work with remotes, and handle more complex scenarios like resolving conflicts, tagging, and cherry-picking changes. For advanced topics, refer to the upcoming **"Git Advanced"** section. 🚀