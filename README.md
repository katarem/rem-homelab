# REM Homelab

Infra de homelab organizada por stacks de servicios, cada uno aislado en su propio archivo `*-compose.yaml`.

## Estructura

- `ai-compose.yaml` → stack de IA local (Ollama + Open WebUI)
- `dashboard-compose.yaml` → dashboard (Homarr)
- `docs-compose.yaml` → gestión documental (Paperless + dependencias)
- `media-compose.yaml` → stack multimedia (Jellyfin y *arr)
- `proxy-compose.yaml` → proxy + DNS dinámico
- `docs/` → documentación detallada por stack

## Requisitos

- Docker + Docker Compose plugin
- Archivos `.env` por stack (copiar desde `*.env.example`)
- Red compartida `rem-network` (externa)

```bash
docker network create rem-network
```

## Levantar un stack

Ejemplo:

```bash
docker compose -f media-compose.yaml up -d
```

Parar:

```bash
docker compose -f media-compose.yaml down
```

## Documentación detallada

- [Índice de documentación](docs/README.md)
- [AI stack](docs/ai/README.md)
- [Dashboard stack](docs/dashboard/README.md)
- [Documents stack](docs/documents/README.md)
- [Media stack](docs/media/README.md)
- [Proxy stack](docs/proxy/README.md)
