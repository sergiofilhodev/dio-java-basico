# dio-java-basico

Repositório para armazenar todo o conteúdo do curso de Java Básico oferecido pela [DIO (Digital Innovation One)](https://www.dio.me/).

📌 Aqui você encontrará:
- Conceitos fundamentais da linguagem Java
- Explicações sobre orientação a objetos
- Comandos úteis de Git e versionamento de código
- Dicas de autenticação com GitHub (via token e SSH)
- Práticas com branches, stash e resolução de conflitos

---

## ☕ Java Básico

Java é uma linguagem **totalmente orientada a objetos**, baseada em **classes**. Para entendê-la melhor, é essencial compreender os seguintes conceitos:

1. **Classes e Objetos**
2. **Encapsulamento**
3. **Abstração**
4. **Herança**
5. **Polimorfismo**

### 🌐 Plataforma Independente

- O **bytecode Java** não está vinculado a nenhuma plataforma.
- A **JVM (Java Virtual Machine)** permite executar o mesmo programa em qualquer sistema operacional.

### 💻 Portabilidade

- O conceito **WORA (Write Once, Run Anywhere)** garante que o código Java funcione em qualquer lugar, graças ao uso do bytecode + JVM.

### 🛠️ Robustez

- Gerenciamento automático de memória.
- Tratamento de exceções e **coleta de lixo (garbage collection)** integrada.

### 🔒 Segurança

- Análise prévia do código antes da execução.
- Suporte à **criptografia/descriptografia** para proteção de dados.

### ⚙️ Compilado e Interpretado

- O código-fonte é **compilado em bytecode**.
- A JVM **interpreta** o bytecode em tempo de execução.

### 🧵 Multithreading

- Suporte nativo à execução de **múltiplas threads simultâneas**, compartilhando recursos de forma eficiente.

---

## 🗂️ Versionamento de Código

### 🔄 VCS Centralizado (CVCS)

**Exemplo:** SVN  
✅ *Vantagens*:
- Simples de usar
- Centralização facilita o controle

❌ *Desvantagens*:
- Se o servidor cair, você perde o histórico
- Requer conexão constante com o servidor

### 🌍 VCS Distribuído (DVCS)

**Exemplo:** Git  
✅ *Vantagens*:
- Cada usuário possui uma cópia completa do repositório
- Permite trabalhar offline
- Fusões e branches são mais eficientes

❌ *Desvantagens*:
- Curva de aprendizado inicial mais acentuada

➡️ **DVCS é melhor** porque é mais flexível, seguro e escalável para equipes distribuídas.

---

## 🧰 Git

Sistema de controle de versão distribuído e open source.

- Rápido, leve, eficiente com ramificações e fusões.
- Amplamente usado em projetos open source e corporativos.

### 🔧 Comandos Básicos

```bash
git clone URL               # Clona um repositório remoto
git commit -m "mensagem"   # Registra mudanças
git pull                    # Atualiza com alterações remotas
git push                    # Envia alterações para o repositório remoto
```

### ⚙️ Configuração Inicial

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
git config --global init.defaultBranch main
git config --global --list
```

---

## 🔐 Autenticação com GitHub

### ✔️ Token (HTTPS)

1. Gere um **token** em [github.com/settings/tokens](https://github.com/settings/tokens)
2. Use esse token no lugar da senha ao fazer `git push`, `pull`, etc.

💡 Dica: use o Git Credential Manager para salvar suas credenciais:

```bash
git config --global credential.helper manager
```

---

### ✔️ Chave SSH

**Passo a passo:**

```bash
ssh-keygen -t ed25519 -C "seu@email.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```

Adicione a chave pública no GitHub em: [github.com/settings/keys](https://github.com/settings/keys)

Para clonar via SSH:

```bash
git clone git@github.com:usuario/repositorio.git
```

---

## 🌿 Trabalhando com Branches

### 📌 Conceitos

Branches permitem **trabalhar com funcionalidades separadas** do código principal (`main`).

### 🌱 Criar e trocar de branch

```bash
git checkout -b nome-da-branch
```

### 🔁 Voltar para a main

```bash
git checkout main
git log
git branch -v
```

### 🔀 Fazer merge

```bash
git merge nome-da-branch
git branch -d nome-da-branch
```

---

## ⚠️ Tratando Conflitos

```bash
git fetch origin main
git diff
git diff main origin/main
```

Após resolver:

```bash
git add arquivo
git commit
```

---

## 📦 Stash – Mudanças temporárias

```bash
git stash         # Guarda alterações
git stash list    # Lista stashes
git stash apply   # Aplica alterações
```

Exemplo:

```bash
git checkout -b nova-branch
git checkout main
git stash
git checkout nova-branch
git stash apply
```

---

## 🌍 Clonar uma branch específica

```bash
git clone URL --branch nome-da-branch --single-branch
```

---

## 🧑‍💻 GitHub

**Plataforma de hospedagem de código com suporte ao Git.**

- Controle de versão colaborativo
- Recursos como **Issues**, **Pull Requests**, **CI/CD**, **Projects**, etc.


