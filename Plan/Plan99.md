# Plan99

- **Date**: 2026-09-09
- **Time**: 14:51
- **Project**: noob/Client/Unity
- **Continues**: none
- **Session goal**: 制作 Unity 工具：选 Prefab 按主体包围盒生成 16x16 占用图 `_e.png`

## Scope

- In scope:
  - EditorWindow 选 Prefab
  - 按主体 XZ 包围盒俯视栅格化
  - 输出 `{prefabName}_e.png`（黑占用/白空，符合道路占用约定）
- Out of scope:
  - 改运行时道路逻辑

## Steps

1. 对照 RoadConfig `_e` 约定
2. 实现 PrefabOccupancyMapWindow
3. 写入 Plan 并回复入口

## Success criteria

- [x] Tools 菜单可打开工具
- [x] 可选 Prefab 生成 16x16 `_e.png`
- [x] 边界为主体 Prefab 包围盒

## Notes

- RoadConfig: 黑色占用，纯白未占用
- 用户原文写白=模型；工具默认跟项目约定（黑=模型），提供反转选项
- 入口：Tools/关卡工具/Prefab 占用图生成(_e)
- 文件：Assets/Editor/ToolEditor/PrefabOccupancyMapWindow.cs
