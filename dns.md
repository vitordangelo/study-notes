# Notas de estudo sobre DNS

# Dig

## Informações básicas sobre um domínio

```shell
dig <dominio>
```

## Lista os IPs do servidor

```shell
dig +short <dominio>
```

## Lista informações detalhadas sobre a configuração do DNS

```shell
dig +noall +answer <dominio>
```

## Query para buscar todos os Registros do tipo MX e outros

```shell
dig <dominio> MX
dig <dominio> TXT
dig <dominio> CNAME
dig <dominio> NS
```

## Epecificando um servidor DNS para realizar a consulta

```shell
dig @8.8.8.8 www.raj.ninja
```
