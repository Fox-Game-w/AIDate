# Plan111

- **Date**: 2026-09-09
- **Time**: 20:09
- **Project**: noob/Client/Unity
- **Continues**: Plan110.md
- **Session goal**: 修复 Copy_F_road_03_01 多个山石未涂黑

## Root cause

Mountain01_fbx_2 Y=-1.9、Mountain02_1 Y=-1.46 等深埋，全局路面中心±1.5 接触带盖不住。

## Fix (contour-v5)

- 每模型按自身最低点向上取底部接触带，并与路面带并集
- 默认底部厚度 3
- 裁剪失败时回退三角 XZ 投影

## Objects

- ExploreCopy04_Mountain01_fbx_2 (Y=-1.9)
- Scene_Magma_stone01_05 (Y=-0.46)
- Scene_Magma_Mountain03_1 / Mountain02_1
