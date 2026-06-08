# Git no terminal

> **Está na escola ou em um computador público?**  
> **Pule este arquivo.** Você não precisa instalar o Git — faça tudo pelo navegador: [00-aula-pelo-navegador.md](./00-aula-pelo-navegador.md)

Esta etapa é **opcional** e indicada para quem está em um **computador pessoal** (casa), com permissão para instalar programas.

Os comandos Git são **iguais no Mac e no Windows**. O que muda é como abrir o terminal e como instalar o Git.

---

## 1. Instalar o Git

### Mac

O Mac pode já ter o Git instalado. Para verificar, abra o **Terminal** (busque por "Terminal" no Spotlight) e digite:

```bash
git --version
```

Se **não** estiver instalado, instale pelo [Homebrew](https://brew.sh) (se tiver):

```bash
brew install git
```

Ou baixe em: [git-scm.com/download/mac](https://git-scm.com/download/mac)

---

### Windows

#### Passo 1 — Baixar

1. Acesse [git-scm.com/download/win](https://git-scm.com/download/win)
2. O download deve começar automaticamente
3. Execute o arquivo `.exe` baixado

#### Passo 2 — Instalar

Na instalação, para alunos iniciantes, pode **aceitar as opções padrão** (Next, Next, Install). Pontos importantes:

| Tela | Recomendação |
|------|--------------|
| Editor padrão | Deixe como está ou escolha **VS Code** se tiver instalado |
| PATH | Mantenha **Git from the command line and also from 3rd-party software** |
| HTTPS | **Use the OpenSSL library** (padrão) |
| Line endings | **Checkout Windows-style, commit Unix-style** (padrão) |
| Terminal | **Use Windows' default console** ou **MinTTY** (padrão) |

#### Passo 3 — Abrir o terminal no Windows

Depois de instalar, use uma destas opções:

| Terminal | Como abrir |
|----------|------------|
| **Git Bash** | Menu Iniciar → digite "Git Bash" |
| **PowerShell** | Menu Iniciar → digite "PowerShell" |
| **Prompt de Comando** | Menu Iniciar → digite "cmd" |

Para esta aula, **Git Bash** ou **PowerShell** funcionam bem.

#### Passo 4 — Verificar

No Git Bash ou PowerShell:

```bash
git --version
```

Se aparecer algo como `git version 2.x.x`, está instalado.

---

## 2. Configurar sua identidade (fazer uma vez)

No terminal (Mac, Git Bash ou PowerShell):

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

Use o **mesmo e-mail** da sua conta GitHub.

Para conferir:

```bash
git config --global --list
```

---

## 3. Clonar seu repositório

Substitua `SEU-USUARIO` pelo seu usuário do GitHub.

### Mac

```bash
cd ~
git clone https://github.com/SEU-USUARIO/minha-primeira-aula.git
cd minha-primeira-aula
```

### Windows (Git Bash ou PowerShell)

```bash
cd ~
git clone https://github.com/SEU-USUARIO/minha-primeira-aula.git
cd minha-primeira-aula
```

No Windows, a pasta ficará em `C:\Users\SEU-NOME\minha-primeira-aula`.

### Alternativa com SSH (se já configurou chave SSH)

```bash
git clone git@github.com:SEU-USUARIO/minha-primeira-aula.git
```

> Configurar SSH no Windows é um passo extra. Na primeira aula, prefira **HTTPS** — é mais simples.

---

## 4. Criar um arquivo novo

### Mac / Git Bash

```bash
echo "# Minhas notas de aula" > notas.md
```

### Windows (PowerShell)

```powershell
"# Minhas notas de aula" | Out-File -Encoding utf8 notas.md
```

Ou abra a pasta no **Bloco de Notas**, **VS Code** ou **Notepad++** e crie o arquivo manualmente.

---

## 5. O ritual do Git

Sempre nesta ordem — **igual no Mac e no Windows**:

```bash
git status
git add .
git commit -m "Adiciona arquivo de notas"
git push
```

| Comando | O que faz |
|---------|-----------|
| `git status` | Mostra o que mudou |
| `git add .` | Prepara as alterações |
| `git commit -m "..."` | Salva uma versão |
| `git push` | Envia para o GitHub |

Na primeira vez que usar `git push` com HTTPS, o Windows pode pedir login do GitHub — use sua conta ou um **Personal Access Token** como senha.

---

## 6. Conferir no GitHub

Atualize a página do seu repositório no navegador. O arquivo `notas.md` deve aparecer.

---

## Erros comuns

### `Repository not found`

- Você digitou o nome do repositório errado
- O repositório ainda não foi criado no GitHub
- **Não use** `NOME-DO-REPO` — isso é só um exemplo!

### `Permission denied`

- Sua conta não tem permissão no repositório
- Se usar SSH, verifique se a chave SSH foi adicionada no GitHub
- No Windows com HTTPS, confira usuário e token de acesso

### `Nothing to commit`

- Nenhum arquivo foi alterado
- Edite ou crie um arquivo antes do `git add`

### `git is not recognized` (Windows)

- O Git não foi instalado ou o terminal não foi reiniciado após a instalação
- Feche e abra o Git Bash ou PowerShell de novo
- Reinstale o Git marcando a opção de adicionar ao PATH

---

## Próximo passo

Faça os exercícios em [05-exercicios.md](./05-exercicios.md).
