# Bug12

- **Date**: 2026-09-16
- **Time**: 20:25
- **Project**: d:\noob\Client\Unity
- **Related plan**: Plan130.md
- **Status**: open

## Summary

主线大地图刷怪时报 `创建怪物失败`。日志未打印 monsterId，无法从这条 Error 本身看出是缺表还是缺资源。

## Environment

- OS / shell: Windows / Unity
- Branch / commit (if known):
- Command or repro steps: 主线 InfinitePerlinTerrain 生成 chunk → ChangeActiveArea → AddMonsterArea → Spawn

## Expected

刷怪成功，或失败时打印 monsterId / 配置缺失原因。

## Actual

`RoleHelper.CreateMonsterAsync` 在 `AddMonsterToBattle` 返回 null 时只打 `Log.Error("创建怪物失败")`。

## Error output

```
创建怪物失败
RoleHelper.CreateMonsterAsync
MonsterAreaGizmo.Spawn
LevelObjectLogic.AddMonsterArea
```

## Suspected cause

服务端下发的 CopyMonsterGroup.MonsterIds 中某个怪物配置 ID：Monster 表不存在、MonsterType 无法映射 UnitType，或模型预制路径为空/加载失败。

## Fix / next action

- [ ] 对照同一时刻 Console 是否有「预制资源不存在」或 GetData 缺表日志
- [ ] 在 CreateMonsterAsync 失败日志中补上 monsterId / area / group
