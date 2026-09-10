# Bug11

- **Date**: 2026-09-10
- **Related**: Plan113
- **Symptom**: 输出分辨率选 256，生成的 `_e.png` 仍是 16×16

## Cause

- 工具曾长期卡在未编译成功的旧程序集；默认 `outputSize`/`MapSize` 为 16，写出 PNG 即为 16。
- `Copy_F_road_03_01_e.png` / `03_02_e.png` 磁盘实测 16×16。

## Fix

contour-v7：默认 256；写图与 TextureImporter.maxTextureSize 使用同一 `outputSize`。
