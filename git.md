---
title: Minhas notas de estudo sobre Git
published: true
description:
tags: git, github
---

# Controle de versão

O git é capaz de identificar se a versão do código a ser enviada é a mais recente ou não, caso tenha código mais recente no servidor, as alterações local não serão enviadas até que **o conteúdo local seja atualizado** com a versão que esta no servidor.

#### Adicionar todos os arquivos:

```
git add .
```

#### Commit:

```
git commit -m "Criando arquivo”
```

- A boa prática pede para colocarmos mensagens descritivas, evitando que fiquem muito grandes.

#### Estados:

- HEAD: Estado atual do nosso código, ou seja, onde o Git nos colocou
- Working tree: Local onde os arquivos realmente estão sendo armazenados e editados
- index: Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.

#### Lista todos os commits já feitos:

```
git log
```

#### Verifica endereço remoto do repositório:

```
git remote -v
```

- O arquivo .gitignore tem uma função especial, de listar os diretórios e arquivos que devem ser ignorados ao realizar o commit.

#### Envia os arquivos para o repositório remoto:

```
git push origin master
```

#### Baixa as atualizações presentes no repositório remoto:

```
git pull
```

#### Alterar endereço remoto:

```
git remote set-url origin git@github.com:vitordangelo/xxxx.git
```

#### Lista todas as branchs:

```
git branch
```

#### Cria novo branch:

```
git branch titulo
```

#### Mudar para determinada branch:

```
git checkout titulo
```

#### Cria uma nova branch e já muda pra ela:

```
git checkout -b lista
```

#### Commit pra juntar os arquivos de um branch com o master:

```
git commit merge homologation
```

- Gerar um commit a mais, de merge, dependendo da estratégia utilizada para gerar os commits, isto pode acabar atrapalhando ou "poluindo" o log.

- git rebase titulo, e o Git pegará os commits na branch título, atualizando master, que possui todos os commits contidos em titulo, além do commit que havia nela mesma. Deste modo, geramos uma única linha, sem confusões.

#### Juntar todos os commits em uma branch:

```
git rebase titulo
```

#### Salva as alterações em um local temporário sem fazer commit:

```
git stash
```

#### Lista todas as alterações salvas em stash:

```
git stash list
```

#### Recupera as modificações salvas na stash:

```
git stash apply 0
```

#### Recupera as modificações da stash e a remove da lista:

```
git stash pop
```

#### Viaja no tempo, indo para o estágio desejado:

```
git checkout ea539b3
```

#### Volta para o estágio atual:

```
git checkout master
```

#### Juntar commits:

```
git rebase -i ea539b3 (até que nível deseja juntar)
```

Para fazermos isto, substituiremos os pick por s
Com isso, os commits se tornarão um só, o único que possui pick
