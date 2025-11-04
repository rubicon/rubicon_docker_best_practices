![Docker Compose CI](https://github.com/yourusername/docker_best_practices/actions/workflows/docker-compose-ci.yml/badge.svg)

# 🐳 Dax's Docker Compose Best Practices (Synology DSM 7+)

This repository contains a hardened, production-ready Docker Compose best practices guide specifically tailored for Synology DSM 7.2+ environments.

## 📁 Contents

- `docker_compose_best_practices.md` – Full Markdown Guide
- `docker_compose_best_practices.pdf` – Printable PDF Version

## 📦 Use Cases

- Media servers (Plex, Jellyfin, Sonarr, Radarr)
- Intel VAAPI hardware acceleration (e.g., DS1019+)
- Secure container deployments with dedicated users and permissions
- Auto-updating containers with Watchtower or Pullio

## 🔐 Features

- User & group security hardening
- Volume mapping best practices
- Healthchecks, labels, restart policies
- Hardware acceleration for Intel Quick Sync
- Safe networking strategies (host vs bridge)

## 📄 Licensing

MIT License
