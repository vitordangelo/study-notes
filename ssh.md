![SSH](./images/ssh-icon.png)

# SSH

## Adicionar chave como confiável

Crie um arquivo com o nome authorized_keys no diretório .ssh/ com as chaves de deseja tornar confiável para acesso sem senha.

# SCP

- SCP (secure copy) linha de comando para realizar cópia de arquivos entre dois locais (ex: máquina local e servidor em nuvem).

## Copiar arquivo local para o servidor

```bash
scp file.txt remote_username@10.10.0.2:/remote/directory
```

## Copiar diretório local para o servidor

```bash
scp -r /local/directory remote_username@10.10.0.2:/remote/directory
```

## Usando o shortcut do ssh config

```bash
scp -r acknowledgment/ plprod:/home/vitor
```

## Copiar arquivo remoto para máquina local

```bash
scp remote_username@10.10.0.2:/remote/file.txt /local/directory
```

# Rsync

- Rsync, which stands for “remote sync”, is a remote and local file synchronization tool. It uses an algorithm that minimizes the amount of data copied by only moving the portions of files that have changed.

```bash
rsync \
  --exclude node_modules \
  --exclude .git \
  --exclude docker/mysql \
  -P -z -r -a -v -e \
  ssh /home/vitor/Documents/Apps/api-alarm-module vitor@104.196.221.13:~/
```

## Usando o shortcut do ssh config

```bash
sync \
  --exclude node_modules \
  --exclude .git \
  --exclude docker/mysql \
  -P -z -r -a -v -e \
  ssh /home/vitor/Documents/Apps/api-alarm-module plprod:~/
```
