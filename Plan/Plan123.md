# Plan123

- **Date**: 2026-09-16
- **Time**: 13:23
- **Project**: d:\noob\Client\Unity / CopyLevel
- **Continues**: Plan122.md
- **Session goal**: 确认 CopyLevel.PreMonsterGroupId 是否支持填写多组 ID

## Scope

- In scope: 字段格式、现表样例、与 PreMonsterGroup / MonsterGroup 关系
- Out of scope: 改表或改编辑器

## Steps

1. 查 CopyLevel 字段注释与现有填法
2. 对照 PreMonsterGroup 表结构
3. 查客户端是否解析该字段

## Success criteria

- [x] 明确能否填多组及格式含义

## Notes

- 格式同 CopyObjectGroupId：进度,Id,Id|进度,Id
- 现表样例已有多 ID；HotFix 未见运行时引用
