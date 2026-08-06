# Plan2

- **Date**: 2026-08-06
- **Time**: 18:02 (local)
- **Project**: AIDate / 火焰纹章体系研究
- **Continues**: Plan1.md
- **Session goal**: 产出「火焰纹章 · 道具」底层框架配置表（字段定义 + 示例数据）

## Scope

- In scope:
  - 道具分类、静态表字段、运行时背包实例字段
  - 武器/道具/短杖/饰品统一 Item 模型
  - 与职业（Plan1 武器等级）、战斗公式输入侧对齐
  - 相对路径配置样例：`Data/items.json` 骨架
- Out of scope:
  - 实现完整战斗/商店 UI
  - 原版 ROM 全物品 dump

## Steps

1. 定义 Item 类型枚举与 tags
2. 输出静态配置表字段说明
3. 输出运行时持有物表字段
4. 给 5～8 条示例配置行（刀/枪/斧/弓/理/杖/回复/钥匙 等）
5. 写入仓库文档并 git 同步

## Success criteria

- [x] 用户可直接按表建 SO/JSON/表结构
- [x] 与 FE GBA 术语可对齐（圣魔向）
- [ ] 后续接战斗公式 Plan

## Notes

- 承接 Plan1 职业·武器等级；道具 `weaponType` / `reqWeaponRank` 与 Class 武器适性联动。
