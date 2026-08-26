# Plan76

- **Date**: 2026-08-26
- **Time**: 14:55
- **Project**: noob/Client/Unity
- **Continues**: Plan75.md
- **Session goal**: 将异形格子+点击旋转规则与宝箱取物文档导出为 Word

## Scope

- In scope:
  - 确认/完善两份 Markdown 设计稿
  - 导出两份 docx（Doc/ + d:\）
  - Git sync Plan76
- Out of scope:
  - 程序实现异形背包 / UIMainChestLoot

## Steps

1. [x] 撰写异形格子 + 点击旋转规则 md
2. [x] 撰写宝箱取物 md
3. [x] 用导出脚本生成两份 docx 到 Doc/ 与 d:\
4. [x] Git sync Plan76（本地 commit 成功；push 因 github.com:443 连通失败，待重试）

## Success criteria

- [x] 形状表、旋转规则、放置判定、操作说明齐全
- [x] 宝箱取物含箱内格、拖取、一键拿取、与异形背包联动
- [x] 两份 `.docx` 已输出并可打开

## Notes

- MD 源：`Doc/主线搜打撤异形格子与旋转规则.md`、`Doc/主线搜打撤宝箱取物设计文档.md`
- 导出脚本：`Doc/Tools/export_alien_grid_rotate_doc.py`、`Doc/Tools/export_chest_loot_doc.py`
- Word 输出：
  - `Doc/主线搜打撤异形格子与旋转规则.docx` / `d:\主线搜打撤异形格子与旋转规则.docx`
  - `Doc/主线搜打撤宝箱取物设计文档.docx` / `d:\主线搜打撤宝箱取物设计文档.docx`
