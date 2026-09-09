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
2. 修正截面采样（高度/翻转/填充）使占位贴合模型
3. 写 Bug 记录并同步 Plan

## Success criteria

- [ ] 生成图中占用区域与 Y=0 截面模型轮廓一致
- [ ] 颜色约定与工具说明一致且可对照样例

## Notes

- 用户原文：白=模型、黑=空；RoadConfig：黑=占用、白=空
- 疑点：Y=0 薄截面漏检、Z 翻转、默认颜色与预期相反
