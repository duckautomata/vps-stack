## dps-stack

The main stack used to run my apps on a single VPS.

## Setting up data folder

```bash
mkdir -p ./data/{prometheus,grafana,portainer,api,archive}
chmod -R 777 ./data/prometheus ./data/prometheus ./data/api ./data/archive
```

## Creating .env file
should return UID=1...

```bash
echo "UID=$(id -u)" > .env
cat .env
```

## Starting stack

```bash
docker compose up -d
```

## Applying changed

```bash
docker compose up -d
docker compose restart caddy
```
