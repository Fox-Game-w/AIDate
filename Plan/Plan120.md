# Plan120

- **Date**: 2026-09-15
- **Time**: 17:33
- **Project**: d:\noob\Client\Unity
- **Continues**: none
- **Session goal**: 梳理 Monster 表 MonsterType 字段被哪些客户端系统关联使用

## Scope

- In scope:
  - Monster_Monster.MonsterType 直接引用
  - 经 RoleHelper.GetUnitType / IsBoss 间接影响的系统
- Out of scope:
  - Proto emMonsterType（击杀上报来源类型，非配表字段）
  - MonsterTypeParam 表（由 MonsterLevBonusId 关联，非 MonsterType）

## Steps

1. 定位枚举与配置注释
2. 搜索 DataTable.MonsterType / RoleDefine.MonsterType 引用
3. 归纳直接关联与 UnitType 下游系统
4. 同步 Plan120

## Success criteria

- [x] 给出 MonsterType 关联系统清单
- [x] 区分直接读表与经 UnitType 间接使用

## Notes

- 枚举：Normal=1 Elite=2 Boss=3 WorldBoss=4 Cannon=10 Trap=11 SceneObject=99
