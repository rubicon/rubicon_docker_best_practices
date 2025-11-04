# 🐳 Rubicon Docker Compose Best Practices (Synology DSM 7+)

![CI](https://github.com/rubicon/rubicon_docker_best_practices/actions/workflows/docker-compose-ci.yml/badge.svg)
![MkDocs Deploy](https://github.com/rubicon/rubicon_docker_best_practices/actions/workflows/deploy-mkdocs.yml/badge.svg)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-green?logo=github)](https://rubicon.github.io/rubicon_docker_best_practices/)

This repository contains a hardened, production-ready Docker Compose best practices guide specifically tailored for Synology DSM 7.2+ environments.

📘 **Live Docs**:  
🔗 [https://rubicon.github.io/rubicon_docker_best_practices/](https://rubicon.github.io/rubicon_docker_best_practices/)

## 📁 Contents

- `docker_compose_best_practices.md` – Full Markdown Guide
- `docker_compose_best_practices.pdf` – Printable PDF Version
- `mkdocs/` – Structured documentation site with navigation and search

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

## 🧪 CI Integration

This repo uses:
- GitHub Actions for Compose validation (`docker-compose-ci.yml`)
- MkDocs for auto-deployed documentation (`deploy-mkdocs.yml`)

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

## 🔒 Security

See [SECURITY.md](SECURITY.md)

## 📄 Licensing

MIT License
