# Workspace instructions for AI agents

This repository is a documentation/reference project for Docker Compose best practices on Synology DSM 7.2+.

## Getting started

- **Docs** live under `mkdocs/docs/` and are published with MkDocs Material. The root config is `mkdocs.yaml` which sets `docs_dir: mkdocs/docs` (nonstandard).
- To work locally run:
  ```bash
  pip install mkdocs mkdocs-material      # one-time
  mkdocs serve                           # local live reload
  mkdocs build --config-file mkdocs.yaml  # build static site
  ```
- Docker Compose examples live in `compose/`. Every YAML file should have a corresponding documentation page in `mkdocs/docs/compose/` and must be added to the `nav` section of `mkdocs.yaml` manually. MkDocs does **not** auto-discover pages.
- Validate compose files before committing:
  ```bash
  docker compose -f compose/docker-compose.yaml config
  docker compose -f compose/n8n-compose.yaml config
  ```

## Key conventions

- Compose files must include these patterns:
  - OCI labels (`org.opencontainers.image.*`) on every service
  - Healthcheck with `interval`, `timeout`, `retries`, `start_period`
  - `restart: unless-stopped`
  - `PUID`/`PGID`/`TZ` environment variables
  - `/etc/localtime:/etc/localtime:ro` bind mount
  - Named volumes or explicit binds under `/volume1/docker/`
- The `env/.env.example` template sets Synology-specific defaults (PUID=1026, PGID=65542).

## CI/CD

- Workflow files are in `.github/workflows/`:
  - `deploy-mkdocs.yaml` builds & deploys to GitHub Pages on push to `main`.
  - `docker-compose-ci.yaml` validates compose syntax on pushes/PRs.

## File structure overview

```
mkdocs.yaml              # MkDocs config
mkdocs/docs/            # documentation source
compose/                # Docker Compose examples
env/                    # environment templates
scripts/                # helper scripts (mostly docs)
```

## Tips for AI assistants

1. When adding or editing docs, always update `mkdocs.yaml` nav.
2. Preserve formatting and YAML examples exactly; the site renders code blocks.
3. Use `docker compose config` to sanity‑check any changes to the YAML examples.
4. There is no build/test target beyond docs and compose validation.

> ⚠️ There’s no Makefile or build system; don’t invent one unless you ask first.

---

You can now answer queries about the repo by referencing these instructions. For tasks that touch only specific folders (e.g. `compose/` or `mkdocs/docs/`), consider using `applyTo` rules in additional agent customizations.
