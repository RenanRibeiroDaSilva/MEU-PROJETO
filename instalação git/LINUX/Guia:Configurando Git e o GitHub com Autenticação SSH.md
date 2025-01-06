# Guia: Configurando Git e o GitHub com Autenticação SSH

### 1. Instalar o Git.

* Ubunto/Linux: Execulte o comando:  
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

