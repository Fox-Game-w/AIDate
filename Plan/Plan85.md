# Plan85

- **Date**: 2026-09-04
- **Time**: 09:42
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan84.md
- **Session goal**: 表头显示第3行备注，并重新打包 exe

## Scope

- In scope:
  - UI 表头 = 字段名 + 备注
  - 导出仍保持原表结构（第1字段名 / 第2类型 / 第3备注）
- Out of scope:
  - 改共享列或行数逻辑

## Steps

1. 增加 display_headers（字段名+备注）
2. Sheet 使用 display_headers
3. 重打包 exe

## Success criteria

- [x] 页签表头可见中文备注
- [x] 导出结构不变
- [x] 新 exe 已生成

## Notes

- 路径：d:\noob_excel\Tools\TowerFloorEditor\
- Plan 本地已 commit；push 网络失败需稍后重试
