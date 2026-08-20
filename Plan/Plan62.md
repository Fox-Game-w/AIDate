# Plan62

- **Date**: 2026-08-20
- **Time**: 14:42 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan61.md
- **Session goal**: 说明掉落物品相关配置表

## Scope

- In scope: 定位掉落/Reward 相关表与 Copy 侧挂接点
- Out of scope: 改表、改数值

## Steps

1. 搜 Drop / Reward / 掉落 配置与引用
2. 归纳表职责与关联
3. 回复；git sync Plan

## Success criteria

- [x] 说清掉落物品主表及 Copy 侧关联字段

## Notes

- 主表：Reward_Reward（RewardId → ItemId,Num,Rate）
- 道具本体：Item_Item
- Copy 侧：DropEquip* / *Reward / Limit*Reward / FreeReward / BossRewardShow
- CopyObject.FinishPrize 等也挂 Reward 或道具

