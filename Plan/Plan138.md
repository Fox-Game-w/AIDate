# Plan138

- **Date**: 2026-09-17
- **Time**: 19:46
- **Project**: d:\noob_excel\Config\ExcelData
- **Continues**: none
- **Session goal**: 按 MonsterGroupId 前5位分组，写入 PreMonsterGroup.xlsx

## Scope

- In scope:
  - 读取 MonsterGroup.xlsx 唯一 MonsterGroupId
  - 前5位相同归组，生成 PreMonsterGroupId / PreMonsterGroupRate
  - 按 PreMonsterGroup 表格式追加或填充数据
- Out of scope:
  - 改客户端代码、导表工具其它表

## Steps

1. 确认两表格式与 Rate 写法（id,1000|id,1000）
2. 统计前5位分组
3. 写入 PreMonsterGroup.xlsx
4. 抽样校验并同步 Plan

## Success criteria

- [x] 已生成分组数据（1122 组，Rate 权重均为 1000）
- [ ] 覆盖写入原 PreMonsterGroup.xlsx（当前被 Excel 占用）

## Notes

- Rate 格式按现表：`MonsterGroupId,1000|MonsterGroupId,1000`
- 已保留原 134 行，追加 1122 行到 `PreMonsterGroup_filled.xlsx`
- 原文件 Permission denied，需关闭 Excel 后覆盖
