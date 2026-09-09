# Plan101

- **Date**: 2026-09-09
- **Time**: 16:07
- **Project**: noob/Client/Unity
- **Continues**: Plan100.md
- **Session goal**: 修复 Prefab 占用图白色区域与模型占位不符

## Scope

- In scope: PrefabOccupancyMapWindow 栅格/坐标/颜色与 Y=0 截面判定
- Out of scope: 运行时 RoadOccupancyMap 逻辑

## Steps

1. 对照现有 `_e.png` 与 RoadConfig 读法找偏差
2. 改为按格柱体/截面采样，默认白=模型；道路约定可选
3. 截面无命中时自动落到模型底部；写 Bug 并同步 Plan

## Success criteria

- [x] 按格采样 Y 截面，减少中间漏白
- [x] 默认白=模型；可勾选道路约定（黑占用）
- [x] 截面无命中可自动落到模型底部

## Notes

- 文件：Assets/Editor/ToolEditor/PrefabOccupancyMapWindow.cs
- 入口：Tools/关卡工具/Prefab 占用图生成(_e)
- 请在 Unity 里对目标 Prefab 重新生成 `_e.png` 目视确认
