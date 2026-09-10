# Plan113

- **Date**: 2026-09-10
- **Time**: 09:44
- **Project**: noob/Client/Unity
- **Continues**: Plan112.md
- **Session goal**: 输出分辨率默认/实际 256；预览放在状态上方

## Problem

- 滑条可设 256，但磁盘 `_e.png` 仍是 16×16（旧 contour-v3 或默认 outputSize=16）
- 预览在状态下方，不便对照

## Changes (contour-v7)

1. 默认 `outputSize = 256`
2. 生成/写 PNG/importer `maxTextureSize` 均跟 `outputSize`
3. OnGUI：预览移到「状态」上方，点采样放大显示
4. 状态文案带上实际像素 `WxH`
