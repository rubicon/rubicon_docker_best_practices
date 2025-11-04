# 🐳 Rubicon Docker Compose Best Practices (Synology DSM 7+)

![Docker Compose CI](https://github.com/rubicon/rubicon_docker_best_practices/actions/workflows/docker-compose-ci.yml/badge.svg)

This repository contains a hardened, production-ready Docker Compose best practices guide specifically tailored for Synology DSM 7.2+ environments.

📘 **Live GitHub Pages**:  
🔗 [https://rubicon.github.io/rubicon_docker_best_practices/](https://rubicon.github.io/rubicon_docker_best_practices/)

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

## 🧪 CI Integration

This repo uses GitHub Actions to lint and validate Docker Compose configuration.

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

## 🔒 Security

See [SECURITY.md](SECURITY.md)

## 📄 Licensing

MIT License
