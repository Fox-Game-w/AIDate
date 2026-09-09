# Bug9

- **Date**: 2026-09-09
- **Time**: 17:06
- **Project**: noob/Client/Unity
- **Related plan**: Plan102.md
- **Status**: open

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

Y=0 薄截面采不到高于地面的岩石体积，只碰到地面边缘等碎片。

## Fix

待改为 XZ 柱体命中任意网格（俯视占位）并默认黑=占用。

## Follow-up

重新生成该 prefab 的 `_e.png` 验证。
