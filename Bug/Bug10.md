# Bug10

- **Date**: 2026-09-09
- **Related**: Plan111 / Plan112
- **Symptom**: 占用图工具标题与日志一直是 `[contour-v3]`，即使用户要的是 v5 接触轮廓逻辑

## Cause

`PrefabOccupancyMapWindow.cs` 中 `AppendMeshTrianglesReadOnlyData` 编译失败：

- CS1503 L656: `Vector3[]` → 需要 `NativeArray<Vector3>`
- CS1503 L668: `int[]` → 需要 `NativeArray<ushort>`

编译不过时 Unity 保留上一版已编译的 Editor 程序集，故界面仍显示 v3。

## Fix

contour-v6：改用 NativeArray 读写 MeshData，版本号 bump 便于确认加载成功。
