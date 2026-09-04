# Plan86

- **Date**: 2026-09-04
- **Time**: 09:47
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan85.md
- **Session goal**: 导入时保持原表数据/公式不改写，仅主动操作或调行数时再规范化

## Scope

- In scope:
  - 导入不调用 normalize；尽量保留原单元格公式
  - 导出不自动按首行改写共享列
  - sync 网格不强制 normalize
- Out of scope:
  - 完整复制 Excel 样式主题

## Steps

1. 改 load / sync_from_grid / export / on_export
2. 重打包 exe
3. 记 Plan

## Success criteria

- [ ] 导入后共享列、Id 链与源表一致（含公式）
- [ ] 仅「同步/重算/改行数」才改写规则字段
- [ ] 新 exe 已生成

## Notes

- d:\noob_excel\Tools\TowerFloorEditor\
