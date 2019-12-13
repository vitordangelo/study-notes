# Notas de estudo sobre PM2

![PM2](./images/pm2.png)

## Iniciar um processo

```shell
pm2 start app.js
pm2 start <config_file>
```

## Listar todos processos

```shell
pm2 list
```

## Reiniciar todas processos

```shell
pm2 restart all
```

## Status

```shell
pm2 status
```

## Detalhes sobre uma instância em execução

```shell
pm2 describe <id>
```

## Mostra os logs do processo

```shell
pm2 log <id>
```

## Parar um processo

```shell
pm2 stop <id>
```
