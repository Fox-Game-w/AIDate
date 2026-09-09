# Plan109

- **Date**: 2026-09-09
- **Time**: 19:44
- **Project**: noob/Client/Unity
- **Continues**: Plan108.md
- **Session goal**: 修复 Scene_Magma_stone02_fbx 未涂黑（Y=-0.79 埋入）

## Root cause

stone02 LocalPosition.y = -0.79，旧接触带几乎只采路面上方，埋入模型与路面相交被裁掉。

## Fix

- 接触带改为路面上下双向 ±thickness
- 重心不在路面三角时，XZ 与道路 AABB 相交则用道路中心 Y
- contour-v3，默认厚度 0.5

## Success criteria

- [x] 代码已修
- [ ] 用户重导 03_02 可见 stone02 接触黑区
