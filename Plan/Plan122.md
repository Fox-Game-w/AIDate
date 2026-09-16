# Plan122

- **Date**: 2026-09-16
- **Time**: 09:40
- **Project**: d:\Tools\CopyLevelEditor
- **Continues**: none
- **Session goal**: 为 CopyLevelEditor 增加按章节数/每章关卡数批量生成主线关卡数据

## Scope

- In scope:
  - LevelID 规则：首位类型(6主线/9秘境)+章节6位+关卡2位
  - NextLevelID / ChapterID / LevelType 自动填充
  - 主线以 600000101 为模板，接在已有主线数据后插入
  - UI 输入最终章节数与每章关卡数
- Out of scope:
  - 秘境批量生成（规则可预留，本次主做主线）
  - CopyObjectGroup 批量新建

## Steps

1. 读取现有 CopyLevel 主线数据确认 ID/插入位置
2. 实现批量生成逻辑与对话框
3. 接入工具栏与 README
4. 同步 Plan122

## Success criteria

- [ ] 输入章节数与每章关卡数可生成/补齐主线关卡
- [ ] NextLevelID、ChapterID、LevelType 符合规则
- [ ] 从模板复制其它字段，插入主线段末尾

## Notes

- LevelID 例：600000101 = 类型6 + 章节000001 + 关卡01
- ChapterID = NextLevelID 前7位（用户说明）
- 当前约到 41 章
