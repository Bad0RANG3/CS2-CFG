# 🗺️ 地图指南（Annotations）

本目录存放 CS2 游戏内的**地图标注数据**（annotation）——跑图练习时直接显示在游戏世界中的投掷物落点、瞄准参考等信息。

## 目录结构

```
annotations/
├── rgb.txt                    # 标注颜色名称与 RGB 值的对照（编辑器配色使用）
└── local/<地图名>/<地图名>.txt # 各地图的标注数据（KV3 格式，与游戏官方文件同构）
```

## 内置地图指南（7 张）

| 地图 | 数据文件 |
| --- | --- |
| 炙热沙城 II（Dust II） | `local/de_dust2/de_dust2.txt` |
| 炼狱小镇（Inferno） | `local/de_inferno/de_inferno.txt` |
| 荒漠迷城（Mirage） | `local/de_mirage/de_mirage.txt` |
| 核子危机（Nuke） | `local/de_nuke/de_nuke.txt` |
| 远古遗迹（Ancient） | `local/de_ancient/de_ancient.txt` |
| 阿努比斯（Anubis） | `local/de_anubis/de_anubis.txt` |
| 死亡游乐园（Overpass） | `local/de_overpass/de_overpass.txt` |

## 使用方式

1. 确保本目录已复制到 CS2 的 `game\csgo\` 下（与 `cfg` 目录同级）
2. **通过游戏 UI 正常创建练习房间**（开始游戏 → 练习），不要用控制台 `map` 命令直接开图
3. 加载 PT 配置（已开启 `annotation_auto_load 1`），进入有指南的地图即**自动显示**；
   也可以输入 `guide` 打开指南菜单，用 `load_dust2` 等命令手动加载
4. 或直接在控制台输入 `annotation_load <地图名>` 手动加载

> ⚠️ **注意**：用控制台 `map` 命令直接开图（游戏模式为空）会导致标注加载失败，报
> `Annotation: Error loading file : Missing file ''`。走游戏 UI 正常流程创建练习房即可解决。

## 创意工坊（可选）

以下 4 张地图的指南已发布到创意工坊，**订阅后游戏自动加载**（无需本地文件，适合分享给朋友）：

- [MIRAGE中文道具批注](https://steamcommunity.com/sharedfiles/filedetails/?id=3527779856)
- [Dust2中文道具批注](https://steamcommunity.com/sharedfiles/filedetails/?id=3528590225)
- [INFERNO中文道具批注](https://steamcommunity.com/sharedfiles/filedetails/?id=3527834272)
- [Ancient中文道具批注](https://steamcommunity.com/sharedfiles/filedetails/?id=3528643942)

## 补充 / 新增指南

- 把他人分享的标注文件放入 `local/<地图名>/` 目录（文件名需与地图名一致，如 `local/de_vertigo/de_vertigo.txt`）
- 然后在 `cfg/guides_menu.cfg` 中按相同格式添加一行 `load_xxx` 别名（文件内已有注释示例）
- 标注颜色可在 `rgb.txt` 中自定义
- 想分享自己的指南？游戏内输入 `workshop_annotation_submit <工坊ID>` 提交到创意工坊
