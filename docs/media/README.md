# Media Stack (`media-compose.yaml`)

Servicios:

- `jellyfin`: servidor multimedia.
- `sonarr`: series.
- `radarr`: películas.
- `seerr`: requests de usuarios.
- `qbittorrent`: cliente de descarga.
- `prowlarr`: agregador de indexers.
- `jackett`: indexers alternativos.
- `byparr` (profile `bypass`): bypass opcional.

## Variables de entorno

Archivo: `media/.env` (base: `media/.env.example`)

- `MEDIA_SERIES_PATH`
- `MEDIA_MOVIES_PATH`
- `MEDIA_ANIME_PATH`
- `MEDIA_DOWNLOADS_PATH`

## Puertos principales

- Jellyfin: `8096`, `8920`
- Sonarr: `8989`
- Radarr: `7878`
- Seerr: `5055`
- qBittorrent: `8080`, `6881/tcp`, `6881/udp`
- Prowlarr: `9696`
- Jackett: `9117`

## Red

- `rem-network` (externa)

## Comandos

```bash
docker compose --env-file media/.env -f media-compose.yaml up -d
docker compose --env-file media/.env -f media-compose.yaml --profile bypass up -d
docker compose -f media-compose.yaml down
```
