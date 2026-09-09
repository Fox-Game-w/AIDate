# Plan102

- **Date**: 2026-09-09
- **Time**: 17:06
- **Project**: noob/Client/Unity
- **Continues**: Plan101.md
- **Session goal**: 修复 Copy_F_road_06_04 占用图：红圈岩石区域应全黑

## Scope

- In scope: PrefabOccupancyMapWindow 采样改为贴合俯视占位；默认黑=占用
- Out of scope: 手改已有 `_e.png` 美术资源

## Steps

1. 分析 prefab / 现 `_e.png`（33 黑边、与岩石不符）
2. 默认改为俯视剪影 + 排除扁平地面 + 黑=占用
3. 更新 Bug 并同步；请用户在 Unity 重导验证

## Success criteria

- [x] 工具改为俯视占位，默认黑占用、可排除地面
- [ ] 用户对 Copy_F_road_06_04 重导后岩石区为实心黑

## Notes

- 文件：Assets/Editor/ToolEditor/PrefabOccupancyMapWindow.cs
- 旧 Y=0 薄截面采不到高出地面的岩石，导致大片白
