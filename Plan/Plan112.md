# Plan112

- **Date**: 2026-09-09
- **Time**: 20:20
- **Project**: noob/Client/Unity
- **Continues**: Plan111.md
- **Session goal**: 修复「工具仍显示 contour-v3」——源码已是 v5 但编译失败，Unity 一直跑旧程序集

## Root cause

`AppendMeshTrianglesReadOnlyData` 对 `Mesh.MeshData.GetVertices` / `GetIndices` 传了托管数组，本机 Unity API 要求 `NativeArray`，导致 CS1503，脚本不编译，窗口仍是上次成功的 contour-v3。

## Fix (contour-v6)

- `using Unity.Collections` + `UnityEngine.Rendering`
- `GetVertices(NativeArray<Vector3>)`
- 按 `indexFormat` 分别用 `NativeArray<ushort>` / `NativeArray<int>` 取索引并 `Dispose`
- 版本号改为 `contour-v6`，便于确认是否已热重载

## Verify

1. Console 无 PrefabOccupancyMapWindow CS1503
2. 关闭再开「Tools/关卡工具/Prefab 占用图生成(_e)」标题为 contour-v6
3. 对 Copy_F_road_03_01 / 03_02 生成，状态里 Mountain/Stone 的 polys>0
