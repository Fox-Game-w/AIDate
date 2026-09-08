# Plan97

- **Date**: 2026-09-08
- **Time**: 11:02
- **Project**: Tools/CopyObjectGroupEditor
- **Continues**: Plan96.md
- **Session goal**: Times/Range/Number 按组编辑；Times与Number用逗号、Range用|；Range为最小最大

## Scope

- In scope: 条件组表格编辑与序列化；群组可插行；重打包
- Out of scope: 改 CopyObject 逻辑

## Steps

1. 实现条件组解析/序列化
2. 细编辑区改为组表格
3. 重打包 exe

## Success criteria

- [x] 条件按组编辑，三组数量一致
- [x] Times `,` / Range `|` 且 min,max / Number `,`
- [x] 新 exe 已生成

## Notes

- 例：Times=30,50 Range=1,1|5,8 Number=7,7
