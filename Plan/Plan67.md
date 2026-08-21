# Plan67

- **Date**: 2026-08-21
- **Time**: 11:11 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan66.md
- **Session goal**: 制作交互物刷新密度参数导出 exe（ObjectId + 三段多段串）

## Scope

- In scope: Python GUI + Excel 导出 + PyInstaller 打包 exe 到 Doc
- Out of scope: 改游戏配置、接入运行时

## Steps

1. 写 tkinter 工具（分段编辑 → 生成串 → 导出 xlsx）
2. PyInstaller 打 exe
3. git sync Plan

## Success criteria

- [x] Doc 下有可用 exe：`Doc/ChestSpawnExporter.exe`
- [x] 源码：`Doc/Tools/ChestSpawnExporter/chest_spawn_exporter.py`
- [x] 导出格式与单行多段表结构一致
