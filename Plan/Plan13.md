# Plan13

- **Date**: 2026-08-08
- **Time**: 17:46 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan12.md
- **Session goal**: 给出龙蛇洞窟/地下城遗迹「外置入口 + 主线寻找 + 限时开启」玩法方案

## Scope

- In scope: 玩法设计、与现有主线/遗迹/传送门系统的落点
- Out of scope: 直接改代码实现

## Steps

1. 对照现有主线探索、Type13 门、DungeonExplore 流程
2. 输出可落地的玩法方案（流程、状态、配表、UI、风险）
3. commit + push Plan13

## Success criteria

- [x] 用户获得完整玩法方案
- [ ] Plan13 已推送

## Notes

- 复用 LevelType.Dungeon + DungeonExplorePortal / Dungeon_Dungeon，避免新开一套战斗模块
