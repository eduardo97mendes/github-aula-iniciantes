# Git no terminal

Esta etapa é opcional na primeira aula, mas recomendada para quem quer usar o computador.

## 1. Verificar se o Git está instalado

No terminal (Mac):

```bash
git --version
```

Se aparecer algo como `git version 2.x.x`, está instalado.

## 2. Configurar sua identidade (fazer uma vez)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

Use o **mesmo e-mail** da sua conta GitHub.

## 3. Clonar seu repositório

Substitua `SEU-USUARIO` pelo seu usuário do GitHub:

```bash
cd ~
git clone https://github.com/SEU-USUARIO/minha-primeira-aula.git
cd minha-primeira-aula
```

### Alternativa com SSH (se já configurou chave SSH)

```bash
git clone git@github.com:SEU-USUARIO/minha-primeira-aula.git
```

## 4. Criar um arquivo novo

```bash
echo "# Minhas notas de aula" > notas.md
```

Ou abra a pasta no editor de texto e crie o arquivo manualmente.

## 5. O ritual do Git

Sempre nesta ordem:

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

## 6. Conferir no GitHub

Atualize a página do seu repositório no navegador. O arquivo `notas.md` deve aparecer.

## Erros comuns

### `Repository not found`

- Você digitou o nome do repositório errado
- O repositório ainda não foi criado no GitHub
- **Não use** `NOME-DO-REPO` — isso é só um exemplo!

### `Permission denied`

- Sua conta não tem permissão no repositório
- Se usar SSH, verifique se a chave SSH foi adicionada no GitHub

### `Nothing to commit`

- Nenhum arquivo foi alterado
- Edite ou crie um arquivo antes do `git add`

## Próximo passo

Faça os exercícios em [05-exercicios.md](./05-exercicios.md).
