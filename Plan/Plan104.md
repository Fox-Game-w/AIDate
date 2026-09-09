# Plan104

- **Date**: 2026-09-09
- **Time**: 18:55
- **Project**: noob/Client/Unity
- **Continues**: Plan103.md
- **Session goal**: 占用改为道路接触面实际轮廓，去掉整模方块

## Scope

- In scope: PrefabOccupancyMapWindow 仅按与 Copy_01_road_01_01 接触薄层填黑
- Out of scope: 运行时

## Steps

1. 去掉 TopDown 整模柱体
2. 每格多样点：先采路面高度，再判断道具表面是否落在接触带
3. 同步 Plan

## Success criteria

- [x] 默认只画接触面，非整模/非 AABB 方块
- [ ] 用户重导 Copy_F_road_03_02 等验证轮廓

## Notes

- 接触向上默认 0.25，可调；采样默认 3x3/格
