# Plan125

- **Date**: 2026-09-16
- **Time**: 17:06
- **Project**: d:\Tools\CopyLevelEditor
- **Continues**: Plan124.md
- **Session goal**: 秘境批量生成：层3清空 Next；新行紧接对应章节；同步修正已有行

## Scope

- In scope: 秘境插入位置、Next 链、已有行修正、重打包
- Out of scope: 主线插入策略大改

## Steps

1. 层3 Next 清空 + 网格同步修正
2. `_insert_secret_rows_for_chapter` 紧接章节块
3. 重打包 exe

## Success criteria

- [x] LevelID 结尾为 3 的 Next 为空
- [x] 新数据紧接对应 Chapter
- [x] 目标网格已有行一并修正

## Result

- apply_secret_row_links / _insert_secret_rows_for_chapter
- exe 已重打包
