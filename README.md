# PlusCraft (Fabric 1.21.11)

Open-source host-and-social mod by LOVE-YT (@Loveyt224) & NotHeartYT.

## Build
Requires JDK 21.

    gradle wrapper --gradle-version 9.2.1   # once, if gradlew is missing
    ./gradlew build

Jar: `build/libs/pluscraft-1.0.0.jar`. Needs Fabric Loader 0.18.1+ and Fabric API.
If a version in `gradle.properties` is not found, take the current ones from https://fabricmc.net/develop.

## What works now
| Feature | How |
|---|---|
| Host a single-player world | `/pc host [port]` (direct IP:port, needs a reachable port) |
| Whitelist / blacklist | `/pchost whitelist\|blacklist add\|remove <name>`, `/pchost whitelist-mode on\|off` |
| Per-player roles | `/pchost role <name> spectator\|visitor\|builder\|operator` |
| Lobby limit | `maxPeers` in `config/pluscraft.json` (default 8) |
| Offline-account hosting | `/pc offline-mode on` sets online-mode=false for the hosted session (off by default) |
| Friends list (local) | `/pc friends list\|add\|remove` |

Host commands only work for the world owner (first player in the integrated server).

## Roadmap (not implemented yet)
These need substantial extra work and, for the social parts, a signalling/relay service:
- WebRTC/STUN/TURN hole punching (no port forwarding)
- Cross-world DMs, groups, live friend presence, direct invites
- Screenshot editor and link sharing
- Cosmetics: .bbmodel models, animated GIF/APNG capes, emotes
- Custom skin loading (CustomSkinLoader / Ely.by), in-menu account switcher
- Discord Rich Presence
- Pause-menu host UI (needs screen mixins)

Notes: Yarn names shift between builds; if a call fails to compile, check it against your Yarn 1.21.11 build.
