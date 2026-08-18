# Plan53

- **Date**: 2026-08-18
- **Time**: 17:21 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan52.md
- **Session goal**: 按 120 分钟 60 宝箱投放节奏，换算每多少格投放一个宝箱

## Scope

- In scope: 时段拆分 + 格子间隔 + Excel
- Out of scope: 改关卡配置

## Steps

1. 拆时段：0–20 / 20–40 / 40–60 / 60–120
2. 用 100 进度≈48 格、约 3 分钟满进度 换算走格速度
3. 导出 Excel 并 git sync

## Success criteria

- [x] 给出各时段「每 N 格一个宝箱」

## Notes

- 产出：`Doc/宝箱投放_格子间隔.xlsx`
- 有效走格 16 格/分钟（100进度≈48格≈3分钟）
- 0–20: 约 11 格/箱；20–40 与 40–60: 32 格/箱；60–120: 96 格/箱
