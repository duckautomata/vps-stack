## dps-stack

The main stack used to run my apps on a single VPS.

## Setting up data folder

```bash
mkdir -p ./data/{prometheus,grafana,portainer,api,archive}
chmod -R 777 ./data/prometheus ./data/grafana ./data/api ./data/archive
```

## Setting up certs

Since this will go behind Cloudflare proxy, we don't really care about having a valid cert.

Because of this, we will use an Origin Server certificate since it lasts for 15 years.

Go to [certs](/certs/) and follow the guide to add certs.

## Setting up Portainers console (if wanted)
If you do not want this, then you can remove it from docker-compose and skip this part.

Run the script bellow in the repo's root directory. Should return UID=1...

```bash
echo "UID=$(id -u)" > .env
cat .env
```

## Starting stack

```bash
docker compose up -d
```

## Applying changes example

```bash
docker compose up -d
docker compose restart caddy
```

## Updated all images
```bash
docker compose pull && docker compose up -d && docker image prune -f
```

for updating a specific server
```bash
docker compose pull api && docker compose up -d api && docker image prune -f
```