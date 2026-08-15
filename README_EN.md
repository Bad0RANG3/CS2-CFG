# 🎮 CS2 Practice Configuration

[![CS2](https://img.shields.io/badge/CS2-Counter%20Strike%202-orange)](https://www.counter-strike.net/)
[![Version](https://img.shields.io/badge/version-2.0.0-blue)](CHANGELOG.md)
[![Author](https://img.shields.io/badge/author-Bad0RANG3-9cf)](https://space.bilibili.com/482966540)

> **A complete, ready-to-use configuration pack for CS2 practice / map studying**: one-command practice server setup, grenade trajectory & impact display, spawn teleportation, knife cycling, and in-game map guides (smoke/flash lineups).

🌐 **中文版**: [README.md](README.md) ・ 📜 **Changelog**: [CHANGELOG.md](CHANGELOG.md)

---

## 📑 Table of Contents

- [✨ Features](#-features)
- [📦 Quick Start](#-quick-start)
- [⌨️ Key Bindings](#️-key-bindings)
- [📟 Console Commands](#-console-commands)
- [🏁 Spawn Teleport System](#-spawn-teleport-system)
- [🗺️ Map Guides (Annotations)](#️-map-guides-annotations)
- [🛠️ Customization](#️-customization)
- [❓ FAQ](#-faq)
- [📁 Project Structure](#-project-structure)
- [🔗 Links](#-links)

---

## ✨ Features

| Feature | Description | Entry |
| --- | --- | --- |
| 🔫 Infinite ammo | Unlimited reserve ammo (`sv_infinite_ammo 2`, includes no-reload mode) | Auto on PT load |
| 🎯 Bullet impacts | Server & client-side hitbox impact display | Auto on PT load |
| 🧨 Unlimited grenades | Carry up to 5 grenades for endless throw practice | Auto on PT load |
| 🪢 Rethrow / Clear nades | Rethrow last grenade / clear all grenades instantly | `AG` / `QC` |
| 🦅 Noclip | Fly through walls to explore the map | `CQ` |
| 🔪 Knife cycling | Cycle through 20 knife models with one key | `HD` |
| ⏱ Infinite round time | 60-min rounds, win conditions off, instant respawn | Auto on PT load |
| 👁 Zoomed FOV | Dynamic FOV zoom for studying angles | `FOV` |
| 🤖 Bot control | Kick / add / place / crouch / mimic for custom scenarios | `BOT` |
| 🛡 Full armor | One-key armor refill | `BJ` |
| 🏁 Spawn teleports | CT/T spawn points for 15 maps | `spawn` |
| 🗺 Map guides | In-game annotations (lineups) for 7 maps | `guide` |
| 🔄 Competitive reset | Restore official competitive settings | `default` |

---

## 📦 Quick Start

### 1️⃣ Install

1. Steam library → **CS2** → right-click → **Manage** → **Browse local files**
2. Open the `game\csgo\cfg` folder
3. Copy **everything** from this repo's `game\csgo\cfg` (including the `spawn` subfolder) into it
4. *(Optional)* Copy this repo's `game\csgo\annotations` into `game\csgo\` for the built-in map guides

> Layout: `Counter-Strike Global Offensive\game\csgo\cfg\` (configs) + `...\game\csgo\annotations\` (map guides)

### 2️⃣ Use

1. Launch CS2 and create an **offline practice lobby** (or a local server)
2. Open the console (`~`) and type `exec PT`
3. Type the commands you need (see table below), or type `showmenu` anytime to view the feature menu
4. When done, type `default` to restore competitive settings

> 💡 **Tip**: want one-key practice? Bind it: `bind <key> "exec PT"`

---

## ⌨️ Key Bindings

> ⚠️ **Bind-on-demand design**: the config never overwrites your binds on load — keys are bound only after you type the corresponding command.

| Key | Function | Enable with |
| --- | --- | --- |
| `F1` | Refill armor | `BJ` |
| `F2` | Cycle knife models | `HD` |
| `F5` | Kick all bots | `BOT` |
| `F6` | Add random bot | `BOT` |
| `F7` | Place bot at crosshair | `BOT` |
| `F8` | Toggle bot stand/crouch | `BOT` |
| `F9` | Toggle bot mimic mode | `BOT` |
| `V` | Toggle FOV zoom | `FOV` |
| `C` | Toggle noclip | `CQ` |
| `,` | Rethrow last grenade | `AG` |
| `.` | Clear all grenades | `QC` |

> Clear all these binds at once: type `unbindbindings`

---

## 📟 Console Commands

| Command | Function | Notes |
| --- | --- | --- |
| `BOT` | Bind F5~F9 bot control keys | Run first |
| `FOV` | Bind V to FOV zoom | Run first |
| `CQ` | Bind C to noclip | Run first |
| `QC` | Bind `.` to clear grenades | Run first |
| `AG` | Bind `,` to rethrow last nade | Run first |
| `HD` | Bind F2 to cycle knives | Run first |
| `BJ` | Bind F1 to refill armor | Run first |
| `dao` | Cycle knives manually | No bind needed |
| `spawn` | Enable spawn teleport system | See below |
| `guide` | Open map guides menu | See below |
| `showmenu` | Show the feature menu | Always available |
| `unbindbindings` | Clear all config binds | Always available |
| `default` | Restore competitive settings | Always available |

---

## 🏁 Spawn Teleport System

Three steps:

```
spawn          ← ① Enable the system
dust2          ← ② Load a map by name
CT1 / T3       ← ③ Teleport with CT1~CT15 / T1~T15
```

**15 built-in maps:**

| Map | Map | Map |
| --- | --- | --- |
| `dust2` | `nuke` | `office` |
| `inferno` | `vertigo` | `italy` |
| `mirage` | `anubis` | `pool_day` |
| `ancient` | `overpass` | `shoots` |
| `train` | `cache` | `baggage` |

> 💡 Each map has a different number of spawns (shown on load, e.g. `Map: Dust2 | CT: 5 spawns | T: 15 spawns`). Invalid numbers only show a warning — no errors.

---

## 🗺️ Map Guides (Annotations)

Map guides are **in-game annotations** that show grenade **lineups and aim references** while you practice.

- Type `guide` to open the menu, then `load_dust2` etc. to load a map's guide
- **7 maps bundled**: Dust II, Inferno, Mirage, Nuke, Ancient, Anubis, Overpass
- Data lives in `game/csgo/annotations/local/<map>/` — see [annotations/README.md](annotations/README.md)

---

## 🛠️ Customization

### Change a keybind
Edit the `bind` part of the matching alias in `PT.cfg`, e.g. move noclip from `C` to `X`:

```cfg
alias "CQ" "exec showmenu; bind X noclip"
```

### Custom knife list
Edit `knife.cfg` — it contains the ID table for all 20 knives. Swap the ID/name of any line:

```cfg
alias "dao1" "subclass_create 515; alias dao dao2; say Knife: Butterfly"
```

### Tweak practice parameters
All server cvars live in the `③ Practice server settings` block of `PT.cfg`, each with a Chinese comment. Adjust values as you like.

### Add a new map's spawns
1. Copy any file in `spawn/`, rename it to your map (e.g. `spawn/aztec.cfg`)
2. Grab coordinates in-game with `getpos_exact` and replace the values
3. Add a line to `spawn/spawn.cfg`: `alias "aztec" "exec spawn/aztec.cfg"`

### Add map guides
Drop shared annotation files into `game/csgo/annotations/local/<map>/`, then add a matching `load_xxx` alias in `guides_menu.cfg`.

---

## ❓ FAQ

**Q: Some features don't work after loading?**
Make sure you are in an **offline practice lobby / local server**. Commands like noclip, `subclass_create` and `setpos` require `sv_cheats 1`, which the PT config enables automatically.

**Q: F1~F9 do nothing when pressed?**
This config binds keys on demand — type the enabling command first (e.g. `BOT`, `HD`, `BJ`).

**Q: How do I fully restore official settings?**
Type `default` (or `exec Default.cfg`). The lobby resets to competitive parameters and restarts automatically; change map or restart the game once for a fully clean state.

**Q: A bind conflicts with mine?**
Type `unbindbindings` to clear all config binds, then edit the bind in `PT.cfg`.

**Q: `default` says unknown command?**
Run `exec PT` first (aliases are defined there), or use `exec Default.cfg` directly.

---

## 📁 Project Structure

```
CS2PraticeCFG/
├── README.md                  # Chinese documentation
├── README_EN.md               # English documentation
├── CHANGELOG.md               # Changelog
└── game/csgo/
    ├── cfg/                   # ★ All configs (copy to game\csgo\cfg\)
    │   ├── PT.cfg             #   Entry: commands + practice cvars (load this)
    │   ├── knife.cfg          #   Knife cycling module (auto-loaded)
    │   ├── Default.cfg        #   Competitive reset (default command)
    │   ├── showmenu.cfg       #   Feature menu display
    │   ├── guides_menu.cfg    #   Map guides menu
    │   ├── QC.cfg             #   Clear grenades (binds [.])
    │   └── spawn/             #   Spawn teleport system
    │       ├── spawn.cfg      #   Entry: map aliases + name table
    │       ├── init_spawns.cfg#   Placeholder init (auto-loaded)
    │       └── <map>.cfg      #   Spawn coordinates for 15 maps
    └── annotations/           # ★ Map guide data (copy to game\csgo\)
        ├── rgb.txt            #   Annotation color definitions
        └── local/<map>/       #   Per-map annotation files (KV3)
```

---

## 🔗 Links

- 🎬 [Tutorial video (Bilibili)](https://www.bilibili.com/video/BV1HSe6ehE8g)
- 👤 [Bad0RANG3 on Bilibili](https://space.bilibili.com/482966540)
- 🐙 [GitHub profile](https://github.com/Bad0RANG3)
- ⚙️ [More settings (Settings.gg)](https://settings.gg/Bad0RANG3)

---

📜 See [CHANGELOG.md](CHANGELOG.md) for all changes. If you find this useful, give it a ⭐!
