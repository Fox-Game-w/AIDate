# Plan139

- **Date**: 2026-09-17
- **Time**: 19:50
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: Plan138.md
- **Session goal**: 将 PreMonsterGroup 前5位分组生成功能加入 MainMonsterGroupGenerator

## Scope

- In scope:
  - 读 MonsterGroup.xlsx，按 MonsterGroupId 前5位分组
  - 写入/追加 PreMonsterGroup.xlsx（Rate: id,1000|…）
  - UI 按钮 + 可选路径；必要时重打包 exe
- Out of scope:
  - 改导表工具其它逻辑

## Steps

1. 阅读现有 generator UI/导入逻辑
2. 实现 generate_pre_monster_group 并挂按钮
3. 试跑校验；更新 README；同步 Plan

## Success criteria

- [x] UI 可一键根据 MonsterGroup 生成 PreMonsterGroup
- [x] 保留已有 PreMonsterGroupId：已存在则更新 Rate，否则追加；支持 ID 段过滤
- [x] exe 已重新打包

## Notes

- PreMonsterGroupId = 前5位；权重固定 1000
- 按钮：「同步 PreMonsterGroup」
- 试跑：当前 MonsterGroup 524 唯一 ID → 41 组
