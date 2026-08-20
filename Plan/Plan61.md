# Plan61

- **Date**: 2026-08-20
- **Time**: 11:47 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan60.md
- **Session goal**: 说明 CallMonsterGroup 字段/表的关联关系

## Scope

- In scope: 查字段定义、引用表、代码用法
- Out of scope: 改配置

## Steps

1. 搜索 CallMonsterGroup
2. 确认关联到哪张表/ID
3. 回复并 git sync Plan

## Success criteria

- [x] 说清归属表、指向表、调用时机

## Notes

- CallMonsterGroup 不是独立表，是 CopyObject_Reward 字段
- 关联 MonsterGroup_MonsterGroup.MonsterGroupId
- 现网多用于 Type=4 大裂隙类交互物

