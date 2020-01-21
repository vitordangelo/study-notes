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

# Config

## Lista configurações

```sh
gcloud config configurations list
```

## Remove arquivo de configuração

```sh
gcloud config configurations delete config_file
```

# Storage

![Bucket](./images/bucket.png)

## Cria um novo bucket

```sh
gsutil mb gs://vmhack
```

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

## Upload de um arquivo para uma nova pasta

```shell
gsutil cp <local_file> gs://<bucketname>/<new_folder>/
```

## Manter o bucket como público (Permissão)

```sh
gsutil acl ch -u AllUsers:R gs://vmhack
```

## Remove um diretório

```sh
gsutil rm -r gs://vmhack/videos
```

# Compute (VM)

![Bucket](./images/compute.png)

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
