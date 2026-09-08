# Plan94

- **Date**: 2026-09-08
- **Time**: 09:40
- **Project**: noob/Client/Unity
- **Continues**: none
- **Session goal**: 解释 CS0122 CreateGitProcess 不可访问报错

## Scope

- In scope: 说明 protection level 原因
- Out of scope: 除非用户要求再改代码

## Steps

1. 对照 GameDataChangeWindow 与 GitForUnityUtils
2. 回复含义与改法建议

## Success criteria

- [x] 用户理解 CS0122 原因

## Notes

- CreateGitProcess 为 private，且签名只有 (string args)
