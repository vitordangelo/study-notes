# Raspberry Pi Servidor: Samba, VPN, IoT e AWS S3

## Instalação e configuração do SAMBA

```sh
sudo apt install samba samba-common -y
```

> O diretório a ser compartilhado deve ter sua permissão de acesso alterada: **chmod 777**

### Mapeamento do smb.conf do diretório share

- [Doc - smb.conf](https://www.samba.org/samba/docs/current/man-html/smb.conf.5.html)

> sudo vim /etc/samba/smb.conf

```txt
[share]
Comment = Pi shared folder
Path = /share
Browseable = yes
Writeable = Yes
only guest = no
create mask = 0777
directory mask = 0777
Public = yes
Guest ok = yes
```

### Testparm

> testparm — check an smb.conf configuration file for internal correctness

### Adiciona usuário

sudo smbpasswd -a pi

### Reiniciar o serviço

```sh
sudo /etc/init.d/smbd restart
```

### Verificando se esta habilitado para iniciar no boot e se o serviço esta rodando

![stats](https://i.imgur.com/CwuiVja.png)

**enabled** indica que esta ativo para iniciar durante o boot

### Duck DNS

- [Install Doc](https://www.duckdns.org/install.jsp)

## PiVPN

- [Install Doc](https://www.pivpn.io/)

```sh
curl -L https://install.pivpn.io | bash
```

### Create a client

```sh
pivpn add
```

## Android

- [Google Play - OpenVPN](https://play.google.com/store/apps/details?i-d=net.openvpn.openvpn&hl=en)

- [PingTools Network Utilities](https://play.google.com/store/apps/details?id=ua.com.streamsoft.pingtools&hl=en)

- [AndSMB](https://play.google.com/store/apps/details?id=lysesoft.andsmb&hl=en)
