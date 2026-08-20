# Plan63

- **Date**: 2026-08-20
- **Time**: 15:11 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan62.md
- **Session goal**: 按主流掉落表格式，把 Copy 掉落迁出为独立掉落表；关卡表+掉落表另存 Doc，不改原配置

## Scope

- In scope: 从 Copy_Copy.json 抽取关卡与掉落，导出 Excel 到 Doc/
- Out of scope: 改 Assets 配置、改运行时代码

## Steps

1. 定关卡表 / 掉落表字段（对齐章节-关卡拆分 + 主流 DropGroup/DropEntry）
2. 从现网 Copy 生成样例数据 Excel
3. git sync Plan

## Success criteria

- [x] Doc 下有关卡表、掉落表（可打开核对）
- [x] 原 Copy json 未改动

## Notes

- `Doc/Copy关卡表.xlsx` / `CopyLevel_Export.xlsx`
- `Doc/Copy掉落表.xlsx` / `CopyDrop_Export.xlsx`（DropGroup + DropEntry）
- 关卡 1495 行；掉落组 23；掉落条目约 2.5 万（Limit*Reward 展开）

