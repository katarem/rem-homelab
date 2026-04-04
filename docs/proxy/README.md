# Proxy Stack (`proxy-compose.yaml`)

Servicios:

- `nginx-proxy-manager`: reverse proxy con UI.
- `duckdns`: actualización de DNS dinámico.

## Variables de entorno

Archivo: `proxy/.env` (base: `proxy/.env.example`)

- `DUCKDNS_SUBDOMAINS`
- `DUCKDNS_TOKEN`

## Puertos

- `80:80`
- `443:443`
- `81:81`

## Volúmenes

- `./proxy/nginx/data:/data`
- `./proxy/nginx/letsencrypt:/letsencrypt`

## Comandos

```bash
docker compose --env-file proxy/.env -f proxy-compose.yaml up -d
docker compose -f proxy-compose.yaml down
```
