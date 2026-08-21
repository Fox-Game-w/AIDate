# Plan65

- **Date**: 2026-08-21
- **Time**: 10:50 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan63.md
- **Session goal**: 设计「按已获宝箱数分段控制刷新间距」的可配置表结构

## Scope

- In scope: 表字段、枚举、示例行、与 CopyObject/关卡关联建议
- Out of scope: 改正式 JSON、写运行时逻辑

## Steps

1. 归纳分段规则为可配置区间
2. 给出主流表结构 + 示例 Excel 到 Doc（可选）
3. git sync Plan

## Success criteria

- [x] 表结构能表达：获取数量区间、格子间距区间、停止条件
- [x] Excel: `Doc/宝箱刷新密度表结构.xlsx` / `ChestSpawnDensity_Schema.xlsx`

