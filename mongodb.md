# Notas de estudo sobre MongoDB

![Alexa](./images/mongodb.png)

# Ferramentas

## [MongoDB Community Edition](https://docs.mongodb.com/manual/administration/install-community/)

Instructions to install MongoDB Community Edition.

## [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

MongoDB Atlas is the global cloud database service for modern applications. Deploy fully managed MongoDB across AWS, Azure, or GCP.

## [MongoDB Compass](https://www.mongodb.com/download-center/compass)

As the GUI for MongoDB, MongoDB Compass allows you to make smarter decisions about document structure, querying, indexing, document validation, and more.

## [CosmosDB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb)

Browse and query your MongoDB databases both locally and in the cloud using scrapbooks with rich Intellisense.

## [Mongo - Docker](https://hub.docker.com/_/mongo)

MongoDB document databases provide high availability and easy scalability.

# Docker Compose para backup do banco de dados

```sh
version: '3'

services:
  mongo:
    image: mongo
    container_name: mongo
    volumes:
      - ./:/dump
```

## Dump

```sh
mongodump --host cluster0-xxxx.gcp.mongodb.net:27017 --db curso_alura --ssl --username vitor --password 5X3G7QONo3fgLPwV --out /dump --authenticationDatabase admin
```

## Restore

```sh
mongorestore --host cluster0-xxxx.gcp.mongodb.net:27017 --db curso_alura --ssl --username vitor--password 5X3G7QONo3fgLPwV --authenticationDatabase admin ./pl-api
```

# Comandos

## [find](https://docs.mongodb.com/manual/reference/method/db.collection.find/)

### Lista os documentos com filtro

```js
db.autores.find({
  "artigos.slug": "visualizando-dados-de-frequencia"
});
```

### Lista os documentos com filtro e limita da quantidade de resultado

```js
db.autores.find(
  {
    "artigos.slug": "visualizando-dados-de-frequencia"
  },
  {
    "artigos.titulo": 1,
    "artigos.conteudo": 1
  }
);
```

### Lista todos os documentos

```js
db.autores.find();
```

---

## [insertOne](https://docs.mongodb.com/manual/reference/method/db.collection.insertOne/)

### Insere um documento na coleção

```js
db.autores.insertOne({
  nome: "Vitor Ivan DAngelo",
  descricao: "Descrição do post",
  email: "metroid.p2p@gmail.com",
  senha: "1234"
});
```

---

## [update](https://docs.mongodb.com/manual/reference/method/db.collection.update/)

### Atualiza um documento

```js
db.autores.update(
  {
    nome: "Vitor Ivan DAngelo"
  },
  {
    $set: {
      artigos: [
        {
          slug: "projeto-modelagem",
          titulo: "Modelagem do MongoDB",
          conteudo: "Este é um post que fala sobre modelagem do MongoDB",
          dataCriado: ISODate("2020-01-05")
        }
      ]
    }
  }
);
```
