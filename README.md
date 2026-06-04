# PPE Essential

PPE Essential is a lightweight server-side mod that adds useful commands (like `/home`, `/warp`, `/tpa`, `/rtp`) and admin controls, with highly configurable options and polished multilingual messages. No dependencies, no client install.

## Features

- Server-side only: players do not need to install the mod on their client.
- No extra dependencies.
- Ready out of the box with common essentials-style commands.
- Polished chat messages, clickable request buttons, titles, and sounds.
- Highly configurable command toggles and permission levels.
- Multilingual message support.
- Persistent player data for homes, warps, back locations, fly, god mode, and notices.

## Supported Versions

| Minecraft | Loader | Mod Version |
| --- | --- | --- |
| 1.21.1 | NeoForge 21.1.233+ | 1.1.0-SNAPSHOT |

## Commands

### Teleport

| Command | Description |
| --- | --- |
| `/tpa <player>` | Request to teleport to another player. |
| `/tpaa` | Accept a pending TPA request. |
| `/tpad` | Deny a pending TPA request. |
| `/tpaauto` | Toggle automatic TPA acceptance. |
| `/tpahere <player>` | Request another player to teleport to you. |
| `/tpaherea` | Accept a pending TPAhere request. |
| `/tpahered` | Deny a pending TPAhere request. |
| `/rtp` | Randomly teleport nearby. |
| `/spawn` | Teleport to world spawn. |
| `/back` or `/dback` | Return to your last death location. |
| `/tback` | Return to your previous teleport location. |

### Homes And Warps

| Command | Description |
| --- | --- |
| `/sethome` | Set your home. |
| `/home` | Teleport home. |
| `/delhome` | Delete your home. |
| `/setwarp <name>` | Create a server warp. |
| `/warp <name>` | Teleport to a server warp. |
| `/delwarp <name>` | Delete a server warp. |

### Utility And Admin

| Command | Description |
| --- | --- |
| `/trash` | Open a temporary trash inventory that clears on close. |
| `/suicide` | Kill yourself. |
| `/heal [player]` | Heal yourself or another player. |
| `/fly [player]` | Toggle flight for yourself or another player. |
| `/god [player]` | Toggle god mode for yourself or another player. |
| `/repeat <times> [command]` | Repeat your last command or a specified command. |
| `/ppe-essential help` | Show the command list. Disabled or unavailable commands are shown in red. |
| `/ppe-essential reset all` | Clear all player data. |
| `/ppe-essential reset notice` | Clear notice trigger data. |

## Configuration

PPE Essential uses a common config file. Command registration toggles require a server restart, while permission level changes are designed to apply without restarting.

General options:

```toml
fallbackLanguage = "en_us"
firstJoinNotice = true
rtpCooldownSeconds = 30
rtpMinDistance = 2000
rtpMaxDistance = 5000
rtpNetherMinDistance = 600
rtpNetherMaxDistance = 1500
teleportRequestTimeoutSeconds = 60
```

Each command has:

```toml
enabled = true
permissionLevel = 0
```

`permissionLevel` uses Minecraft OP permission levels:

| Level | Meaning |
| --- | --- |
| 0 | Everyone can use it. |
| 1-4 | Requires the matching OP permission level. |

## Installation

1. Install NeoForge on the server.
2. Put the PPE Essential jar into the server's `mods` folder.
3. Start the server.
4. Edit the generated config if needed.
5. Restart the server if you changed command `enabled` toggles.

Clients do not need to install this mod.

## Building

```powershell
.\gradlew.bat build --no-daemon
```

The built jar will be generated under:

```text
build/libs/
```

## License

MIT
