# Plan117

- **Date**: 2026-09-11
- **Time**: 12:28
- **Project**: D:\Tools\CopyLevelEditor
- **Continues**: Plan116
- **Session goal**: 优化 CopyLevelEditor 卡顿/卡死

## Likely causes

- UI 线程同步 load_workbook 两遍
- 切关卡时全量 refresh_level_list + 反复 serialize
- 进度段刷新时对每个群组查 map + 重绘 listbox
- 导出时整表写回

## Plan

1. 导入改后台线程 + 进度提示
2. 减少不必要全量刷新；节流/脏标记
3. 列表虚拟化或延迟渲染 Type 汇总
4. 重新打包 exe
