# Plan116

- **Date**: 2026-09-10
- **Time**: 18:10
- **Project**: noob/Client/Unity
- **Continues**: none
- **Session goal**: 查清击杀怪物涨魂由哪个配置表控制

## Scope

- In scope:
  - 定位主线/关卡魂进度相关配置与击杀结算链路
- Out of scope:
  - 修改配置或逻辑

## Steps

1. 搜索魂/Soul/KillMonster 相关配置与代码
2. 确认 Copy / CopyLevel / Monster 等表字段职责
3. 回答用户并同步 Plan 日志

## Success criteria

- [x] 明确涨魂相关表与字段
- [x] 说明客户端无单怪涨魂字段、数值由服务端结算返回

## Notes

- 魂对应 WellkonwItem.SOUL_ID=3（空间石碑）
- Copy_Copy.SoulAmount：关卡灵魂总量
- CopyLevel_CopyLevel.LevelSoul：单个关卡/子阶段魂数量
