# Plan88

- **Date**: 2026-09-04
- **Time**: 10:00
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan87.md
- **Session goal**: 新增「地块拼接」页签编辑 CopyPlotArray，拼完后写回对应 TowerType 全部行

## Scope

- In scope:
  - 解析/序列化：`,` 分列，`|` 分行
  - 独立页签：增删行列、从页签加载、应用到全部行
- Out of scope:
  - 改其它共享列逻辑

## Steps

1. 实现 parse/serialize 与地块拼接 UI
2. 应用到指定 TowerType 全部 CopyPlotArray
3. 重打包 exe

## Success criteria

- [ ] 可可视化编辑地块网格
- [ ] 可增删行/列
- [ ] 可写回对应页签全部行
- [ ] 新 exe 已生成

## Notes

- CopyPlotArray 例：`66101,66101,66101|66101,10000001,66101|66101,66101,66101`
