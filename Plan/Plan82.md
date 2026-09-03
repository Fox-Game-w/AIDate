# Plan82

- **Date**: 2026-09-03
- **Time**: 11:36
- **Project**: noob/Client/Unity
- **Continues**: Plan81.md
- **Session goal**: 确认场景中 NPC、StartPos 由何种编辑器工具生成

## Scope

- In scope:
  - 查找 NPC / StartPos 的编辑器生成入口与工具名
- Out of scope:
  - 修改关卡编辑器或配置

## Steps

1. 搜索 StartPos / NPC 相关 Editor 代码
2. 确认工具菜单与生成逻辑
3. 写入 Plan 并 git 同步后回复用户

## Success criteria

- [ ] 明确工具名称与入口
- [ ] Plan/Plan82.md 已提交并 push

## Notes

- 候选：Assets/Editor/LevelEditor/LevelEditor/LevelEditorWindow.cs
