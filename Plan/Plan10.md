# Plan10

- **Date**: 2026-08-08
- **Time**: 14:45 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: Plan9.md
- **Session goal**: 拆解 Hotfix 世界 / 关卡系统的目录、职责、运行时流程与关键类

## Scope

- In scope:
  - `Assets/Hotfix/Game/` 及关卡相关 Manager / UI / Model 依赖
  - Level、Territory、Task、FeatureUnlock、Farm、Dialogue 等子模块关系
- Out of scope:
  - 战斗 GamePlay 内部技能/Buff 细节
  - 修改工程代码

## Steps

1. 列出 Game/ 与 Level 相关目录结构
2. 读关键 Manager / 入口与流程
3. 按子模块归纳职责与依赖
4. 回复用户；commit + push Plan10

## Success criteria

- [x] 用户获得世界/关卡分层拆解说明
- [x] Plan/Plan10.md 已推送

## Notes

- 承接 Plan9 中「世界 / 关卡」条目的深化
- 双场景：Territory（主城/领地）vs Level（战斗关卡）；关卡运行时核心在 StageManager + LevelLogic，不完全在 Game/Level
