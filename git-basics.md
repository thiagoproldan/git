# 🚀 **Git Basics**

**Git** is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
It allows multiple developers to work on a project simultaneously, without interfering with each other's work.

Git tracks changes in files and directories, enabling teams to revert back to previous versions, compare changes over time, and merge updates from different branches. It's widely used for source code management in software development but can manage any set of files or documents.

For detailed instructions on Git commands, refer to the official documentation available [here](https://git-scm.com/doc).

## 📑 **Table of Contents**
1. 🛟 [**Getting Help**](#getting-help)
2. 🛠️ [**Setting Up Git**](#setting-up-git)
3. 🚀 [**Basic Git Commands**](#basic-git-commands)

## 🛟 **Getting Help**

When using Git commands, you can utilize the `--help` or `-h` options to obtain detailed information and usage instructions directly from the command line. These options provide essential guidance on how to correctly use a specific command, its available options, and examples of its usage.

### 📜 **Using `--help`**
To get help for a specific Git command, append `--help` at the end of the command. For example:
```
git <command> --help
```
This command displays detailed information about the Git command, including its syntax, options, and usage examples.

### ⚡ **Using `-h`**
Alternatively, you can use `-h` as a shorthand for `--help`. For instance:
```
git <command> -h
```
This command provides concise help information for the Git command, helping you understand its functionality and how to apply it effectively in your workflow.

## 🛠️ **Setting Up Git**

### 🔧 **Configuring User Information**
Sets the global username for Git commits:
```
git config --global user.name "Your Name"
```
Displays the current Git username:
```
git config user.name
```

Sets the global email for Git commits:
```
git config --global user.email "your@email.com"
```
Displays the current Git email:
```
git config user.email
```

### 📝 **Setting the Default Text Editor**
Sets the global default text editor for Git:
```
git config --global core.editor "editor path"
```
Displays the current default text editor for Git:
```
git config core.editor
```

## 🚀 **Basic Git Commands**

### 🆕 **Initializing a Repository**
Initializes a new Git repository:
```
git init
```

### 📥 **Cloning a Repository**
Clones a remote repository to the local machine:
```
git clone <repository-url>
```

### 📌 **Staging Changes**
Stages a specific file for commit:
```
git add <file-name>
```
Stages all changes in the current directory for commit:
```
git add .
```

### ✅ **Committing Changes**
Commits the staged changes with a message:
```
git commit -m "Commit Message"
```

### 🔍 **Viewing Commit History**
Shows the commit history:
```
git log
```
Shows the commit history in a condensed format:
```
git log --oneline
```

Shows the commit history with a custom format:
```
git log --format="%parameter1 %parameter2 ..."
```
```
git log --pretty="%parameter1 %parameter2 ..."
```

📊 **Table of `--format` Parameters**
| Placeholder | Description                 |
| ----------- | --------------------------- |
| %H          | Full commit hash            |
| %h          | Abbreviated commit hash     |
| %an         | Author name                 |
| %ae         | Author email                |
| %ad         | Author date                 |
| %ar         | Author date, relative       |
| %cn         | Committer name              |
| %ce         | Committer email             |
| %cd         | Committer date              |
| %cr         | Committer date, relative    |
| %s          | Commit message              |
| %b          | Commit body                 |
| %D          | Refs associated with commit |
| %Cred       | Switch color to red         |
| %Cgreen     | Switch color to green       |
| %Cblue      | Switch color to blue        |
| %Creset     | Reset color                 |

Shows the commit history with the differences introduced in each commit:
```
git log -p
```

Displays the commit history in a graphical representation showing branching and merging:
```
git log --graph
```

---

For more advanced commands and workflows, refer to the upcoming **"Git Intermediate"** and **"Git Advanced"** sections of this repository. 🌟