# Notas de estudo sobre Docker

![Docker](./images/docker.png)

## Remove containers parados, networks não utilizada, imagens sem uso e cache de build

```shell
docker system prune -a
```

## Lista imagens em disco

```shell
docker images
```

## Cria um container

```shell
docker run -it <imagem> bash
docker run -p 80:8080 -it ubuntu/apache bash
```

## Renomear container

```shell
docker rename <old name> <new name>
```

## Acessa o container

```shell
docker exec -i -t blog-alura bash
docker exec -i -t blog-alura sh
docker run -it ubuntu bash
```

## Faz o download de imagens

```shell
docker pull <imagem>
```

## Lista os containers em execução

```shell
docker ps
```

## Mostra todos os containers

```shell
docker ps -a
```

## Remove container

```shell
docker rm <id>
```

## Remover imagem

```shell
docker rmi <nome da imagem>
```

## Remove todos os conteiners

```shell
docker rm \$(docker ps -qa)
```

## Para o processo do conteiner

```shell
docker stop <nome>
```

## Redimensionando portas

```shell
docker run -it -p 8080:80 <imagem> bash
porta-local:porta-container
```

## Iniciar container

```shell
docker start <container>
```

## Parar container

```shell
docker stop <container>
```

## Matar container

```shell
docker kill <container>
```

## Criar um container temporário

```shell
docker run --rm -it ubuntu bash
```

## Executar um comando sem “abrir” o container

```shell
docker exec -it [id do contêiner][nome do processo com saida]
```

## Exportar container

```shell
docker save -o <diretorio/nome_container.tar> <container>
```

## Montar Dockerfile

```shell
FROM mysql //imagem base

RUN apt-get update && apt-get install -y apache2 //executa a instrução de instalação do Apache

EXPOSE 8080

CMD ["/usr/sbin/apache2clt", "-D", "FOREGROUND"]
```

## Executar Dockerfile

```shell
docker build -t ubuntu/apache .
```

## Executar compose

```shell
docker-compose up -d
```

## Obter informações do container e obter ip

```shell
docker inspect <container>
```

## Informações de rede de um container

```shell
docker network ls
```
