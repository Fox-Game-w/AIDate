# Bug8

- **Date**: 2026-09-09
- **Time**: 16:07
- **Project**: noob/Client/Unity
- **Related plan**: Plan101.md
- **Status**: open

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

Y=0 截面上有模型的区域与占用图对应一致。

## Actual

白色区域与实际占用模型不符。

## Root cause

调查中：可能为 Y=0 薄截面漏检、纹理 Z 轴方向、或默认黑白与用户预期相反。

## Fix

待定。

## Follow-up

对照现有手绘 `_e.png` 与生成算法后修正。
