# Plan132

- **Date**: 2026-09-17
- **Time**: 16:42
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: none
- **Session goal**: 按 Copy 备注地形 + Monster 规则生成主线关卡怪物组，并打包 exe

## Scope

- In scope:
  - MonsterId 6010001–6053005
  - 左第3位属性；MonsterType 2/1/6/5 折算
  - 每组标准=2只类型2当量；按 Copy 备注匹配
  - 输出 关卡ID|怪ID,数|…
  - tkinter + PyInstaller exe
- Out of scope: 写入游戏服正式 MonsterGroup 表

## Steps

1. 解析 Copy 备注与 Monster 池
2. 实现折算与组生成
3. UI + 导出 + 打 exe

## Success criteria

- [x] exe 可读两表并导出结果（见 Plan133 收尾）
