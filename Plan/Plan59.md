# Plan59

- **Date**: 2026-08-19
- **Time**: 18:18 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan58.md
- **Session goal**: 设计 Copy_Copy 拆分为「章节表 + 关卡表」，关卡挂带权重的怪物组与交互物组

## Scope

- In scope: 表职责切分、字段草案、与现网 PreMonsterGroup / CopyObjectGroup 关系、示例映射
- Out of scope: 改代码、改正式 JSON、全量数据迁移

## Steps

1. 对齐现网：Copy 进度切池 + PreMonsterGroupRate / CopyObjectRate
2. 出章节表 / 关卡表字段与权重串格式
3. 写 Excel 方案 + 示例行；git sync Plan

## Success criteria

- [x] 两表职责清晰：CopyId=章节，等级区间=关卡
- [x] 关卡行可配怪物组权重、交互物组权重
- [x] Excel: `Doc/Copy拆分_章节关卡表方案.xlsx`（别名 `Copy_Chapter_Level_Split.xlsx`）

## Notes

- 现网权重已在 PreMonsterGroup / CopyObjectGroup 叶子表；拆表后关卡层再挂「组级权重」
- 章节表建议名 `CopyChapter` / 关卡表 `CopyLevel`；叶子表 MonsterGroup、CopyObjectGroup 保留
