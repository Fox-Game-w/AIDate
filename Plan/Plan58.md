# Plan58

- **Date**: 2026-08-19
- **Time**: 13:20 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan54.md
- **Session goal**: 完成 Copy 表梳理：关卡链路、字段分组、进度对照，并导出 Excel

## Scope

- In scope: 读 Copy_Copy 定义与 JSON，整理结构与现网关卡一览
- Out of scope: 改表、改代码

## Steps

1. 按职责分组字段
2. 抽出全部关卡链路与 SoulAmount / CopyProgress 等关键值
3. 输出 Excel（关卡一览 / 字段分组 / 进度对照 / 串格式 / 空字段）

## Success criteria

- [x] 给出 Copy 表结构分组与关卡一览
- [x] Excel: `Doc/Copy表梳理.xlsx`

## Notes

- 承接 Plan54（上次 PowerShell 内嵌 Python 失败，未写出 Excel）
- 23 关线性链 6000001–6000023，累计 SoulAmount=149500
- 现网进度远大于规划 v4（规划累计约 90000）
