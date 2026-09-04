# ⛏️ Homelab Minecraft (PaperMC & Live Map)

PaperMC high-performance Minecraft dedicated server with real-time web map rendering (BlueMap).

---

## 🏗️ Architecture & Requirements

- **Proxy Network**: Attached to external `proxy-net`
- **Domain**: `minecraft.roadtotech.me` (Web Map)
- **Game Port**: `25565` (Direct TCP connection)
- **Web Map Port**: `8100`

---

## ⚙️ Configuration & Metadata (`app.yaml`)

```yaml
name: "minecraft"
aliases:
  - "mc"
  - "server"
domain: "minecraft.roadtotech.me"
description: "PaperMC Minecraft Server with Bluemap Live View"
visible: true
auth: false
networks:
  - proxy-net
env:
  MINECRAFT_DOMAIN: "minecraft.roadtotech.me"
homepage:
  title: "Minecraft"
  group: "Media & Productivity"
  icon: "minecraft.png"
  container: "minecraft-server"
  weight: 20
```

---

## 🚀 Deployment

### Via Orchestrator (`appctl`)
```bash
appctl up minecraft
# or using shortcut alias
appctl up mc
```

### Manual Deployment
```bash
docker compose up -d
```

---

## 📄 License
This repository is released into the public domain under the [Unlicense](LICENSE).
