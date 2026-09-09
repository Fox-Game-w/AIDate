# Plan100

- **Date**: 2026-09-09
- **Time**: 15:05
- **Project**: noob/Client/Unity
- **Continues**: Plan99.md
- **Session goal**: 占用图改为按 Y=0 截面判定模型占用

## Scope

- In scope: PrefabOccupancyMapWindow 用 Y=0 截面栅格化
- Out of scope: 改运行时道路逻辑

## Steps

1. 去掉俯视整模渲染
2. Mesh 与 Y=0 薄截面求交并栅格到 16x16
3. 同步 Plan

## Success criteria

- [x] 占用依据 Y=0 截面
- [x] 仍输出 prefab名_e.png

## Notes

- 边界仍为主体 Prefab XZ 包围盒
- 可调「截面半厚度」；默认 0.05
- 入口：Tools/关卡工具/Prefab 占用图生成(_e)
