---
title: Minhas notas de estudo sobre Git
published: true
description:
tags: git, github
---

![git](./images/git.png)

# Controle de versão

O git é capaz de identificar se a versão do código a ser enviada é a mais recente ou não, caso tenha código mais recente no servidor, as alterações local não serão enviadas até que **o conteúdo local seja atualizado** com a versão que esta no servidor.

## Configurar dados do usuário

```sh
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "MY_NAME@example.com"
```

## Adicionar todos os arquivos

```shell
git add .
```

## Commit

```shell
git commit -m "Criando arquivo”
```

- A boa prática pede para colocarmos mensagens descritivas, evitando que fiquem muito grandes.

## Estados

- HEAD: Estado atual do nosso código, ou seja, onde o Git nos colocou
- Working tree: Local onde os arquivos realmente estão sendo armazenados e editados
- index: Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.

## Lista todos os commits já feitos

```shell
git log
```

## Verifica endereço remoto do repositório

```shell
git remote -v
```

- O arquivo .gitignore tem uma função especial, de listar os diretórios e arquivos que devem ser ignorados ao realizar o commit.

## Envia os arquivos para o repositório remoto

```shell
git push origin master
```

## Baixa as atualizações presentes no repositório remoto

```shell
git pull
```

## Alterar endereço remoto

```shell
git remote set-url origin git@github.com:vitordangelo/xxxx.git
```

## Lista todas as branchs

```shell
git branch
```

## Cria novo branch

```shell
git branch titulo
```

## Mudar para determinada branch

```shell
git checkout titulo
```

## Cria uma nova branch e já muda pra ela

```shell
git checkout -b lista
```

## Deletar uma branch local

```shell
git branch -d <branch>
```

## Deletar uma branch Remoto

```shell
git push origin -d <branch>
```

## Commit pra juntar os arquivos de um branch com o master

```shell
git commit merge homologation
```

- Gerar um commit a mais, de merge, dependendo da estratégia utilizada para gerar os commits, isto pode acabar atrapalhando ou "poluindo" o log.

- git rebase titulo, e o Git pegará os commits na branch título, atualizando master, que possui todos os commits contidos em titulo, além do commit que havia nela mesma. Deste modo, geramos uma única linha, sem confusões.

## Juntar todos os commits em uma branch

```shell
git rebase titulo
```

## Salva as alterações em um local temporário sem fazer commit

```shell
git stash
```

## Lista todas as alterações salvas em stash

```shell
git stash list
```

## Recupera as modificações salvas na stash

```shell
git stash apply 0
```

## Recupera as modificações da stash e a remove da lista

```shell
git stash pop
```

## Viaja no tempo, indo para o estágio desejado

```shell
git checkout ea539b3
```

## Volta para o estágio atual

```shell
git checkout master
```

## Juntar commits

```shell
git rebase -i ea539b3 (até que nível deseja juntar)
```

## Alterar mensagem de um commit

```shell
git commit --amend -m <mensagem>
```

Para fazermos isto, substituiremos os pick por s
Com isso, os commits se tornarão um só, o único que possui pick

## Clonar um repositório específico

```shell
git clone -b <branch> <remote_repo>

```

## Remover commit (ou série de commits)

```shell
git reset --hard <last_known_good_commit>
git push -f origin
```
