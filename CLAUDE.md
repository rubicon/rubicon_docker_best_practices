# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Documentation and reference project for Docker Compose best practices targeting Synology DSM 7.2+ environments. The live site is published via MkDocs Material to GitHub Pages.

## Commands

### Local docs development

```bash
# Install dependencies (one-time)
pip install mkdocs mkdocs-material

# Serve docs locally with live reload
mkdocs serve

# Build static site
mkdocs build --config-file mkdocs.yml
```

> **Note:** `mkdocs.yml` must have `docs_dir: mkdocs/docs` set — MkDocs defaults to `docs/` at the repo root, which doesn't exist. Without this, both `serve` and `build` will fail.

### Validate compose files

```bash
docker compose -f compose/docker-compose.yaml config
docker compose -f compose/n8n-compose.yaml config
```

## Architecture

**Documentation** lives in `mkdocs/docs/` and is configured via `mkdocs.yml` at the root. The navigation structure in `mkdocs.yml` must be updated whenever docs pages are added or removed — MkDocs doesn't auto-discover pages.

**Compose examples** in `compose/` each have a corresponding doc page in `mkdocs/docs/compose/`. When adding a new compose example, create both the YAML in `compose/` and the documentation in `mkdocs/docs/compose/`, then add it to `mkdocs.yml` nav.

**CI/CD**: GitHub Actions in `.github/workflows/` handles:

- `deploy-mkdocs.yml` — builds and deploys to GitHub Pages on push to `main`
- `docker-compose-ci.yml` — validates compose file syntax on push/PR

**Env template** at `env/.env.example` uses Synology-specific defaults (PUID=1026, PGID=65542).

## Compose File Conventions

All compose examples follow these patterns:

- OCI labels (`org.opencontainers.image.*`) on every service
- Healthcheck with `interval`, `timeout`, `retries`, `start_period`
- `restart: unless-stopped`
- `PUID`/`PGID`/`TZ` environment variables
- `/etc/localtime:/etc/localtime:ro` volume mount
- Named volumes or explicit bind mounts under `/volume1/docker/`
