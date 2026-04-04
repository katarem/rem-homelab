# AI Stack (`ai-compose.yaml`)

Servicios:

- `ollama-gpu`: runtime de modelos locales con soporte GPU (NVIDIA).
- `open-webui`: interfaz web para consumir modelos de Ollama.

## Variables de entorno

Archivo: `ai/.env` (base: `ai/.env.example`)

- `OLLAMA_DATA_PATH`
- `OLLAMA_GPU_OVERHEAD`
- `WEBUI_SECRET_KEY`

## Puertos

- `1134:1134` (ollama-gpu)
- `8080:8080` (open-webui)

## Volúmenes

- `./ai/data/ollama:/root/.ollama`
- `./ai/data/openwebui/data:/data`
- `./ai/data/openwebui/models:/models`
- `./ai/data/openwebui/open-webui:/app/backend/data`

## Comandos

```bash
docker compose -f ai-compose.yaml up -d
docker compose -f ai-compose.yaml down
```
