# SSH

![SSH](./images/ssh-icon.png)

## SCP

- SCP (secure copy) linha de comando para realizar cópia de arquivos entre dois locais (ex: máquina local e servidor em nuvem).

### Copiar arquivo local para o servidor

```bash
scp file.txt remote_username@10.10.0.2:/remote/directory
```

### Copiar diretório local para o servidor

```bash
scp -r /local/directory remote_username@10.10.0.2:/remote/directory
```

#### Usando o shortcut do ssh config

```bash
scp -r acknowledgment/ plprod:/home/vitor
```

### Copiar arquivo remoto para máquina local

```bash
scp remote_username@10.10.0.2:/remote/file.txt /local/directory
```
