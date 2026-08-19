# 📜 更新日志（Changelog）

本项目所有重要变更都会记录在此文件中。
格式遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/)。

## [2.0.2] - 2026-08-19

### 🐛 修复（地图指南加载）

- 修复“用配置加载地图指南只能加载 30 个节点 / 道具不显示”的问题：`PT.cfg` 新增 `sv_allow_annotations_access_level 2`（完整查看+编辑）与 `sv_annotation_limits_max_rounds_per_half -1`（解除半场前 5 回合限制）
- `guides_menu.cfg` 的 7 个 `load_xxx` 命令现在会先强制设置完整权限（`sv_allow_annotations_access_level 2`）再执行 `annotation_load`，避免进图后游戏模式把权限重置回受限等级
- 说明：竞技 / 回防模式对地图指南有 30 节点硬性上限（2026-03-18 更新规定），完整节点仅在【练习模式】下加载；建议通过游戏 UI（开始游戏 → 练习 → 练习模式 → 勾选“加载地图指南”）建房

## [2.0.1] - 2026-08-15

### 🐛 修复（地图指南加载）

- 定位"地图指南加载报 `Missing file ''`"的问题：原因是用控制台 `map` 命令直接开图（游戏模式为空）导致标注系统无法获取地图名；通过游戏 UI 正常创建练习房间后，`annotation_load` 与自动加载均正常
- `guides_menu.cfg` 与 `PT.cfg` 新增 `annotation_auto_load 1`：进图自动加载本地地图指南，无需手动执行加载命令
- 文档补充地图指南的使用前提（正常练习房）、自动加载说明与创意工坊订阅链接

## [2.0.0] - 2026-08-15

### 🔧 修复

- 修复 `PT.cfg` 中 `default` 命令误写为 `exec Default.exe`（应为 `Default.cfg`），导致无法一键恢复竞技参数的问题
- 修复 `spawn/anubis.cfg` 中 CT 出生点别名多余的转义引号（`\"`）导致命令解析异常的问题
- 修复 `spawn/overpass.cfg` 中 CT 出生点别名缺少 `say` 命令、产生无效指令的问题
- 修复 `spawn/cache.cfg` 出生点数量提示错误（实际 4 个 CT 点，提示误写 5 个）
- 修复 `spawn/spawn.cfg` 地图中英文对照表错误（dust2/inferno/cache 中文名错误）
- 修复 `unbindbindings` 未清除 F6~F9 绑键、遗漏 `[.]` 键的问题
- 修复 `Default.cfg` 使用说明错误（原误写 `exec reset`）与可选解绑列表遗漏 `[.]` 键的问题
- 修复 `guides_menu.cfg` 菜单数量与实际不符（内置 7 张地图指南）及 de_vertigo/de_train 指南缺失导致加载报错的问题
- 修正 `Default.cfg` 中 `mp_maxrounds` 注释与实际数值不一致的问题
- 统一 15 张地图出生点文件的传送提示消息格式（如 Train 原格式不一致）

### ♻️ 重构

- 将刀型循环（`dao` 系列别名）从 `PT.cfg` 拆分为独立模块 `knife.cfg`，`PT.cfg` 作为唯一入口
- 统一全部配置文件的注释格式、段落结构与排版（文件头说明 / 分区标题 / 行内注释对齐）
- 所有功能命令、按键绑定、服务器参数保持与原版完全一致，无行为变更

### 📖 文档

- 重写 `README.md`（中文）与 `README_EN.md`（英文）：新增功能一览、快速开始、按键绑定表、命令速查表、出生点系统说明、地图指南说明、自定义指南、FAQ、目录结构等
- 新增 `CHANGELOG.md` 与 `.gitignore`
- `annotations/` 目录新增说明文档 `annotations/README.md`

## [1.0.0] - 历史版本

- 5.0 及更早版本的变更见 Git 提交记录。
