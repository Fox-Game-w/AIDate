# Plan90

- **Date**: 2026-09-04
- **Time**: 15:06
- **Project**: noob/Client/Unity
- **Continues**: Plan82.md
- **Session goal**: 确认 Unity 关卡编辑器关卡列表的数据来源

## Scope

- In scope: 查找 LevelEditor 关卡列表填充逻辑与配置来源
- Out of scope: 修改编辑器代码

## Steps

1. 阅读 ShowLevelList / allLevels / LoadLevelConfig
2. 确认各玩法对应配置表
3. 回复来源并同步 Plan

## Success criteria

- [ ] 明确关卡列表从何处读取
- [ ] Plan 已提交

## Notes

- 入口：Assets/Editor/LevelEditor/LevelEditor/LevelEditorWindow.cs
