# Bug9

- **Date**: 2026-09-09
- **Time**: 17:06
- **Project**: noob/Client/Unity
- **Related plan**: Plan102.md
- **Status**: fixed

## Summary

`Copy_F_road_06_04` 导出的 `_e.png` 黑色区域与岩石占位不符；红圈内岩石区域应全为黑色。

## Environment

- Prefab: Assets/Bundles/Level/Maps/MainCopy/Scene_Forest/road/Terrain_Fire/Copy_F_road_06_04.prefab
- 现 `_e.png`: 16x16，约 33 黑像素（左边/底边），其余全白

## Expected

俯视下四堆岩石覆盖区域在占用图中为实心黑色（RoadConfig：黑=占用）。

## Actual

几乎全白，黑色不成岩石形状。

## Root cause

Y=0 薄截面采不到高于地面的岩石体积；且曾默认白=模型，与道路约定相反。

## Fix

- 默认模式改为「俯视占位」（XZ 投影/柱体命中任意三角）
- 默认黑=占用、白=空
- 默认排除大面积扁平地面 Mesh，只保留岩石等立体物

## Follow-up

Unity 中对该 Prefab 重新点「生成占用图」验证红圈区域是否实心黑。
