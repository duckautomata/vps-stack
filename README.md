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

## Setting up Admin console

1. Run `docker run --rm caddy caddy hash-password --plaintext "example-password"` and change the example password with one you want to use. It should output a hash starting with `$2a$14$`

Inside [Caddyfile](./config/Caddyfile), change `$2a$14$your_long_hash_string_here...` with the hash created above

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

## Applying changes example

```bash
docker compose up -d
docker compose restart caddy
```
