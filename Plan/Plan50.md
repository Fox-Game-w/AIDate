# Plan50

- **Date**: 2026-08-18
- **Time**: 11:33 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan49.md
- **Session goal**: 计算打满一关进度需要走过多少地形块

## Scope

- In scope: 从现有配置/代码推算关卡灵魂进度 vs 区块
- Out of scope: 改生成逻辑

## Steps

1. 确认进度口径（SoulAmount）与区块尺寸
2. 估算每块刷怪组/只数与灵魂
3. 给出每关所需地形块

## Success criteria

- [x] 给出可复核的计算公式与每关块数

## Notes

- 地形块 16m；进度=SoulAmount；假设 1 杀 1 魂、每走过的块清 1 组
- 关1 约 23 块；之后约 SoulAmount/4 块
