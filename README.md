## dps-stack

The main stack used to run my apps on a single VPS.

## Setting up data folder

```bash
mkdir -p ./data/{prometheus,grafana,portainer,api,archive}
chmod -R 777 ./data/prometheus ./data/prometheus ./data/api ./data/archive
```

## Starting stack

```bash
UID=$(id -u) docker compose up -d
```

## Applying changed

```bash
UID=$(id -u) docker compose up -d
UID=$(id -u) docker compose restart caddy
```
