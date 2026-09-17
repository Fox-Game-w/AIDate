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

- [ ] PreMonsterGroup 含各组 PreMonsterGroupId
- [ ] Rate 为组内唯一 MonsterGroupId 且权重 1000

## Notes

- 用户描述：PreMonsterGroupId=前5位；Rate=组内 MonsterGroupId，各 1000
- 现有 Rate 格式样例：`id,weight|id,weight`
