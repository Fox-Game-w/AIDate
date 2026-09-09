# Plan110

- **Date**: 2026-09-09
- **Time**: 19:54
- **Project**: noob/Client/Unity
- **Continues**: Plan109.md
- **Session goal**: 修复 Mountain01 / stone02 仍未涂黑

## Root cause

1. ExploreCopy04_Mountain01_fbx isReadable=0，顶点读不到
2. 两个物体 Y 埋入路面（-0.3 / -1.28 / -0.79），且可能落在路面三角外，旧逻辑跳过

## Fix (contour-v4)

- AcquireReadOnlyMeshData 读取不可读 Mesh
- 接触带用道路中心 Y ± 厚度（默认 1.5）
- 画布用道路 AABB，不再要求点必须在路面三角内
- 状态输出每个匹配物体的 meshTris/contactPolys

## Success criteria

- [x] 代码已改
- [ ] 重导后状态里 Mountain01/stone02 的 contactPolys>0 且图上有黑
