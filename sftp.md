# SFTP

## Adicionando configuração do SFTP no arquivo de configuração SSH

    sudo vim /etc/ssh/sshd_config

    Match group sftp
    ChrootDirectory /home
    X11Forwarding no
    AllowTcpForwarding no
    ForceCommand internal-sftp

## Reinciar o serviço SSH

    sudo service ssh restart

## Adicionando grupo SFTP

    sudo addgroup sftp

## Criando um novo usuário e adicionando no grupo SFTP

    sudo useradd -m sftpuser -g sftp

## Alterando senha do usuário

    sudo passwd sftpuser

## Alterando permissão do usuário

    sudo chmod 700 /home/sftpuser/

## Acesso

    sftp sftpuser@ubuntu-sftp

![screen](https://i.imgur.com/8JNLtNu.png)
