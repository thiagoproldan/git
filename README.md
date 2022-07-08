Install Git [Using Winget Tool - Windows Package Manager]
---

Install [winget tool](https://docs.microsoft.com/en-us/windows/package-manager/winget/) if you don't already have it, then type this command in command prompt or Powershell.

```
 winget install --id Git.Git -e --source winget
```

Configure Git [Username]
---

Type these commands in Git Bash to configure username.

```
 git config --global user.name "Thiago Roldan"
 git config user.name
```

Configure Git [E-Mail]
---

Type these commands in Git Bash to configure e-mail.

```
 git config --global user.email "thiago.roldan@outlook.com"
 git config user.email
```

Configure Git [Core Editor]
---

Type these commands in Git Bash to configure core editor.

```
 git config --global core.editor "C:\Program Files\Microsoft VS Code\Code.exe"
 git config core.editor
```

Create System Variables
---

Add vscode path in environment variables.

- [ ] Press Win + R and type:
```
SystemPropertiesAdvanced
```
- [ ] Click in 'Environment Variables'.
- [ ] In the section 'System Variables' click in 'New'.
- [ ] Set the 'Variable Name' to:
```
code
```
- [ ] Set the 'Variable Value' to:
```
C:\Program Files\Microsoft VS Code\Code.exe
```
- [ ] In Git Bash test this command:
```
code .
```
