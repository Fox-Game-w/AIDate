# Plan121

- **Date**: 2026-09-15
- **Time**: 17:35
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan120.md
- **Session goal**: 说明 RoleDefine.UnitType 与 RoleDefine.MonsterType 的关联方式

## Scope

- In scope:
  - 枚举定义对照
  - RoleHelper.GetUnitType 映射入口与调用点
- Out of scope:
  - Proto emMonsterType
  - 改代码

## Steps

1. 对照 RoleDefine 中两枚举
2. 确认 GetUnitType 映射表
3. 说明 AddMonsterToBattle 等使用路径
4. 回答用户并同步 Plan121

## Success criteria

- [x] 给出 MonsterType → UnitType 映射表
- [x] 标明唯一转换入口 GetUnitType

## Notes

- 数值不完全相等：WorldBoss 与 Boss 都映射到 UnitType.Boss；Trap 同为 11 属巧合
