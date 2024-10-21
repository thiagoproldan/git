<details open>
<summary>en-US</summary>

# GIT

**Git** is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
It allows multiple developers to work on a project simultaneously, without interfering with each other's work.

Git tracks changes in files and directories, enabling teams to revert back to previous versions, compare changes over time, and merge updates from different branches.
It's widely used for source code management in software development, but it can manage any set of files or documents.

For detailed instructions on Git commands, refer to the official documentation available [here](https://git-scm.com/doc).

## Help

When using Git commands, you can utilize the `--help` or `-h` options to obtain detailed information and usage instructions directly from the command line. These options provide essential guidance on how to correctly use a specific command, its available options, and examples of its usage.

### **Using `--help`**

To get help for a specific Git command, append --help at the end of the command. For example:
```
git <command> --help
```
This command displays detailed information about the git command, including its syntax, options, and usage examples.

### **Using `-h`**

Alternatively, you can use `-h` as a shorthand for `--help`. For instance:
```
git <command> -h
```
This command provides concise help information for the git command, helping you understand its functionality and how to apply it effectively in your workflow.

### Notes:
- The `--help` and `-h` options are invaluable for both beginners and experienced users alike, offering quick access to command documentation without needing to leave the terminal.
- Experimenting with these options is encouraged to familiarize yourself with Git's capabilities and enhance your efficiency when working with version control.

By utilizing `--help` or `-h`, you can efficiently access documentation and master the usage of Git commands directly from your command line interface.

## Setting Up Git

### Configuring user information
Sets the global username for Git commits and displays the current Git username:
```
git config --global user.name "Your Name"
git config user.name
```

Sets the global email for Git commits and displays the current Git email:
```
git config --global user.email "your@email.com"
git config user.email
```

### Setting the default text editor
Sets the global default text editor for Git and displays the current default text editor for Git:
```
git config --global core.editor "editor path"
git config core.editor
```

### Generating SSH keys
To set up secure authentication on GitHub, it's crucial to generate SSH keys. Learn how to configure yours by following the steps outlined [here](ssh-key.md).

## Basic Git Commands

### Initializing a repository
Initializes a new Git repository:
```
git init
```

### Cloning a repository
Clones a remote repository to the local machine:
```
git clone <github repository link>
```

### Staging changes
Stages a specific file for commit:
```
git add <file name>
```

Stages all changes in the current directory for commit:
```
git add .
```

### Committing changes
Commits the staged changes with a message:
```
git commit -m "Commit Message"
```

Changes the last commit's message:
```
git commit --amend -m "New commit message"
```

### Viewing commit history
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

Table of --format Parameters
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

## Branching and Merging

### Managing branches
Renames the current branch to main:
```
git branch -M main
```

Lists all local branches in the repository:
```
git branch
```

Renames a branch from `<old branch name>` to `<new branch name>`:
```
git branch -m <old branch name> <new branch name>
```

Creates a new branch named `<new branch>`:
```
git branch <new branch>
```

Switches to the specified branch:
```
git checkout <branch name>
```

Correct command to create and switch to a new branch:
```
git checkout -b <new branch>
```

Switches to the specified branch. Modern alternative to `git checkout <branch>`:
```
git switch <branch>
```

Creates and switches to a new branch. Modern alternative to `git checkout -b <new branch>`:
```
git switch -c <new branch>
```

### Merging changes

Merges changes from a specific branch (<branch>) into the current branch of the Git repository:
```
git merge <branch>
```

### Deleting branches

Deletes the specified branch, ensuring it has been fully merged into its upstream branch:
```
git branch -d <branch to delete>
```

Force deletes the specified branch, even if it has unmerged changes:
```
git branch -D <branch to delete>
```

## Working with Remotes

### Remote repository
Displays the URLs of remote repositories:
```
git remote -v
```

Adds a remote repository link:
```
git remote add origin <github repository link>
```

Renames the remote repository from origin to github:
```
git remote rename origin github: 
```

Lists the names of remote repositories.
```
git remote
```

### Pushing and pulling changes
Fetches changes from the remote repository and integrates them into the current local branch:
```
git pull
``` 

Fetches changes from the remote main branch and integrates them into the current local branch:
```
git pull origin main
``` 

Pushes the current branch to the remote repository:
```
git push
``` 

Pushes the main branch to the remote repository:
```
git push origin main
``` 

Pushes the local main branch to the remote repository and sets it as the upstream branch:
```
git push -u origin main
``` 

Pushes the tag v0.1.0 to the remote repository:
```
git push origin v0.1.0
``` 

Pushes all tags to the remote repository:
```
git push origin --tags
``` 

### Managing remote branches
Deletes the specified branch from the remote repository:
```
git push origin :<branch name>
```

## Advanced Git Operations

### Stashing changes
Applies stashed changes to the working directory and removes them from the stash:
```
git stash pop
```

Applies changes from a specific stash in the stash list:
```
git stash apply <stash@{index}>
```

Lists all stashed changesets:
```
git stash list
```

Removes all stashed entries:
```
git stash clear
```

Saves the current state of the working directory with an optional message:
```
git stash push -m "Stash message"
```

Temporarily shelves changes so you can work on a different task:
```
git stash
```

### Reverting and resetting commits

Resets the current branch to the specified commit ID, keeping changes in the staging area:
```
git reset --soft <commit id> 
```

Resets the current branch to the specified commit ID, discarding all changes:
```
git reset --hard <commit id>
```

Moves the current branch tip to the specified commit ID, keeping changes staged:
```
git reset --soft <commit id>
```

Moves the current branch tip to the specified commit ID, discarding all changes in the working directory and staging area:
```
git reset --hard <commit id>
```

Creates a new commit that undoes the changes introduced by the specified commit ID:
```
git revert <commit id>
```

### Rebasing
Reapplies commits on top of the specified branch's current commit:
```
git rebase <branch>
```

## Tagging and Releases

### Creating and managing tags
Lists all tags in the repository:
```
git tag
```

Creates a new lightweight tag named v0.1.0 at the current commit:
```
git tag v0.1.0
```

Creates a lightweight tag v0.1.1 pointing to the current HEAD commit:
```
git tag v0.1.1 HEAD
```

Creates a lightweight tag v0.1.1 pointing to the specified commit ID:
```
git tag v0.1.1 <commit id>
```

Deletes the local tag v0.1.1:
```
git tag -d v0.1.1
```

Creates an annotated tag v0.1.1 with a message:
```
git tag -a v0.1.1 -m "Tag message"
```

Verifies the signature of the tag v0.1.1:
```
git tag -v v0.1.1
```

### Working with GitHub releases
GitHub > Releases > Create a new release : Choose a Tag > ...

## Troubleshooting and Tips

### Viewing changes

Displays differences between the working directory and the staging area.
When no commit ID is specified, it shows the changes between the working directory and the staging area:
```
git diff
```

Shows differences between two specified commits:
```
git diff <commit id>..<commit id>
```

### Resolving merge conflicts

### Useful shortcuts and commands

Displays the working directory and staging area status:
```
git status
```

## Investigating Changes

### Cherry-Picking Changes.

Applies the changes introduced by the specified commit ID to the current branch:
```
git cherry-pick <commit id>
```

### Blaming
Shows who last modified each line of a file and when:
```
git blame <file name>
```

### Viewing changes
Displays detailed information about a specific commit:
```
git show
```
Shows changes introduced by the specified commit ID:
```
git show <commit id>
```

## Restoring and Reverting

### Restoring Files
Restores specified files in the working directory to their last committed state:
```
git restore <file name>
```

Restores all files in the working directory to their last committed state:
```
git restore .
```

Unstages the specified file, but retains changes in the working directory:
```
git restore --staged <file name>
```

Restores a file to the state it was in at the specified commit:
```
git restore --source=<commit id> <file name>:
```

Restores a file to its state in the last commit:
```
git restore --source=HEAD <file name>
```

## References and Resources

### Online resources for learning Git
- [visualizing.git](https://git-school.github.io/visualizing-git/)
- [gitignore.io](https://gitignore.io)
- [gist.github.com](https://gist.github.com)
- [git-scm.com/doc](https://git-scm.com/doc)

</details>

---

<details>
<summary>pt-BR</summary>

# GIT

**Git** é um sistema de controle de versão distribuído projetado para lidar com projetos pequenos a muito grandes com rapidez e eficiência.
Ele permite que vários desenvolvedores trabalhem em um projeto simultaneamente, sem interferir no trabalho uns dos outros.

O Git rastreia alterações em arquivos e diretórios, permitindo que equipes voltem a versões anteriores, comparem alterações ao longo do tempo e mesclam atualizações de diferentes branches.
É amplamente utilizado para gerenciamento de código-fonte no desenvolvimento de software, mas pode gerenciar qualquer conjunto de arquivos ou documentos.

Para instruções detalhadas sobre os comandos do Git, consulte a documentação oficial disponível [aqui](https://git-scm.com/doc).

## Ajuda

Ao usar comandos do Git, você pode utilizar as opções `--help` ou `-h` para obter informações detalhadas e instruções de uso diretamente da linha de comando. Essas opções fornecem orientações essenciais sobre como usar corretamente um comando específico, suas opções disponíveis e exemplos de uso.

### **Usando `--help`**

Para obter ajuda para um comando Git específico, adicione --help ao final do comando. Por exemplo:
```
git <comando> --help
```
Este comando exibe informações detalhadas sobre o comando git, incluindo sua sintaxe, opções e exemplos de uso.

### **Usando `-h`**

Alternativamente, você pode usar `-h` como um atalho para `--help`. Por exemplo:
```
git <comando> -h
```

Este comando fornece informações concisas de ajuda para o comando git, ajudando você a entender sua funcionalidade e como aplicá-lo efetivamente em seu fluxo de trabalho.

### Notas:
- As opções `--help` e `-h` são inestimáveis tanto para iniciantes quanto para usuários experientes, oferecendo acesso rápido à documentação do comando sem precisar sair do terminal.
- Experimentar com essas opções é encorajado para se familiarizar com as capacidades do Git e aumentar sua eficiência ao trabalhar com controle de versão.

Ao utilizar `--help` ou `-h`, você pode acessar eficientemente a documentação e dominar o uso dos comandos do Git diretamente da sua interface de linha de comando.

## Configurando o Git

### Configurando informações do usuário
Define o nome de usuário global para commits do Git e exibe o nome de usuário Git atual:
```
git config --global user.name "Seu Nome"
git config user.name
```

Define o e-mail global para commits do Git e exibe o e-mail Git atual:
```
git config --global user.email "your@email.com"
git config user.email
```

### Configurando o editor de texto padrão
Define o editor de texto padrão global para o Git e exibe o editor de texto padrão atual para o Git:
```
git config --global core.editor "caminho do editor"
git config core.editor
```

### Gerando chaves SSH
Para configurar autenticação segura no GitHub, é crucial gerar chaves SSH. Aprenda a configurar as suas seguindo os passos descritos [aqui](ssh-key.md).

## Comandos Básicos do Git

### Inicializando um repositório
Inicializa um novo repositório Git:
```
git init
```

### Clonando um repositório
Clona um repositório remoto para a máquina local:
```
git clone <link do repositório do github>
```

### Adicionando alterações ao stage
Adiciona um arquivo específico para commit:
```
git add <nome do arquivo>
```

Adiciona todas as alterações no diretório atual para commit:
```
git add .
```

### Commitando alterações
Faz commit das alterações em stage com uma mensagem:
```
git commit -m "Mensagem do Commit"
```

Altera a mensagem do último commit:
```
git commit --amend -m "Nova mensagem de commit"
```

### Visualizando o histórico de commits

Mostra o histórico de commits:
```
git log
```

Mostra o histórico de commits de forma condensada:
```
git log --oneline
```

Mostra o histórico de commits com um formato personalizado:
```
git log --format="%parâmetro1 %parâmetro2 ..."
```
```
git log --pretty="%parâmetro1 %parâmetro2 ..."
```

Tabela de Parâmetros de --format
| Placeholder | Descrição                   |
| ----------- | --------------------------- |
| %H          | Hash completo do commit     |
| %h          | Hash abreviado do commit    |
| %an         | Nome do autor               |
| %ae         | Email do autor              |
| %ad         | Data do autor               |
| %ar         | Data do autor, relativa     |
| %cn         | Nome do committer           |
| %ce         | Email do committer          |
| %cd         | Data do committer           |
| %cr         | Data do committer, relativa |
| %s          | Mensagem do commit          |
| %b          | Corpo do commit             |
| %D          | Refs associadas ao commit   |
| %Cred       | Muda a cor para vermelho    |
| %Cgreen     | Muda a cor para verde       |
| %Cblue      | Muda a cor para azul        |
| %Creset     | Reseta a cor                |

Mostra o histórico de commits com as diferenças introduzidas em cada commit:
```
git log -p
```

Exibe o histórico de commits em uma representação gráfica mostrando ramificação e mesclagem:
```
git log --graph
```

## Branches e Merging

### Gerenciando branches
Renomeia o branch atual para main:
```
git branch -M main
```

Lista todos os branches locais no repositório:
```
git branch
```

Renomeia um branch de `<nome do branch antigo>` para `<novo nome do branch>`:
```
git branch -m <nome do branch antigo> <novo nome do branch>
```

Cria um novo branch chamado `<novo branch>`:
```
git branch <novo branch>
```

Muda para o branch especificado:
```
git checkout <nome do branch>
```

Comando correto para criar e mudar para um novo branch:
```
git checkout -b <novo branch>
```

Muda para o branch especificado. Alternativa moderna para `git checkout <branch>`:
```
git switch <branch>
```

Cria e muda para um novo branch. Alternativa moderna para `git checkout -b <novo branch>`:
```
git switch -c <novo branch>
```

### Mesclando alterações

Mescla alterações de um branch específico (<branch>) no branch atual do repositório Git:
```
git merge <branch>
```

### Deletando branches

Deleta o branch especificado, garantindo que ele tenha sido totalmente mesclado em seu branch upstream:
```
git branch -d <branch a ser deletado>
```

Deleta forçadamente o branch especificado, mesmo que ele tenha alterações não mescladas:
```
git branch -D <branch a ser deletado>
```

## Trabalhando com Remotos

### Repositório remoto
Exibe os URLs dos repositórios remotos:
```
git remote -v
```

Adiciona um link de repositório remoto:
```
git remote add origin <link do repositório do github>
```

Renomeia o repositório remoto de origin para github:
```
git remote rename origin github: 
```

Lista os nomes dos repositórios remotos.
```
git remote
```

### Enviando e puxando alterações
Busca alterações do repositório remoto e as integra no branch local atual:
```
git pull
```

Busca alterações do branch main remoto e as integra no branch local atual:
```
git pull origin main
```

Envia o branch atual para o repositório remoto:
```
git push
```

Envia o branch main para o repositório remoto:
```
git push origin main
```

Envia o branch main local para o repositório remoto e o define como branch upstream:
```
git push -u origin main
```

Envia a tag v0.1.0 para o repositório remoto:
```
git push origin v0.1.0
```

Envia todas as tags para o repositório remoto:
```
git push origin --tags
```

### Gerenciando branches remotos
Deleta o branch especificado do repositório remoto:
```
git push origin :<nome do branch>
```

## Operações Avançadas do Git

### Guardando alterações
Aplica alterações guardadas ao diretório de trabalho e as remove do stash:
```
git stash pop
```

Aplica alterações de um stash específico na lista de stashes:
```
git stash apply <stash@{índice}>
```

Lista todos os conjuntos de alterações guardadas:
```
git stash list
```

Remove todas as entradas guardadas:
```
git stash clear
```

Salva o estado atual do diretório de trabalho com uma mensagem opcional:
```
git stash push -m "Mensagem do Stash"
```

Guarda temporariamente alterações para que você possa trabalhar em uma tarefa diferente:
```
git stash
```

### Revertendo e resetando commits

Reseta o branch atual para o ID do commit especificado, mantendo as alterações na área de stage:
```
git reset --soft <id do commit>
```

Reseta o branch atual para o ID do commit especificado, descartando todas as alterações:
```
git reset --hard <id do commit>
```

Move a ponta do branch atual para o ID do commit especificado, mantendo as alterações em stage:
```
git reset --soft <id do commit>
```

Move a ponta do branch atual para o ID do commit especificado, descartando todas as alterações no diretório de trabalho e na área de stage:
```
git reset --hard <id do commit>
```

Cria um novo commit que desfaz as alterações introduzidas pelo ID do commit especificado:
```
git revert <id do commit>
```

### Rebase
Reaplica commits no topo do commit atual do branch especificado:
```
git rebase <branch>
```

## Tagging e Releases

### Criando e gerenciando tags
Lista todas as tags no repositório:
```
git tag
```

Cria uma nova tag leve chamada v0.1.0 no commit atual:
```
git tag v0.1.0
```

Cria uma tag leve v0.1.1 apontando para o commit HEAD atual:
```
git tag v0.1.1 HEAD
```

Cria uma tag leve v0.1.1 apontando para o ID do commit especificado:
```
git tag v0.1.1 <id do commit>
```

Deleta a tag local v0.1.1:
```
git tag -d v0.1.1
```

Cria uma tag anotada v0.1.1 com uma mensagem:
```
git tag -a v0.1.1 -m "Mensagem da Tag
```

Verifica a assinatura da tag v0.1.1:
```
git tag -v v0.1.1
```

### Trabalhando com releases do GitHub
GitHub > Releases > Criar uma nova release : Escolha uma Tag > ...

## Solução de Problemas e Dicas

### Visualizando alterações

Exibe as diferenças entre o diretório de trabalho e a área de stage.
Quando nenhum ID de commit é especificado, ele mostra as alterações entre o diretório de trabalho e a área de stage:
```
git diff
```

Mostra as diferenças entre dois commits especificados:
```
git diff <id do commit>..<id do commit>
```

### Resolvendo conflitos de mesclagem

### Atalhos e comandos úteis

Exibe o status do diretório de trabalho e da área de stage:
```
git status
```

## Investigando Alterações

### Cherry-Picking de Alterações.

Aplica as alterações introduzidas pelo ID do commit especificado no branch atual:
```
git cherry-pick <id do commit>
```

### Blame
Mostra quem modificou pela última vez cada linha de um arquivo e quando:
```
git blame <nome do arquivo>
```

### Visualizando alterações
Exibe informações detalhadas sobre um commit específico:
```
git show
```
Mostra as alterações introduzidas pelo ID do commit especificado:
```
git show <id do commit>
```

## Restaurando e Revertendo

### Restaurando Arquivos
Restaura arquivos especificados no diretório de trabalho para seu estado no último commit:
```
git restore <nome do arquivo>
```

Restaura todos os arquivos no diretório de trabalho para seu estado no último commit:
```
git restore .
```

Desfaz o stage do arquivo especificado, mas mantém as alterações no diretório de trabalho:
```
git restore --staged <nome do arquivo>
```

Restaura um arquivo para o estado em que estava no commit especificado:
```
git restore --source=<id do commit> <nome do arquivo>:
```

Restaura um arquivo para seu estado no último commit:
```

git restore --source=HEAD <nome do arquivo>
```

## Referências e Recursos

### Recursos online para aprender Git
- [visualizing.git](https://git-school.github.io/visualizing-git/)
- [gitignore.io](https://gitignore.io)
- [gist.github.com](https://gist.github.com)
- [git-scm.com/doc](https://git-scm.com/doc)

</details>

---

<details>
<summary>es-ES</summary>

# GIT

**Git** es un sistema de control de versiones distribuido diseñado para manejar proyectos pequeños y muy grandes con rapidez y eficiencia.
Permite que varios desarrolladores trabajen en un proyecto simultáneamente, sin interferir en el trabajo de los demás.

Git rastrea los cambios en archivos y directorios, permitiendo a los equipos volver a versiones anteriores, comparar cambios a lo largo del tiempo y fusionar actualizaciones de diferentes ramas.
Se utiliza ampliamente para la gestión de código fuente en el desarrollo de software, pero puede gestionar cualquier conjunto de archivos o documentos.

Para obtener instrucciones detalladas sobre los comandos de Git, consulte la documentación oficial disponible [aquí](https://git-scm.com/doc).

## Ayuda

Al utilizar comandos de Git, puedes utilizar las opciones `--help` o `-h` para obtener información detallada e instrucciones de uso directamente desde la línea de comandos. Estas opciones proporcionan orientación esencial sobre cómo utilizar correctamente un comando específico, sus opciones disponibles y ejemplos de uso.

### **Usando `--help`**

Para obtener ayuda sobre un comando Git específico, agrega --help al final del comando. Por ejemplo:
```
git <comando> --help
```
Este comando muestra información detallada sobre el comando git, incluyendo su sintaxis, opciones y ejemplos de uso.

### **Usando `-h`**

Alternativamente, puedes usar `-h` como un atajo para `--help`. Por ejemplo:
```
git <comando> -h
```
Este comando proporciona información concisa de ayuda para el comando git, ayudándote a comprender su funcionalidad y cómo aplicarlo de manera efectiva en tu flujo de trabajo.

### Notas:
- Las opciones `--help` y `-h` son invaluables tanto para principiantes como para usuarios experimentados, ofreciendo acceso rápido a la documentación del comando sin necesidad de salir del terminal.
- Se recomienda experimentar con estas opciones para familiarizarte con las capacidades de Git y aumentar tu eficiencia al trabajar con el control de versiones.

Al utilizar `--help` o `-h`, puedes acceder eficientemente a la documentación y dominar el uso de los comandos de Git directamente desde tu interfaz de línea de comandos.

## Configuración de Git

### Configuración de la información del usuario
Establece el nombre de usuario global para los commits de Git y muestra el nombre de usuario Git actual:
```
git config --global user.name "Tu Nombre"
git config user.name
```

Establece el correo electrónico global para los commits de Git y muestra el correo electrónico Git actual:
```
git config --global user.email "your@email.com"
git config user.email
```

### Establecer el editor de texto predeterminado
Establece el editor de texto predeterminado global para Git y muestra el editor de texto predeterminado actual para Git:
```
git config --global core.editor "ruta del editor"
git config core.editor
```

### Generación de claves SSH
Para configurar la autenticación segura en GitHub, es crucial generar claves SSH. Aprende a configurar las tuyas siguiendo los pasos descritos [aquí](ssh-key.md).

## Comandos Básicos de Git

### Inicializando un repositorio
Inicializa un nuevo repositorio Git:
```
git init
```

### Clonar un repositorio
Clona un repositorio remoto en la máquina local:
```
git clone <enlace del repositorio de github>
```

### Agregar cambios al stage
Agrega un archivo específico para el commit:
```
git add <nombre del archivo>
```

Agrega todos los cambios en el directorio actual para el commit:
```
git add .
```

### Hacer commit de cambios
Hace commit de los cambios en el stage con un mensaje:
```
git commit -m "Mensaje del Commit"
```

Cambia el mensaje del último commit:
```
git commit --amend -m "Nuevo mensaje de commit"
```

### Ver el historial de commits

Muestra el historial de commits:
```
git log
```

Muestra el historial de commits de forma condensada:
```
git log --oneline
```

Muestra el historial de commits con un formato personalizado:
```
git log --format="%parámetro1 %parámetro2 ..."
```
```
git log --pretty="%parámetro1 %parámetro2 ..."
```

Tabla de Parámetros de --format
| Placeholder | Descripción                   |
| ----------- | ----------------------------- |
| %H          | Hash completo del commit      |
| %h          | Hash abreviado del commit     |
| %an         | Nombre del autor              |
| %ae         | Email del autor               |
| %ad         | Fecha del autor               |
| %ar         | Fecha del autor, relativa     |
| %cn         | Nombre del committer          |
| %ce         | Email del committer           |
| %cd         | Fecha del committer           |
| %cr         | Fecha del committer, relativa |
| %s          | Mensaje del commit            |
| %b          | Cuerpo del commit             |
| %D          | Refs asociadas al commit      |
| %Cred       | Cambia el color a rojo        |
| %Cgreen     | Cambia el color a verde       |
| %Cblue      | Cambia el color a azul        |
| %Creset     | Restablece el color           |

Muestra el historial de commits con las diferencias introducidas en cada commit:
```
git log -p
```

Muestra el historial de commits en una representación gráfica que muestra ramificación y fusión:
```
git log --graph
```

## Ramas y Fusiones

### Gestión de ramas
Renombra la rama actual a main:
```
git branch -M main
```

Enumera todas las ramas locales en el repositorio:
```
git branch
```

Renombra una rama de `<nombre de la rama antigua>` a `<nuevo nombre de la rama>`:
```
git branch -m <nombre de la rama antigua> <nuevo nombre de la rama>
```

Crea una nueva rama llamada `<nueva rama>`:
```
git branch <nueva rama>
```

Cambia a la rama especificada:
```
git checkout <nombre de la rama>
```

Comando correcto para crear y cambiar a una nueva rama:
```
git checkout -b <nueva rama>
```

Cambia a la rama especificada. Alternativa moderna a `git checkout <rama>`:
```
git switch <rama>
```

Crea y cambia a una nueva rama. Alternativa moderna a `git checkout -b <nueva rama>`:
```
git switch -c <nueva rama>
```

### Fusionar cambios

Fusiona los cambios de una rama específica (<rama>) en la rama actual del repositorio Git:
```
git merge <rama>
```

### Eliminar ramas

Elimina la rama especificada, asegurándose de que se haya fusionado completamente en su rama upstream:
```
git branch -d <rama a eliminar>
```

Elimina forzosamente la rama especificada, incluso si tiene cambios sin fusionar:
```
git branch -D <rama a eliminar>
```

## Trabajando con Remotos

### Repositorio remoto
Muestra las URL de los repositorios remotos:
```
git remote -v
```

Agrega un enlace de repositorio remoto:
```
git remote add origin <enlace del repositorio de github>
```

Renombra el repositorio remoto de origin a github:
```
git remote rename origin github: 
```

Enumera los nombres de los repositorios remotos.
```
git remote
```

### Enviar y recibir cambios
Obtiene cambios del repositorio remoto e integra en la rama local actual:
```
git pull
```

Obtiene cambios de la rama main remota e integra en la rama local actual:
```
git pull origin main
```

Envía la rama actual al repositorio remoto:
```
git push
```

Envía la rama main al repositorio remoto:
```
git push origin main
```

Envía la rama main local al repositorio remoto y la establece como rama upstream:
```
git push -u origin main
```

Envía la etiqueta v0.1.0 al repositorio remoto:
```
git push origin v0.1.0
```

Envía todas las etiquetas al repositorio remoto:
```
git push origin --tags
```

### Gestión de ramas remotas
Elimina la rama especificada del repositorio remoto:
```
git push origin :<nombre de la rama>
```

## Operaciones Avanzadas de Git

### Guardar cambios
Aplica los cambios guardados al directorio de trabajo y los elimina del stash:
```
git stash pop
```

Aplica cambios de un stash específico en la lista de stashes:
```
git stash apply <stash@{índice}>
```

Enumera todos los conjuntos de cambios guardados:
```
git stash list
```

Elimina todas las entradas guardadas:
```
git stash clear
```

Guarda el estado actual del directorio de trabajo con un mensaje opcional:
```
git stash push -m "Mensaje del Stash"
```

Guarda temporalmente los cambios para que puedas trabajar en una tarea diferente:
```
git stash
```

### Revertir y restablecer commits

Restablece la rama actual al ID del commit especificado, manteniendo los cambios en la área de stage:
```
git reset --soft <id del commit>
```

Restablece la rama actual al ID del commit especificado, descartando todos los cambios:
```
git reset --hard <id del commit>
```

Mueve la punta de la rama actual al ID del commit especificado, manteniendo los cambios en stage:
```
git reset --soft <id del commit>
```

Mueve la punta de la rama actual al ID del commit especificado, descartando todos los cambios en el directorio de trabajo y en la área de stage:
```
git reset --hard <id del commit>
```

Crea un nuevo commit que deshace los cambios introducidos por el ID del commit especificado:
```
git revert <id del commit>
```

### Rebase
Vuelve a aplicar commits en la parte superior del commit actual de la rama especificada:
```
git rebase <rama>
```

## Etiquetado y Lanzamientos

### Crear y gestionar etiquetas
Enumera todas las etiquetas en el repositorio:
```
git tag
```

Crea una nueva etiqueta ligera llamada v0.1.0 en el commit actual:
```
git tag v0.1.0
```

Crea una etiqueta ligera v0.1.1 apuntando al commit HEAD actual:
```
git tag v0.1.1 HEAD
```

Crea una etiqueta ligera v0.1.1 apuntando al ID del commit especificado:
```
git tag v0.1.1 <id del commit>
```

Elimina la etiqueta local v0.1.1:
```
git tag -d v0.1.1
```

Crea una etiqueta anotada v0.1.1 con un mensaje:
```
git tag -a v0.1.1 -m "Mensaje de la Etiqueta
```

Verifica la firma de la etiqueta v0.1.1:
```
git tag -v v0.1.1
```

### Trabajar con lanzamientos de GitHub
GitHub > Lanzamientos > Crear un nuevo lanzamiento : Elija una Etiqueta > ...

## Solución de Problemas y Consejos

### Visualización de cambios

Muestra las diferencias entre el directorio de trabajo y la área de stage.
Cuando no se especifica ningún ID de commit, muestra los cambios entre el directorio de trabajo y la área de stage:
```
git diff
```

Muestra las diferencias entre dos commits especificados:
```
git diff <id del commit>..<id del commit>
```

### Resolución de conflictos de fusión

### Atajos y comandos útiles

Muestra el estado del directorio de trabajo y de la área de stage:
```
git status
```

## Investigación de Cambios

### Cherry-Picking de Cambios.

Aplica los cambios introducidos por el ID del commit especificado en la rama actual:
```
git cherry-pick <id del commit>
```

### Blame
Muestra quién modificó por última vez cada línea de un archivo y cuándo:
```
git blame <nombre del archivo>
```

### Visualización de cambios
Muestra información detallada sobre un commit específico:
```
git show
```
Muestra los cambios introducidos por el ID del commit especificado:
```
git show <id del commit>
```

## Restauración y Reversión

### Restauración de Archivos
Restaura archivos especificados en el directorio de trabajo a su estado en el último commit:
```
git restore <nombre del archivo>
```

Restaura todos los archivos en el directorio de trabajo a su estado en el último commit:
```
git restore .
```

Deshace el stage del archivo especificado, pero mantiene los cambios en el directorio de trabajo:
```
git restore --staged <nombre del archivo>
```

Restaura un archivo a su estado en el commit especificado:
```
git restore --source=<id del commit> <nombre del archivo>:
```

Restaura un archivo a su estado en el último commit:
```
git restore --source=HEAD <nombre del archivo>
```

## Referencias y Recursos

### Recursos en línea para aprender Git

- [visualizing.git](https://git-school.github.io/visualizing-git/)
- [gitignore.io](https://gitignore.io)
- [gist.github.com](https://gist.github.com)
- [git-scm.com/doc](https://git-scm.com/doc)

</details>