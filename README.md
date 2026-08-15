# 🎮 CS2 练习配置（跑图模式）

[![CS2](https://img.shields.io/badge/CS2-Counter%20Strike%202-orange)](https://www.counter-strike.net/)
[![Version](https://img.shields.io/badge/version-2.0.0-blue)](CHANGELOG.md)
[![Author](https://img.shields.io/badge/author-Bad0RANG3-9cf)](https://space.bilibili.com/482966540)

> **为 CS2 跑图 / 练习量身打造的一整套配置文件**：练习服务器参数一键加载、投掷物轨迹与落点显示、出生点传送、刀型循环、地图指南（烟点/道具标注）……开箱即用。

📖 **English Version**: [README_EN.md](README_EN.md) ・ 📜 **更新日志**: [CHANGELOG.md](CHANGELOG.md)

---

## 📑 目录

- [✨ 功能一览](#-功能一览)
- [📦 快速开始](#-快速开始)
- [⌨️ 按键绑定总览](#️-按键绑定总览)
- [📟 控制台命令速查](#-控制台命令速查)
- [🏁 出生点传送系统](#-出生点传送系统)
- [🗺️ 地图指南（Annotations）](#️-地图指南annotations)
- [🛠️ 自定义指南](#️-自定义指南)
- [❓ 常见问题（FAQ）](#-常见问题faq)
- [📁 目录结构](#-目录结构)
- [🔗 相关链接](#-相关链接)

---

## ✨ 功能一览

| 功能 | 说明 | 入口 |
| --- | --- | --- |
| 🔫 无限备弹 | 备弹无限（`sv_infinite_ammo 2`，含无需换弹模式） | 加载 PT 自动生效 |
| 🎯 子弹落点显示 | 服务器与客户端双重命中判定箱显示 | 加载 PT 自动生效 |
| 🧨 无限道具 | 投掷物携带上限 5 个，随意练习 | 加载 PT 自动生效 |
| 🪢 重投/清道具 | 一键重投上一次道具、一键清空场上所有投掷物 | `AG` / `QC` |
| 🦅 飞天穿墙 | 自由探索地图（noclip） | `CQ` |
| 🔪 刀型循环 | 20 种刀型一键循环切换 | `HD` |
| ⏱ 无限回合时间 | 回合 60 分钟、胜利条件关闭、秒复活 | 加载 PT 自动生效 |
| 👁 视野放大 | 动态放大 FOV，看清瞄点细节 | `FOV` |
| 🤖 BOT 控制 | 踢出/添加/放置/站蹲/模仿，自定义训练场景 | `BOT` |
| 🛡 护甲补满 | 一键补满护甲 | `BJ` |
| 🏁 出生点传送 | 15 张地图的 CT/T 出生点一键传送 | `spawn` |
| 🗺 地图指南 | 内置 7 张地图的烟点/道具标注 | `guide` |
| 🔄 恢复竞技参数 | 一键还原官方竞技模式设置 | `default` |

---

## 📦 快速开始

### 1️⃣ 安装

1. Steam 库 → **CS2** → 右键 → **管理** → **浏览本地文件**
2. 进入 `game\csgo\cfg` 目录
3. 将本仓库 `game\csgo\cfg` 下的**全部内容**（含 `spawn` 子目录）复制进去
4. （可选）将本仓库 `game\csgo\annotations` 目录复制到 `game\csgo\` 下，获得内置地图指南

> 目录结构：`Counter-Strike Global Offensive\game\csgo\cfg\`（配置）、`...\game\csgo\annotations\`（地图指南）

### 2️⃣ 使用

1. 启动 CS2，创建一个**离线练习房间**（或本地服务器）
2. 打开控制台（`~`），输入 `exec PT`
3. 按需输入功能命令（见下方表格），或在控制台输入 `showmenu` 随时查看功能菜单
4. 练习完毕输入 `default` 恢复竞技模式参数

> 💡 **提示**：想一键跑图？把 `exec PT` 绑定到任意按键：`bind <按键> "exec PT"`

---

## ⌨️ 按键绑定总览

> ⚠️ **按需绑键设计**：本配置**不会**在加载时覆盖你的键位——输入对应的『命令』后才会绑定对应按键。

| 按键 | 功能 | 启用命令 |
| --- | --- | --- |
| `F1` | 补满护甲 | `BJ` |
| `F2` | 循环切换刀型 | `HD` |
| `F5` | 移除所有机器人 | `BOT` |
| `F6` | 添加随机阵营机器人 | `BOT` |
| `F7` | 在准心位置生成机器人 | `BOT` |
| `F8` | 切换机器人站姿/蹲姿 | `BOT` |
| `F9` | 开关动作模仿模式 | `BOT` |
| `V` | 放大视野（再按恢复） | `FOV` |
| `C` | 穿墙模式（noclip） | `CQ` |
| `,` | 重新投掷上一次道具 | `AG` |
| `.` | 清空场上所有投掷物 | `QC` |

> 一键清除以上全部绑键：输入 `unbindbindings`

---

## 📟 控制台命令速查

| 命令 | 功能 | 备注 |
| --- | --- | --- |
| `BOT` | 绑定 F5~F9 机器人控制键 | 需先执行 |
| `FOV` | 绑定 V 键放大视野 | 需先执行 |
| `CQ` | 绑定 C 键穿墙 | 需先执行 |
| `QC` | 绑定 `.` 键清空投掷物 | 需先执行 |
| `AG` | 绑定 `,` 键重投上次道具 | 需先执行 |
| `HD` | 绑定 F2 键循环切刀 | 需先执行 |
| `BJ` | 绑定 F1 键补满护甲 | 需先执行 |
| `dao` | 直接手动切换刀型 | 不依赖绑键 |
| `spawn` | 启用出生点传送系统 | 见下方说明 |
| `guide` | 打开地图指南菜单 | 见下方说明 |
| `showmenu` | 显示功能菜单 | 随时可用 |
| `unbindbindings` | 清除全部绑键 | 随时可用 |
| `default` | 恢复竞技模式参数 | 随时可用 |

---

## 🏁 出生点传送系统

使用三步走：

```
spawn          ← ① 启用系统
dust2          ← ② 输入地图名加载该图出生点
CT1 / T3       ← ③ 输入 CT1~CT15 / T1~T15 传送
```

**内置 15 张地图**（含中英文对照）：

| 地图名 | 中文名 | 地图名 | 中文名 |
| --- | --- | --- | --- |
| `dust2` | 炙热沙城 II | `overpass` | 死亡游乐园 |
| `inferno` | 炼狱小镇 | `train` | 列车停放站 |
| `mirage` | 荒漠迷城 | `cache` | 死城之谜 |
| `ancient` | 远古遗迹 | `office` | 办公室 |
| `nuke` | 核子危机 | `italy` | 意大利小镇 |
| `vertigo` | 殒命大厦 | `pool_day` | 泳池日 |
| `anubis` | 阿努比斯 | `shoots` | 射击练习 |
| | | `baggage` | 行李仓库 |

> 💡 每张图的实际出生点数量不同（加载后会提示，如 `地图: Dust2 | CT: 5个出生点 | T: 15个出生点`）；输入不存在的编号只会得到提示，不会报错。

---

## 🗺️ 地图指南（Annotations）

地图指南是游戏内的**地图标注**——在跑图时直接显示烟雾弹、燃烧瓶等投掷物的**落点与瞄准参考**。

- 输入 `guide` 打开菜单，再输入 `load_dust2` 等命令加载对应地图指南
- **内置 7 张地图**：炙热沙城 II、炼狱小镇、荒漠迷城、核子危机、远古遗迹、阿努比斯、死亡游乐园
- 数据文件位于 `game/csgo/annotations/local/<地图名>/`，详见 [annotations/README.md](annotations/README.md)

---

## 🛠️ 自定义指南

### 修改按键
编辑 `PT.cfg` 中对应别名里的 `bind` 行即可，例如把穿墙从 `C` 键改到 `X` 键：

```cfg
alias "CQ" "exec showmenu; bind X noclip"
```

### 自定义刀型列表
编辑 `knife.cfg`：文件中附有全部 20 种刀型的 ID 对照表，替换任意一行的 ID 与名称即可：

```cfg
alias "dao1" "subclass_create 515; alias dao dao2; say 已生成刀：蝴蝶刀"
```

### 修改练习参数
所有服务器参数集中在 `PT.cfg` 的「③ 练习模式服务器参数」区块，每条都有中文注释，按需修改数值即可。

### 添加新地图出生点
1. 复制 `spawn/` 下任意一个地图文件，重命名为新地图名（如 `spawn/aztec.cfg`）
2. 用游戏内 `getpos_exact` 获取坐标，替换文件中的坐标与角度
3. 在 `spawn/spawn.cfg` 的地图别名区添加一行：`alias "aztec" "exec spawn/aztec.cfg"`

### 添加地图指南
把他人分享的标注文件放入 `game/csgo/annotations/local/<地图名>/` 下，然后在 `guides_menu.cfg` 中按相同格式添加一行 `load_xxx` 别名。

---

## ❓ 常见问题（FAQ）

**Q：加载后部分功能没有生效？**
请确认你处于**离线练习房间 / 本地服务器**。部分指令（noclip、subclass_create、setpos 等）依赖 `sv_cheats 1`，PT 配置会自动开启。

**Q：按 F1~F9 没有反应？**
本配置采用按需绑键：需要先输入对应的启用命令（如 `BOT`、`HD`、`BJ`）才会绑定按键。

**Q：如何完全恢复官方设置？**
输入 `default`（或 `exec Default.cfg`），房间参数会恢复为竞技模式并自动重启；建议再换图或重进一次游戏确保完全生效。

**Q：按键和我自己的键位冲突了？**
输入 `unbindbindings` 一键清除本配置的全部绑键，然后修改 `PT.cfg` 中的绑定即可。

**Q：输入 `default` 提示未知命令？**
需要先执行过 `exec PT`（别名在 PT.cfg 中定义），或直接输入 `exec Default.cfg`。

**Q：想练习连跳等进阶操作？**
`PT.cfg` 参数区已使用官匹 VNL 参数，可在加载 PT 后自行追加 `sv_autobunnyhopping 1` 等指令（需要练习房间支持）。

---

## 📁 目录结构

```
CS2PraticeCFG/
├── README.md                  # 中文文档
├── README_EN.md               # English documentation
├── CHANGELOG.md               # 更新日志
└── game/csgo/
    ├── cfg/                   # ★ 全部配置文件（复制到 game\csgo\cfg\）
    │   ├── PT.cfg             #   入口：功能命令 + 练习参数（加载它即可）
    │   ├── knife.cfg          #   刀型循环模块（PT 自动加载）
    │   ├── Default.cfg        #   恢复竞技模式参数（default 命令）
    │   ├── showmenu.cfg       #   功能菜单显示
    │   ├── guides_menu.cfg    #   地图指南菜单
    │   ├── QC.cfg             #   清空投掷物（绑定 [.]）
    │   └── spawn/             #   出生点传送系统
    │       ├── spawn.cfg      #   入口：地图别名 + 对照表
    │       ├── init_spawns.cfg#   占位初始化（地图文件自动加载）
    │       └── <地图>.cfg     #   15 张地图的出生点坐标
    └── annotations/           # ★ 地图指南数据（复制到 game\csgo\）
        ├── rgb.txt            #   标注颜色定义
        └── local/<地图>/      #   各地图标注文件（KV3 格式）
```

---

## 🔗 相关链接

- 🎬 [跑图配置使用教程（B站）](https://www.bilibili.com/video/BV1HSe6ehE8g)
- 👤 [Bad0RANG3 的 B站主页](https://space.bilibili.com/482966540)
- 🐙 [GitHub 主页](https://github.com/Bad0RANG3)
- ⚙️ [更多游戏设置（Settings.gg）](https://settings.gg/Bad0RANG3)

---

📜 项目所有变更见 [CHANGELOG.md](CHANGELOG.md)。觉得好用的话给个 ⭐ 吧！
