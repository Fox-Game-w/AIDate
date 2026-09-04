# Plan89

- **Date**: 2026-09-04
- **Time**: 13:55
- **Project**: Tools/TowerFloorEditor
- **Continues**: Plan88.md
- **Session goal**: 导出/更新时基于原表保留格式，只改数据行单元格值

## Scope

- In scope:
  - 以源 xlsx 为底板导出
  - 不改第1-3行与样式；仅写数据区内容
  - 行数增减时复制/清理数据行样式
- Out of scope:
  - 重做导入解析

## Steps

1. 重写 export：load 源表 → 只更新数据行 value
2. 验证样式/公式保留
3. 重打包 exe

## Success criteria

- [ ] 导出后表头样式、列宽、字体等仍在
- [ ] 仅数据内容更新
- [ ] 新 exe 已生成

## Notes

- 无源文件时仍可新建空表兜底
