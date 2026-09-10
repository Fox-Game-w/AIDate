# Plan115

- **Date**: 2026-09-10
- **Time**: 11:13
- **Project**: noob/Client/Unity
- **Continues**: Plan114.md
- **Session goal**: 取消压缩到 16×16，按生成分辨率直接输出 PNG

## Changes

- 移除 `DownsampleOccupied` / `FinalMapSize` 输出路径
- 保存与预览使用 `outputSize`（默认 256）
- 版本 bump `contour-v9`
