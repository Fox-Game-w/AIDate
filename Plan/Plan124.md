# Plan124

- **Date**: 2026-09-16
- **Time**: 15:57
- **Project**: d:\Tools\CopyLevelEditor
- **Continues**: Plan122.md
- **Session goal**: 为 CopyLevelEditor 增加秘境专用批量生成（按 ChapterID + 关卡数量）

## Scope

- In scope:
  - 秘境 LevelID：9 + 关卡编号4位 + Level3位 + 层数1位
  - 模板 900010011/12/13（层1/2/3）
  - 填 ChapterID + 关卡数量，每关自动出 3 层
  - 主线批量对话框去掉错误的秘境规则
- Out of scope:
  - 改 Excel 数据本身

## Steps

1. 实现秘境 ID 构造与对话框
2. 接入工具栏并修正主线批量仅主线
3. 更新 README、重打包 exe
4. 同步 Plan124

## Success criteria

- [x] 输入 ChapterID 与关卡数量可生成 每关×3层
- [x] Next/Chapter/Level/LevelType 符合现表
- [x] exe 可见「秘境批量生成」按钮

## Notes

- 例：ChapterID=9000001 → 编号0001；关卡数2 → 900010011~013、900010021~023
- 层3 Next 为空，不跨关卡链接
- 主线按钮改名为「主线批量生成」，秘境独立入口

## Result

- SecretBatchGenerateDialog + on_batch_generate_secret_levels
- 已重打包 CopyLevelEditor.exe
