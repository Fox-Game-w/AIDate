# Plan140

- **Date**: 2026-09-17
- **Time**: 20:20
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: Plan139.md
- **Session goal**: MonsterGroupId 生成前缀扩展一位（Level 右4→右5）

## Scope

- In scope: `make_group_id`、文案/README、重打包 exe
- Out of scope: PreMonsterGroup 规则（仍按前5位，随新 ID 自然变化）

## Steps

1. 改 make_group_id：6 + Level右5位 + 序号
2. 更新 tip / README
3. 抽样校验并打包

## Success criteria

- [x] 组ID形如 6XXXXX{1~4}（7位），例 Level 600000101 → 6001011~4
- [x] exe 已更新

## Notes

- 原：6 + 右4 + 序号 → 601011
- 现：6 + 右5 + 序号 → 6001011
