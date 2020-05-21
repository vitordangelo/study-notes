---
title: Raspberry Pi
published: false
description:
tags: raspberrypi, iot
---

# Criando o cartão de memória (DD)

```bash
dd bs=4M if=2020-02-13-raspbian-buster.img of=/dev/sdX conv=fsync
```

#### GPIO - Raspberry Pi 3 B+

![Raspberry GPIO](https://pi4j.com/1.2/images/j8header-3b-plus.png)

> Temos duas sequências de numeração, uma correspondente ao número do pino e outra ao número do GPIO.

> - A numeração pelo GPIO leva em conta que alguns GPIOs têm um significado especial, pois representam o pino terra (GROUND) ou a alimentação (3V ou 5V). Esses pinos não possuem número na numeração GPIO. Esse esquema de numeração também é chamado de GPIO.BCM (broadcom).

#### Configurando SSH

Para habilitar acesso SSH na raspberry basta criar um arquivo de nome ssh, _sem extensão_, na raiz da partição boot.
Usuário padrão: pi
Senha padrão: raspberry

#### Configurar o Wifi

Para configurar a rede wifi basta criar um arquivo com o nome _wpa_supplicant.conf_ na raiz da partição boot, inserindo o seguinte conteúdo no arquivo:

```shell
country=BR
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
   ssid="NETWORK-NAME"
   psk="NETWORK-PASSWORD"
}
```

> Diferente de outros equipamentos, como o Arduino, o Raspberry PI trabalha com 3.3V em seu GPIO.

#### Definir o pino 7 como saída e atribuir nível alto, baixo e leitura

```shell
gpio mode 7 out
gpio write 7 1
gpio write 7 0
gpio read 7

```

#### Comando **_gpio readall_**

```shell
 +-----+-----+---------+------+---+---Pi 3B--+---+------+---------+-----+-----+
 | BCM | wPi |   Name  | Mode | V | Physical | V | Mode | Name    | wPi | BCM |
 +-----+-----+---------+------+---+----++----+---+------+---------+-----+-----+
 |     |     |    3.3v |      |   |  1 || 2  |   |      | 5v      |     |     |
 |   2 |   8 |   SDA.1 |   IN | 1 |  3 || 4  |   |      | 5v      |     |     |
 |   3 |   9 |   SCL.1 |   IN | 1 |  5 || 6  |   |      | 0v      |     |     |
 |   4 |   7 | GPIO. 7 |   IN | 1 |  7 || 8  | 1 | ALT5 | TxD     | 15  | 14  |
 |     |     |      0v |      |   |  9 || 10 | 1 | ALT5 | RxD     | 16  | 15  |
 |  17 |   0 | GPIO. 0 |   IN | 0 | 11 || 12 | 0 | IN   | GPIO. 1 | 1   | 18  |
 |  27 |   2 | GPIO. 2 |   IN | 0 | 13 || 14 |   |      | 0v      |     |     |
 |  22 |   3 | GPIO. 3 |   IN | 0 | 15 || 16 | 0 | IN   | GPIO. 4 | 4   | 23  |
 |     |     |    3.3v |      |   | 17 || 18 | 0 | IN   | GPIO. 5 | 5   | 24  |
 |  10 |  12 |    MOSI |   IN | 0 | 19 || 20 |   |      | 0v      |     |     |
 |   9 |  13 |    MISO |   IN | 0 | 21 || 22 | 0 | IN   | GPIO. 6 | 6   | 25  |
 |  11 |  14 |    SCLK |   IN | 0 | 23 || 24 | 1 | IN   | CE0     | 10  | 8   |
 |     |     |      0v |      |   | 25 || 26 | 1 | IN   | CE1     | 11  | 7   |
 |   0 |  30 |   SDA.0 |   IN | 1 | 27 || 28 | 1 | IN   | SCL.0   | 31  | 1   |
 |   5 |  21 | GPIO.21 |   IN | 1 | 29 || 30 |   |      | 0v      |     |     |
 |   6 |  22 | GPIO.22 |   IN | 1 | 31 || 32 | 0 | IN   | GPIO.26 | 26  | 12  |
 |  13 |  23 | GPIO.23 |   IN | 0 | 33 || 34 |   |      | 0v      |     |     |
 |  19 |  24 | GPIO.24 |   IN | 0 | 35 || 36 | 0 | IN   | GPIO.27 | 27  | 16  |
 |  26 |  25 | GPIO.25 |   IN | 0 | 37 || 38 | 0 | IN   | GPIO.28 | 28  | 20  |
 |     |     |      0v |      |   | 39 || 40 | 0 | IN   | GPIO.29 | 29  | 21  |
 +-----+-----+---------+------+---+----++----+---+------+---------+-----+-----+
 | BCM | wPi |   Name  | Mode | V | Physical | V | Mode | Name    | wPi | BCM |
 +-----+-----+---------+------+---+---Pi 3B--+---+------+---------+-----+-----+

```

> A pinagem padrão para comandos no terminal é a da coluna _wPi_.

| Tipo de identificação do pino |      Comando       |
| :---------------------------: | :----------------: |
|        Conexão física         | gpio -1 mode 7 out |
|          Número GPIO          | gpio -g mode 7 out |

#### Comando **_pinout_**

```shell
,--------------------------------.
| oooooooooooooooooooo J8     +====
| 1ooooooooooooooooooo        | USB
|                             +====
|      Pi Model 3B  V1.2         |
|      +----+                 +====
| |D|  |SoC |                 | USB
| |S|  |    |                 +====
| |I|  +----+                    |
|                   |C|     +======
|                   |S|     |   Net
| pwr        |HDMI| |I||A|  +======
`-| |--------|    |----|V|-------'

Revision           : a02082
SoC                : BCM2837
RAM                : 1024Mb
Storage            : MicroSD
USB ports          : 4 (excluding power)
Ethernet ports     : 1
Wi-fi              : True
Bluetooth          : True
Camera ports (CSI) : 1
Display ports (DSI): 1

J8:
   3V3  (1) (2)  5V
 GPIO2  (3) (4)  5V
 GPIO3  (5) (6)  GND
 GPIO4  (7) (8)  GPIO14
   GND  (9) (10) GPIO15
GPIO17 (11) (12) GPIO18
GPIO27 (13) (14) GND
GPIO22 (15) (16) GPIO23
   3V3 (17) (18) GPIO24
GPIO10 (19) (20) GND
 GPIO9 (21) (22) GPIO25
GPIO11 (23) (24) GPIO8
   GND (25) (26) GPIO7
 GPIO0 (27) (28) GPIO1
 GPIO5 (29) (30) GND
 GPIO6 (31) (32) GPIO12
GPIO13 (33) (34) GND
GPIO19 (35) (36) GPIO16
GPIO26 (37) (38) GPIO20
   GND (39) (40) GPIO21

```

#### Exemplo I

```python
import RPi.GPIO as GPIO   #Biblioteca GPIO
import time               #Biblioteca de tempo

GPIO.setmode(GPIO.BOARD)  #Utiliza a pinagem da placa
# GPIO.setmode(GPIO.BCM)  #Utiliza a pinagem de GPIO
GPIO.setwarnings(False)   #Desativa as mensagens de wartings do GPIO
GPIO.setup(7, GPIO.OUT)   #Configura o pina 7 como saida

while(1):
  print('LED ON')
  GPIO.output(7, GPIO.HIGH) #Ativa o pino 7
  time.sleep(2)             #Delay de 2s
  GPIO.output(7, GPIO.LOW) #Desativa o pino 7
  print('LED OFF')
  time.sleep(2)
```

#### Exemplo II

```python
import RPi.GPIO as GPIO
import sys

def inicializaBoard():
   GPIO.setmode(GPIO.BOARD)
   GPIO.setwarnings(False)

def definePinoComoSaida(numeroPino):
   GPIO.setup(numeroPino, GPIO.OUT)

def escreveParaPorta(numeroPino, estadoPorta):
   GPIO.output(numeroPino, estadoPorta)

numeroPino = int(sys.argv[1])
estadoPorta = int(sys.argv[2])

inicializaBoard()
definePinoComoSaida(numeroPino)
escreveParaPorta(numeroPino, estadoPorta)
```

#### Executando o comando informando os pinos e o estado

- python automate.py 7 0
- python automate.py 7 1
- python automate.py 11 0
- python automate.py 11 1

<hr>

#### Instalar VNC

```shell
sudo apt install tightvncserver -y
```

- Para iniciar o Tight VNC Server basta dar o comando: tightvncserver, será solicitado uma senha. Posteriormente será dado uma mensagem semelhante:

```shell
New 'X' server desktop is raspberry:2
```

Para acessar a RPi pelo Remmina basta inserir o IP acrescido do :x (número dado na mensagem ao inciar o servidor).

#### Pigs

> Ferramenta para controle de GPIO.

- Iniciar: sudo pigpiod
- Setar o GPIO17 como output: pigs m 17 1
- Setar o GPIO17 como input: pigs m 17 0
- Ativar o GPIO17: pigs w 17 1
- Desativar o GPIO17: pigs w 17 0
- Ler o GPIO17: pigs r 17

#### Atalho para acessar via SSH

- Crie um arquivo de nome **config** no diretório: ~/.ssh/ com o seguinte conteúdo:

```shell
Host piLab
   HostName 192.168.2.138
   User pi
```

Para acessar basta dar o comando: ssh piLab

<hr>

#### Comando Raspconfig

```shell
sudo raspi-config

┌───────────────────┤ Raspberry Pi Software Configuration Tool (raspi-config) ├────────────────────┐
│                                                                                                  │
│        1 Change User Password Change password for the current user                               │
│        2 Network Options      Configure network settings                                         │
│        3 Boot Options         Configure options for start-up                                     │
│        4 Localisation Options Set up language and regional settings to match your location       │
│        5 Interfacing Options  Configure connections to peripherals                               │
│        6 Overclock            Configure overclocking for your Pi                                 │
│        7 Advanced Options     Configure advanced settings                                        │
│        8 Update               Update this tool to the latest version                             │
│        9 About raspi-config   Information about this configuration tool                          │
│                                                                                                  │
│                                                                                                  │
│                                                                                                  │
│                           <Select>                           <Finish>                            │
│                                                                                                  │
└──────────────────────────────────────────────────────────────────────────────────────────────────┘
```

- As mesmas configurações podem ser feitas modificando o arquivo: _/boot/config.txt_

<hr>

##### Habilitar Porta Serial

- Adicionar a flag _enable_uart=1_ no arquivo _/boot/config.txt_

<hr>

#### Fontes importante

- [raspi-config](https://www.raspberrypi.org/documentation/configuration/raspi-config.md)
- [config.txt](https://www.raspberrypi.org/documentation/configuration/config-txt/README.md)

#### Setar ip fixo para interface ethernet

Alterar o arquivo: _/etc/dhcpcd.conf_

```shell
#Example static IP configuration:
#interface eth0
#static ip_address=192.168.0.10/24
```

# Ativar o Copy & Paste no VNC

Instalar o autocutsel.

```sh
sudo apt-get install autocutsel -y
```

Abra o arquivo **/home/pi/.vnc/xstartup** e insira o comando

```sh
autocutsel -fork
```
