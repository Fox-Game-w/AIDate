# Plan118

- **Date**: 2026-09-11
- **Time**: 13:06
- **Project**: D:\Tools\CopyLevelEditor
- **Continues**: Plan117
- **Session goal**: 优化导出卡死

## Cause

openpyxl 导出时整表逐格写回 + 新行拷样式，约 1000×32 格极慢。

## Fix

- 脏行集合：只写改过的行
- 行数不变时不做 delete_rows / 样式拷贝
- 导出进度回调；必要时仅更新关键列
