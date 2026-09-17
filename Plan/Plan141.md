# Plan141

- **Date**: 2026-09-17
- **Time**: 20:24
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: Plan140.md
- **Session goal**: PreMonsterGroupId 按 MonsterGroupId 前6位分组

## Scope

- In scope: PRE_GROUP_PREFIX_LEN、文案/README、重打包
- Out of scope: MonsterGroupId 生成规则

## Steps

1. 前缀长度 5→6
2. 更新 UI/README
3. 试跑并打包

## Success criteria

- [x] PreMonsterGroupId = 前6位；Rate 仍为 id,1000|…
- [x] exe 已更新

## Notes

- 例：6001011~6001014 → PreMonsterGroupId=600101
