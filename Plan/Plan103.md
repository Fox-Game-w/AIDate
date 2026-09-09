# Plan103

- **Date**: 2026-09-09
- **Time**: 17:47
- **Project**: noob/Client/Unity
- **Continues**: Plan102.md
- **Session goal**: 占用图画布以 Copy_01_road_01_01 Mesh 为 16×16，超出不展示

## Scope

- In scope: PrefabOccupancyMapWindow 边界改为道路基座 Mesh
- Out of scope: 改运行时道路逻辑

## Steps

1. 按 Mesh/物体名匹配 Copy_01_road_01_01 取 XZ 包围盒
2. 仅在该范围内栅格化，超出模型不入图
3. 同步 Plan

## Success criteria

- [ ] 画布=道路基座 Mesh 大小
- [ ] 超出部分不出现在 `_e.png`

## Notes

- 例：Copy_F_road_03_02 内含 Copy_01_road_01_01
