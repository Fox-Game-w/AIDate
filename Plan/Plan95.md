# Plan95

- **Date**: 2026-09-08
- **Time**: 10:10
- **Project**: Tools/CopyObjectGroupEditor
- **Continues**: none
- **Session goal**: 制作 CopyObject/CopyObjectGroup 编辑 exe：可选导入、编辑群组、写回保留格式

## Scope

- In scope:
  - 可选文件导入两张表（第1名/第2类型/第3备注/第4起数据）
  - CopyObject ObjectId+备注 对照
  - 编辑 CopyObjectGroup：Type 下拉、CopyObjectRate 用 | 拼 ID、条件字段逗号分隔
  - 导出基于原表保留格式
- Out of scope:
  - 改游戏客户端

## Steps

1. 解析两表结构
2. 实现 GUI + 逻辑
3. PyInstaller 打包 exe

## Success criteria

- [x] 可选导入两表
- [x] 可编辑 Group 并维护 CopyObjectRate
- [x] 导出保留原格式
- [x] 产出 exe

## Notes

- Type 1-15 按用户列表
- 参考 TowerFloorEditor 的导入导出模式
- 产出：d:\noob_excel\Tools\CopyObjectGroupEditor\CopyObjectGroupEditor.exe
