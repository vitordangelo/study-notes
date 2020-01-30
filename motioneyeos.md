# motioneyeos

## [Documentação](https://github.com/ccrisan/motioneyeos/wiki/Installation)

[Releases](https://github.com/ccrisan/motioneyeos/releases)

### Script para instalação

[writeimage.sh](https://raw.githubusercontent.com/ccrisan/motioneyeos/master/writeimage.sh)

### Comando para rodar o script de instalação com DHCP

```x
./writeimage.sh -d /dev/mmcblk0 -i "/path/to/motioneyeos.img" -n 'yournet:yourkey'
```

### Comando para rodar o script de instalação com IP estático

```x
./writeimage.sh -d /dev/mmcblk0 -i "/path/to/motioneyeos.img" -s "192.168.1.101/24:192.168.1.1:8.8.8.8"
```
