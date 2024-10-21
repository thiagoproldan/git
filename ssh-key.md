<details open>
<summary>en-US</summary>
  
# How to configure SSH Key on GitHub?
**SSH (Secure Shell)** is a network protocol that enables secure communication and access to remote servers through encrypted data transmission. By using SSH, you can execute commands and manage files on remote servers securely, ensuring data integrity and confidentiality.

GitHub supports SSH key authentication, allowing you to manage your repositories remotely and securely without the need to provide your username and personal access token repeatedly. This authentication method not only simplifies access but also enhances the security of your operations, protecting against phishing attacks and other threats.

For detailed instructions on configuring SSH keys for GitHub, refer to the official documentation available [here](https://docs.github.com/en/authentication).

## Validate Existing Keys
Before generating a new SSH key, it's important to check if you already have one. This can help avoid creating multiple keys unnecessarily.

To list the existing keys, run the following command in your terminal:
```
ls -al ~/.ssh
```

This command will display the contents of your `.ssh` directory, which typically includes files such as:
- `id_rsa` (private key)
- `id_rsa.pub` (public key)
- `id_ed25519` (private key)
- `id_ed25519.pub` (public key)
- `known_hosts` (a file that stores the SSH server fingerprints)
- `known_hosts.old` (a backup of the `known_hosts` file)

If you see `id_rsa.pub` or `id_ed25519.pub` listed, it means you already have an SSH key pair. You can use the existing key or generate a new one if needed.

## Generate a New Key
- To create an **ed25519** key, run: 
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- To create an **RSA** key, run: 
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Follow the prompts to save the key to the default location (`~/.ssh/id_ed25519` or `~/.ssh/id_rsa`) and enter a secure passphrase if desired.

## Add Private Key to ssh-agent
To ensure your SSH key is used automatically, you need to add it to the `ssh-agent`, which manages your SSH keys.

Start the ssh-agent in the background:
```
eval "$(ssh-agent -s)"
```

Add your SSH private key to the ssh-agent:
```
ssh-add ~/.ssh/id_ed25519
```

If you generated an RSA key, replace `id_ed25519` with `id_rsa`:
```
ssh-add ~/.ssh/id_rsa
```

## Copy Public Key

### On Windows:
```
clip < ~/.ssh/id_ed25519.pub
```
```
clip < ~/.ssh/id_rsa.pub
```
*Automatically copies the content of your public key to the clipboard*.

### On Linux:
```
cat ~/.ssh/id_ed25519.pub
```
```
cat ~/.ssh/id_rsa.pub
```
*Displays the content of the public key in the terminal for you to select and copy.*

### On MacOS:
```
pbcopy < ~/.ssh/id_ed25519.pub
```
```
pbcopy < ~/.ssh/id_rsa.pub
```
*Automatically copies the content of your public key to the clipboard.*

## Add Key to GitHub
1. Open GitHub and go to the profile icon > **Settings** in the top right corner.
2. In the user settings sidebar, click on **SSH and GPG keys**.
3. Click the **New SSH key** button.
4. In the **Title field**, add a descriptive label for the new key. For example, if you are using your personal computer, you can name this key "Personal Computer".
5. Paste the public key from the clipboard into the **Key** field.
6. Click **Add SSH key** and you're done!

## Testing the SSH Connection
To confirm that everything is set up correctly, test your SSH connection to GitHub:

- Run the following command: 
```
ssh -T git@github.com
```

- Wait for the messages. Type "yes" to continue.
- Verify that the resulting message contains your username and confirms successful authentication.

You should see a message like this:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

</details>

---

<details>
<summary>pt-BR</summary>

# Como configurar uma chave SSH no GitHub?
**SSH (Secure Shell)** é um protocolo de rede que permite comunicação segura e acesso a servidores remotos por meio de transmissão de dados criptografada. Usando SSH, você pode executar comandos e gerenciar arquivos em servidores remotos de forma segura, garantindo a integridade e confidencialidade dos dados.

O GitHub suporta autenticação por chave SSH, permitindo que você gerencie seus repositórios remotamente e com segurança, sem a necessidade de fornecer seu nome de usuário e token de acesso pessoal repetidamente. Este método de autenticação simplifica o acesso e melhora a segurança das suas operações, protegendo contra ataques de phishing e outras ameaças.

Para instruções detalhadas sobre como configurar chaves SSH no GitHub, consulte a documentação oficial disponível [aqui](https://docs.github.com/pt/authentication).

## Validar Chaves Existentes
Antes de gerar uma nova chave SSH, é importante verificar se você já possui uma. Isso pode ajudar a evitar a criação de várias chaves desnecessariamente.

Para listar as chaves existentes, execute o seguinte comando no seu terminal:
```
ls -al ~/.ssh
```

Este comando exibirá o conteúdo do diretório `.ssh`, que normalmente inclui arquivos como:
- `id_rsa` (chave privada)
- `id_rsa.pub` (chave pública)
- `id_ed25519` (chave privada)
- `id_ed25519.pub` (chave pública)
- `known_hosts` (um arquivo que armazena as impressões digitais dos servidores SSH)
- `known_hosts.old` (um backup do arquivo `known_hosts`)

Se você vir `id_rsa.pub` ou `id_ed25519.pub` listados, significa que você já tem um par de chaves SSH. Você pode usar a chave existente ou gerar uma nova, se necessário.

## Gerar uma Nova Chave
- Para criar uma chave **ed25519**, execute:
```
ssh-keygen -t ed25519 -C "seu_email@example.com"
```

- Para criar uma chave **RSA**, execute:
```
ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
```

Siga as instruções para salvar a chave no local padrão (`~/.ssh/id_ed25519` ou `~/.ssh/id_rsa`) e insira uma frase secreta segura, se desejar.

## Adicionar a Chave Privada ao ssh-agent
Para garantir que sua chave SSH seja usada automaticamente, você precisa adicioná-la ao `ssh-agent`, que gerencia suas chaves SSH.

Inicie o ssh-agent em segundo plano:
```
eval "$(ssh-agent -s)"
```

Adicione sua chave privada SSH ao ssh-agent:
```
ssh-add ~/.ssh/id_ed25519
```

Se você gerou uma chave RSA, substitua `id_ed25519` por `id_rsa`:
```
ssh-add ~/.ssh/id_rsa
```

## Copiar a Chave Pública

### No Windows:
```
clip < ~/.ssh/id_ed25519.pub
```
```
clip < ~/.ssh/id_rsa.pub
```
*Copia automaticamente o conteúdo da sua chave pública para a área de transferência*.

### No Linux:
```
cat ~/.ssh/id_ed25519.pub
```
```
cat ~/.ssh/id_rsa.pub
```
*Exibe o conteúdo da chave pública no terminal para você selecionar e copiar*.

### No MacOS:
```
pbcopy < ~/.ssh/id_ed25519.pub
```
```
pbcopy < ~/.ssh/id_rsa.pub
```
*Copia automaticamente o conteúdo da sua chave pública para a área de transferência*.

## Adicionar a Chave ao GitHub
1. Abra o GitHub e vá para o ícone do perfil > **Configurações** no canto superior direito.
2. Na barra lateral das configurações do usuário, clique em **Chaves SSH e GPG**.
3. Clique no botão **Nova chave SSH**.
4. No campo **Título**, adicione uma etiqueta descritiva para a nova chave. Por exemplo, se você estiver usando seu computador pessoal, pode nomear esta chave como "Computador Pessoal".
5. Cole a chave pública da área de transferência no campo **Chave**.
6. Clique em **Adicionar chave SSH** e pronto!

## Testando a Conexão SSH
Para confirmar que tudo está configurado corretamente, teste sua conexão SSH com o GitHub:

- Execute o seguinte comando:
```
ssh -T git@github.com
```

- Aguarde as mensagens. Digite "yes" para continuar.
- Verifique se a mensagem resultante contém seu nome de usuário e confirma a autenticação bem-sucedida.

Você deve ver uma mensagem como esta:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

</details>

---

<details>
<summary>es-ES</summary>

# ¿Cómo configurar una clave SSH en GitHub?
**SSH (Secure Shell)** es un protocolo de red que permite una comunicación segura y acceso a servidores remotos mediante la transmisión de datos cifrada. Usando SSH, puedes ejecutar comandos y gestionar archivos en servidores remotos de manera segura, garantizando la integridad y confidencialidad de los datos.

GitHub admite la autenticación mediante clave SSH, lo que te permite gestionar tus repositorios de forma remota y segura sin necesidad de proporcionar tu nombre de usuario y token de acceso personal repetidamente. Este método de autenticación no solo simplifica el acceso, sino que también mejora la seguridad de tus operaciones, protegiéndote contra ataques de phishing y otras amenazas.

Para obtener instrucciones detalladas sobre cómo configurar claves SSH en GitHub, consulta la documentación oficial disponible [aquí](https://docs.github.com/es/authentication). 

## Validar Claves Existentes
Antes de generar una nueva clave SSH, es importante verificar si ya tienes una. Esto puede ayudar a evitar la creación innecesaria de múltiples claves.

Para listar las claves existentes, ejecuta el siguiente comando en tu terminal:
```
ls -al ~/.ssh
```

Este comando mostrará el contenido de tu directorio `.ssh`, que típicamente incluye archivos como:
- `id_rsa` (clave privada)
- `id_rsa.pub` (clave pública)
- `id_ed25519` (clave privada)
- `id_ed25519.pub` (clave pública)
- `known_hosts` (un archivo que almacena las huellas digitales de los servidores SSH)
- `known_hosts.old` (una copia de seguridad del archivo `known_hosts`)

Si ves `id_rsa.pub` o `id_ed25519.pub` en la lista, significa que ya tienes un par de claves SSH. Puedes usar la clave existente o generar una nueva si es necesario.

## Generar una Nueva Clave
- Para crear una clave **ed25519**, ejecuta:
```
ssh-keygen -t ed25519 -C "tu_email@example.com"
```

- Para crear una clave **RSA**, ejecuta:
```
ssh-keygen -t rsa -b 4096 -C "tu_email@example.com"
```

Sigue las indicaciones para guardar la clave en la ubicación predeterminada (`~/.ssh/id_ed25519` o `~/.ssh/id_rsa`) e ingresa una frase de contraseña segura si lo deseas.

## Agregar la Clave Privada al ssh-agent
Para asegurarte de que tu clave SSH se use automáticamente, debes agregarla al `ssh-agent`, que gestiona tus claves SSH.

Inicia el ssh-agent en segundo plano:
```
eval "$(ssh-agent -s)"
```

Agrega tu clave privada SSH al ssh-agent:
```
ssh-add ~/.ssh/id_ed25519
```

Si generaste una clave RSA, reemplaza `id_ed25519` por `id_rsa`:
```
ssh-add ~/.ssh/id_rsa
```

## Copiar la Clave Pública

### En Windows:
```
clip < ~/.ssh/id_ed25519.pub
```
```
clip < ~/.ssh/id_rsa.pub
```
*Copia automáticamente el contenido de tu clave pública al portapapeles*.

### En Linux:
```
cat ~/.ssh/id_ed25519.pub
```
```
cat ~/.ssh/id_rsa.pub
```
*Muestra el contenido de la clave pública en la terminal para que lo selecciones y copies*.

### En MacOS:
```
pbcopy < ~/.ssh/id_ed25519.pub
```
```
pbcopy < ~/.ssh/id_rsa.pub
```
*Copia automáticamente el contenido de tu clave pública al portapapeles*.

## Agregar la Clave a GitHub
1. Abre GitHub y ve al icono de perfil > **Configuración** en la esquina superior derecha.
2. En la barra lateral de configuración del usuario, haz clic en **Claves SSH y GPG**.
3. Haz clic en el botón **Nueva clave SSH**.
4. En el campo **Título**, agrega una etiqueta descriptiva para la nueva clave. Por ejemplo, si estás usando tu computadora personal, puedes nombrar esta clave como "Computadora Personal".
5. Pega la clave pública desde el portapapeles en el campo **Clave**.
6. Haz clic en **Agregar clave SSH** ¡y listo!

## Probar la Conexión SSH
Para confirmar que todo está configurado correctamente, prueba tu conexión SSH con GitHub:

- Ejecuta el siguiente comando:
```
ssh -T git@github.com
```

- Espera a los mensajes. Escribe "yes" para continuar.
- Verifica que el mensaje resultante contenga tu nombre de usuario y confirme la autenticación exitosa.

Deberías ver un mensaje como este:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

</details>
