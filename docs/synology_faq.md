# Synology Docker FAQ

## ❓ Common Issues

### 🔧 Q: My container can't access GPU on Synology.
**A:** Ensure you're using `devices: - /dev/dri:/dev/dri` and the correct driver:
```yaml
LIBVA_DRIVER_NAME=i965
```
The iHD driver is not compatible with the DS1019+.

---

### 🔒 Q: Container permissions are failing.
**A:** Check that the Synology user running the container has correct group memberships:

```bash
sudo synogroup --memberadd docker <username>
```

And confirm UID/GID match:
```bash
id <username>
```

---

### 📦 Q: My container loses settings after reboot.
**A:** Ensure volumes are mapped correctly to persistent Synology folders, e.g.:

```yaml
- /volume2/docker/appname:/config
- /volume1/data:/data
```

---

## 🧠 Tips

- Use `docker compose config` to validate your YAML.
- Backup with:
```bash
docker compose down
rsync -a /volume1/docker/ /volume2/backups/docker/
```

- Prefer `.env` files to prevent hardcoded secrets in YAML.

