# Documents Stack (`docs-compose.yaml`)

Servicios:

- `paperless`: app principal de gestión documental.
- `db`: PostgreSQL para persistencia.
- `broker`: Redis para colas/cache.
- `gotenberg`: conversión de documentos.
- `tika`: extracción/OCR de contenido.
- `paperless-ai` (profile `ai`): capa AI opcional.

## Variables de entorno

Archivo: `documents/.env` (base: `documents/.env.example`)

- `PAPERLESS_EXPORT_FOLDER`
- `PAPERLESS_CONSUME_FOLDER`
- `PAPERLESS_DATABASE`
- `PAPERLESS_DB_USER`
- `PAPERLESS_DB_PASSWORD`

## Puertos

- `8800:8000` (paperless)
- `8998:9998` (tika)
- `6379:6379` (broker)
- `3100:3000` (paperless-ai, opcional)

## Volúmenes clave

- `./documents/data/paperless/data:/usr/src/paperless/data`
- `./documents/data/paperless/media:/usr/src/paperless/media`
- `./documents/data/db/data:/var/lib/postgresql`
- `./documents/data/broker/data:/data`
- `./documents/data/paperless-ai/data:/app/data`

## Comandos

```bash
docker compose --env-file documents/.env -f docs-compose.yaml up -d
docker compose --env-file documents/.env -f docs-compose.yaml --profile ai up -d
docker compose -f docs-compose.yaml down
```
