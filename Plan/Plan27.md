# Plan27

- **Date**: 2026-08-12
- **Time**: 18:17 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: none
- **Session goal**: 汇总秘境（SpDungeon）工程进度并回复现状

## Scope

- In scope:
  - 从 git 提交、配表、客户端代码引用梳理秘境进度
  - 区分旧资源塔「幽能秘境」与新 SpDungeon 体系
- Out of scope:
  - 不实现功能、不改代码

## Steps

1. 核对 CN_1.7_0 相关秘境提交与是否合入 main
2. 检查 SpDungeon / RoomGroup 是否有玩法、UI、协议接入
3. 输出进度结论与缺口清单
4. commit + push Plan27

## Success criteria

- [x] 用户拿到可决策的秘境工程进度结论
- [ ] Plan/Plan27.md 已提交并推送

## Notes

- 新秘境 = SpDungeon + SecretAreaGameModule（LevelType.SecretArea=9）
- 旧「幽能秘境」= ResourceTowerType.Secret + UIResourceYNMJ，勿混
- origin/main 已到 `cd51a62aa9 完善秘境关卡`；本地 HEAD 落后约 42 commit，无 SecretArea 源文件
