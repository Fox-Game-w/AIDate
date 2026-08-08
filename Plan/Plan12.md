# Plan12

- **Date**: 2026-08-08
- **Time**: 17:37 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan11.md
- **Session goal**: 说明 DungeonExplorePortalStageInteractiveEvent / 遗迹传送门有哪些

## Scope

- In scope: 客户端事件类、交互物 Type=13、DungeonType、配表条目
- Out of scope: 改代码

## Steps

1. 读事件类与 CopyObject/Dungeon 配表
2. 汇总 Type=13 传送门与遗迹类型
3. 回复；commit Plan12（push 若网络允许）

## Success criteria

- [x] 用户获得遗迹传送门清单/分类说明
- [ ] Plan12 push（网络可能仍失败）

## Notes

- 客户端事件类只有 1 个；差异在配表 ObjectId / 目标遗迹池 / DungeonType
