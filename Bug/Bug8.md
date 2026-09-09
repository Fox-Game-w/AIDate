# Bug8

- **Date**: 2026-09-09
- **Time**: 16:07
- **Project**: noob/Client/Unity
- **Related plan**: Plan101.md
- **Status**: fixed

## Summary

Prefab 占用图生成工具输出的白色区域与实际模型占位不符。

## Environment

- OS / shell: Windows / PowerShell
- Branch / commit (if known): local Unity client
- Command or repro steps:
  1. Tools/关卡工具/Prefab 占用图生成(_e)
  2. 选 Prefab 生成 `_e.png`
  3. 对比 PNG 白色区域与模型

## Expected

Y 截面上有模型的区域与占用图对应一致（默认白=模型）。

## Actual

白色区域与实际占用模型不符（薄截面漏检 + 默认黑=占用与需求相反）。

## Root cause

1. 仅用三角面薄板裁剪填充，易漏成「外轮廓/大片空白」。
2. 默认按 RoadConfig（黑=占用），与用户需求（白=模型）相反。
3. 模型不在 Y≈0 时整图空白。

## Fix

- 改为按 16×16 格柱体采样：格心/四角竖线 + 三角与薄板 AABB 相交。
- 默认白=模型、黑=空；勾选「道路约定」才黑=占用。
- 截面无命中时自动落到包围盒底部附近再采一次。
- 半厚度默认提高到 0.1。

## Follow-up

Unity 中重新生成目标 Prefab 的 `_e.png` 做目视确认。
