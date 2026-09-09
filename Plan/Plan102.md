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

1. 分析 prefab / 现 `_e.png`（约 33 黑，边框状）
2. 改为俯视剪影 + 排除扁平地面；默认黑=占用
3. 更新 Bug 并同步

## Success criteria

- [x] 默认俯视占位，黑=占用、白=空
- [x] 可排除扁平地面，保留岩石立体占位
- [ ] 需在 Unity 对 Copy_F_road_06_04 重新生成验证

## Notes

- 入口：Tools/关卡工具/Prefab 占用图生成(_e)
- 该 Prefab 含地面+岩石；Y=0 薄截面采不到岩石体积
