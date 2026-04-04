# Dashboard Stack (`dashboard-compose.yaml`)

Servicio:

- `homarr`: dashboard central para exponer enlaces/estado de servicios del homelab.

## Variables de entorno

Archivo: `dashboard/.env` (base: `dashboard/.env.example`)

- `HOMARR_SECRET_ENCRYPTION_KEY`

## Puerto

- `7575:7575`

## Volumen

- `./dashboard/data/homarr/appdata:/appdata`

## Red

- `rem-network` (externa)

## Comandos

```bash
docker compose -f dashboard-compose.yaml up -d
docker compose -f dashboard-compose.yaml down
```
