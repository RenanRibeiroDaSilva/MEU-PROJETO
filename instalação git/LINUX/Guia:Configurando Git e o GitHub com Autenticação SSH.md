# Guia: Configurando Git e o GitHub com Autenticação SSH

### 1. Instalar o Git.

* Ubuntu/Linux: Execulte o comando:  
  ```bash
  sudo apt update
  sudo apt isntall git
  ```
  
* Verificar instalação:   
  
  ```      bash
  git --version
  ```

---

### 2. Configurar o Git.

* Definir o nome e o e-mail (usados nos commits):
  ```bash
    git config --global user.name "Seu nome"
    git congit --global user.e-mail "seuemail@exemplo.com"
  ```

* Verificar as configurações:

  ``` bash
  git config --list
  ```

---

### 3. Criar um Repositório no GitHub.

1. Acesse [GitHub](https://github.com/).
2. Clique em **New Repository**.
3. Dê um nome ao repositório (ex.: `MEU-PROJETO`) e clieque em **Create Repository**.

---

### 4. Inicializar o Repositório Local.

* No terminal, crie e entre no diretório do projeto:
  ``` bash
  mkdir meu-projeto
  cd meu-projeto
  ```

* Inicialize o repositório:
  ```bash
  git init
  ```

---

### 5. Adicionar Um Arquivo e Fazer o Primeiro Commit.

1. Crie um arquivo, por exemplo, `README.md`:
   ```bash
   echo "# Meu Projeto" > README.me
   ```

2. Adicione o arquivo ao Git:
   ```bash
   git add README.me
   ```

3. Faça o commit:
   ```bash
   git commit -m "Adiciona arquivo README"
   ```

---

### 6. Configurar Autenticação Via SSH.

#### 6.1 Gerar Chave SSH.

1. Gere a chave SSH:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "seuemail@exemplo.com"
   ```

   * Pressione `Enter` para aceitar o caminho padrão.
   * Crie ou deixe em branco a senha para chave privada.

2. Adicione a chave privada ao agente SSH:

   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```

#### 6.2 Adicionar a Chave Pública ao GitHub.

1. Copie a chave pública:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

2. No GitHub:

   * Acesse **Settings > SSH and GPG Keys > New SSH Key**.
   * Dê um título para a chave (ex.: "Meu Computador").
   * Cole a chave pública copiada e clique em **Add SSH Key**.

#### 6.3 Testar a Conexão com GitHub.

* Teste se a chave SSH está funcionando corretamente:
  ```bash
  ssh -T git@github.com
  ```

* Você verá uma mensagem como:
  ```bash
  Hi <seu-usuario>! You've successfully authenticated, but GitHub does not provide shell access.
  ```

---

### 7. Configurar o Repositório Remoto.

* Adicione o repositório Remoto usando a URL SSH:
  ```bash
  git remote add origin git@github.com:<seu-usuario>/<seu-repositorio>.git
  ```

* Verifique se o repositório remoto foi configurado:
  ```bash
  git remote -v
  ```

---

### 8. Fazer o Push e Pull

* Enviar alterações para o GitHub (push):
  ```bash
  git push -u origin main
  ```

  (Use `main` ou `master`, dependendo do branch principal do seu repositório.)

* **Baixe alterações do GitHub (pull):**

  ```bash
  git pull origin main
  ```

---

### **Comandos Úteis para o Dia a Dia**

- Verificar o status do repositório:

  ```bash
  git status
  ```

- Adicionar todos os arquivos alterados:

  ```bash
  git add .
  ```

- Fazer commit:

  ```bash
  git commit -m "Descrição do commit"
  ```

- Sincronizar alterações locais com o GitHub:

  ```bash
  git push
  ```

- Atualizar o repositório local com mudanças do GitHub:

  ```bash
  git pull
  ```

- Para verificar todas as configurações do Git:
  ```bash
  git config --list
  ```



Sempre que precisar, basta vir buscar!!! (Nota para meu eu do futuro)
