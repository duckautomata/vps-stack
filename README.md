## dps-stack

The main stack used to run my apps on a single VPS.

## Setting up data folder

```sh
mkdir -p ./data/{prometheus,grafana,portainer,api,archive}}
chmod -R 777 ./data/prometheus ./data/prometheus ./data/api ./data/archive
```

## Starting stack

```sh
docker compose up -d
```

## Applying changed

```sh
docker compose up -d
docker compose restart caddy
```
