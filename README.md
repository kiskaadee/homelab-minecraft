# ⛏️ Homelab Minecraft (Paper + Web Auth Admin)

Dedicated Paper Minecraft server with AuthMe integration and a custom FastAPI web administration dashboard.

Part of the [homelab-core](https://github.com/kiskaadee/homelab-core) cluster ecosystem.

---

## 🏗️ Architecture & Stack

- **Game Server**: `itzg/minecraft-server:latest` (Paper 1.21+, Port `25565`)
- **Web Admin**: Custom FastAPI dashboard in `./web/` (Port `8000`)
- **Storage**: `./data` (server world files, plugins, and configs — gitignored)
- **Domain**: `minecraft.arch-services.mywire.org`

---

## ⚙️ Environment Variables & Secrets

| Variable | Description | Default / Example |
| :--- | :--- | :--- |
| `MINECRAFT_DOMAIN` | Web Admin FQDN | `minecraft.arch-services.mywire.org` |
| `PORT` | Minecraft TCP game port | `25565` |
| `MEMORY` | Allocated JVM Heap memory | `2G` |
| `MINECRAFT_JWT_SECRET` | Secret token for web auth | Injected from SOPS |

---

## 🚀 Deployment

### Via Orchestrator (`appctl`)
```bash
appctl up homelab-minecraft
```

### Manual Deployment
```bash
docker compose up --build -d
```
