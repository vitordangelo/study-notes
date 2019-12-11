# Notas de estudo sobre Google Cloud

![GCP](./images/google-cloud.png)

## Init

```shell
gcloud init
```

## Login

```shell
gcloud auth login <email>
```

## Logout em todas as contas

```shell
gcloud auth revoke --all
```

# Storage

## Lista buckets

```shell
gsutil ls
```

## Lista arquivos no bucket

```shell
gsutil ls gs://v2tech/
```

## Upload do arquivo

```shell
gsutil cp <arquivo> <bucket>

```

## Criar pasta no bucket

```shell
gsutil cp <new_folder> gs://<bucketname>/
```

## Upload de um arquivo para uma nova pasta

```shell
gsutil cp <local_file> gs://<bucketname>/<new_folder>/
```

# Compute (VM)

## Listar instâncias

```shell
gcloud compute instances list
```

## Para uma instância

```shell
gcloud compute instances stop <nome_instancia>
```

## Iniciar (start) uma instância

```shell
gcloud compute instances start <nome_instancia>
```

# Config

## Setar uma configuração existente

```shell
gcloud config set project <nome_projeto>
```
