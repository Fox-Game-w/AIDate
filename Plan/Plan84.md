# Plan84

- **Date**: 2026-09-04
- **Time**: 09:33
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan83.md
- **Session goal**: 导入改为可自由选择任意 xlsx，并重新打包 exe

## Scope

- In scope:
  - 去掉写死默认路径自动加载
  - 启动/导入均可自由选文件
  - 重新生成 TowerFloorEditor.exe
- Out of scope:
  - 其它编辑逻辑改动

## Steps

1. 改导入 UI：自由选文件 + 记住上次目录
2. 重新 PyInstaller 打包
3. 同步 Plan

## Success criteria

- [ ] 启动不强制加载固定路径
- [ ] 可通过对话框任选 xlsx 导入
- [ ] 新 exe 已生成

## Notes

- 路径：d:\noob_excel\Tools\TowerFloorEditor\
