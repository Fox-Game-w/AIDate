# Plan87

- **Date**: 2026-09-04
- **Time**: 09:54
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan86.md
- **Session goal**: 修复 header_height='auto' 导致 int() 报错

## Scope

- In scope: 将表头高度改为数值并重打包 exe
- Out of scope: 其它功能

## Steps

1. 改 header_height 为整数
2. 重打包 exe

## Success criteria

- [x] 不再出现 invalid literal for int() ... 'auto'
- [x] 新 exe 可用

## Notes

- 原因：当前 tksheet 不接受 header_height='auto'
