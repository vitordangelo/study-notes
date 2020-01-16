# Comandos Linux

# du - Disk Usage

## Informa o tamanho do diretório

```sh
du <dir>
```

## Informa o tamanho de cada arquivo de um diretório

```sh
du -ah <dir>
```

# Iniciar um script durante o boot

- Criar o arquivo: **/etc/systemd/system/my_daemon.service** com o conteúdo:

```sh
[Unit]
Description=Spark service

[Service]
ExecStart=/path/to/spark/sbin/start-all.sh

[Install]
WantedBy=multi-user.target
```

### Habilitar e desabilitar o serviço

```sh
sudo systemctl enable my_daemon.service
sudo systemctl disable my_daemon.service
```

# Adicionar um script/App no Laucher

- Criar o arquivo em **/usr/share/applications/nomeApp.desktop** com o conteúdo

```sh
[Desktop Entry]
Name=HeidenSQL
Exec=wine "/home/vitor/soft/HeidenSQL/heidisql.exe"
Icon=/home/vitor/soft/icon/HeidenQSL.png
Type=Application
Categories=Wine;


[Desktop Entry]
Name=Telegram
Exec=/media/vitor/Novo volume/Softwares/Telegram
Icon=/usr/share/icons/Papirus/64x64/apps/telegram.svg
Type=Application
Categories=Internet;
```

# Montar disco

[Ubuntu: Mount The Drive From Command Line](https://www.cyberciti.biz/faq/mount-drive-from-command-line-ubuntu-linux/)

Use o comando abaixo para listar os discos/partições

```sh
lsblk
```

```sh
sudo mount /dev/sdb1 /media/newhd
```

# Hacks

## Criar vários arquivos

```sh
touch file{1..10}.avi

touch 'teste 01'{1..10}.avi
```

## Renomear arquivos (removendo espaço)

```sh
for f in *.mp4; do
  mv "$f" "${f// /}"
done
```

## Mover vários arquivos de diferentes diretórios para um destino

```sh
mv -v /home/vivek/dir1/ /home/vivek/dir2/ -t /nas/home/vivek/archived/
```

# DNS

## Listar servidores de DNS

```sh
nmcli device show wlp2s0 | grep IP4.DNS
```
