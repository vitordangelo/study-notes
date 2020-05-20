# Recover TP-Link

1. Baixar a firmware correspondente ao roteador.

   - TL-WR740N: https://drive.google.com/open?id=1k0eOdVvKTpGPLM6Jk6RzF5vB31lbm70c

2. Baixar o programa TFTP:

   - http://tftpd32.jounin.net/tftpd32_download.html

3. Renomear o arquivo da firmware:
   - _'numeroDoSeuRoteador'versãoDoHardwareDoSeuRoteador'\_tp_recovery.bin_
   - wr740nv4_tp_recovery.bin

> -\_tp_recovery.bin é o final exigido pelo programa TFTP

4. Alterar o endereço IP da placa de rede ethernet para: **192.168.0.66**

5. Abra o programa TFTP e aponte o arquivo da firmware
