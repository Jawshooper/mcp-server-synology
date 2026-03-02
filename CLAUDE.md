# Synology MCP Server

Python MCP server for Synology NAS APIs (FileStation, DownloadStation).

## Tech Stack

Python, FastMCP, Docker. Connects to Synology DSM via REST API.

## Structure

- `src/mcp_server.py` — MCP server entry point
- `src/filestation/` — FileStation API client
- `src/downloadstation/` — DownloadStation API client
- `src/auth/` — session auth
- `src/config.py` — settings from env
- `main.py` — standalone entry point
- Docker: `Dockerfile` + `docker-compose.yml`

## Key Constraints

- Auth via `.env` (SYNOLOGY_URL, SYNOLOGY_USER, SYNOLOGY_PASS)
- NAS hostname: JH-NAS-25
- FileStation paths use forward slashes (`/home/Projects/...`)
- Session tokens expire — handle re-auth gracefully

## Commands

```bash
python main.py                      # Run locally
docker-compose up                   # Run in Docker
```
