# Plan112

- **Date**: 2026-09-09
- **Time**: 20:20
- **Project**: noob/Client/Unity
- **Continues**: Plan111.md
- **Session goal**: 修复「工具仍显示 contour-v3」——源码已是 v5 但编译失败，Unity 一直跑旧程序集

## Root cause

`AppendMeshTrianglesReadOnlyData` 对 `Mesh.MeshData.GetVertices` / `GetIndices` 传了托管数组，本机 Unity API 要求 `NativeArray`，导致 CS1503，脚本不编译，窗口仍是上次成功的 contour-v3。

## Fix (contour-v6)

- 去掉 `Mesh.AcquireReadOnlyMeshData` / NativeArray（本机会 CS1503，编译失败→一直跑旧 contour-v3）
- `isReadable=false` 时用 `ModelImporter.isReadable=true` + `SaveAndReimport` 再读三角
- 版本号 `contour-v6`；若 Unity 未自动 Refresh，需手动 Ctrl+R

## Verify

1. 切到 Unity → Assets/Refresh（或 Ctrl+R），Console 无 PrefabOccupancyMapWindow CS1503
2. 关闭再开工具窗口，标题为 contour-v6（不是 v3）
3. 对 Copy_F_road_03_01 / 03_02 生成，Mountain/Stone 有黑区
