# Plan71 — ChestSpawnExporter 主键改 CopyObjectGroupId

Date: 2026-08-21

## Goal
交互物刷新密度表/工具主键由 ObjectId 替换为 CopyObjectGroupId。

## Steps
1. 更新 exporter：表头识别与 UI 文案改为 CopyObjectGroupId（兼容旧 ObjectId 表头）。
2. 更新样例表 `ChestSpawnDensity_Schema_v3.xlsx` 与 README。
3. 重建 `Doc/ChestSpawnExporter.exe`。

## Status
- Done
