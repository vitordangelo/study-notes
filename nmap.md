# Nmap

## Verifica se uma determinada porta TCP esta aberta

```sh
sudo nmap -Pn  -p 8088 -sT  v2servidor.ddns.net
```

## Verifica se um range de portas TCP estão aberta

```sh
sudo nmap -Pn  -p 6600-6613 -sT  v2servidor.ddns.net
```

## Verifica se uma determinada porta UDP esta aberta

```sh
sudo nmap -Pn  -p 8088 -sU  v2servidor.ddns.net
```
