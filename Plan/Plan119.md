# Plan119

- **Date**: 2026-09-12
- **Time**: 14:20
- **Project**: D:\Tools\MainCopyMapViewer
- **Continues**: Plan118.md
- **Session goal**: 制作 exe 解析 mainCopy JSON，绘制 9x9 地图（怪/交）

## Scope

- In scope:
  - 解析 copyArea 中 monsterIds / objectId
  - 9x9 格，中心 (0,0)，同格可同时显示怪+交
  - 打包 exe
- Out of scope:
  - buffObject 无坐标不画进格子

## Steps

1. 按 CopyLevelEditor 风格用 Python+tkinter 做工具
2. 解析并绘制地图
3. PyInstaller 打包 exe
4. 同步 Plan119

## Success criteria

- [ ] exe 可粘贴/加载 JSON 并画出怪/交
- [ ] 同格可同时标记怪和交

## Notes

- copyArea key 为 \"x:y\"
- CopyGroupTypeMonster -> monsterIds
- CopyGroupTypeComponent -> component.objectId
