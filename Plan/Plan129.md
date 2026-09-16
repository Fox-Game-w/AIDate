# Plan129

- **Date**: 2026-09-16
- **Time**: 19:48
- **Project**: d:\Tools\CopyLevelEditor
- **Continues**: Plan128.md
- **Session goal**: 优化 CopyLevelEditor 导出卡顿

## Scope

- In scope: structure_dirty 全表写回改 write_only；脏行增量写优化；避免无谓全表 dirty
- Out of scope: UI 大改

## Steps

1. 定位导出瓶颈
2. write_only 全量导出 + 增量路径提速
3. 重打包 exe

## Success criteria

- [x] 批量生成后导出明显更快

## Result

- 全表 write_only：约 3666 行 ~1.5s
- 增量脏行：~0.6s
- exe 已更新
