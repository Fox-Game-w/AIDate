# Plan105

- **Date**: 2026-09-09
- **Time**: 19:01
- **Project**: noob/Client/Unity
- **Continues**: Plan104.md
- **Session goal**: 严格按与基座 Mesh 接触面填黑（contact-v3）

## Scope

- In scope: 仅近路面 + 近似水平三角，按实际轮廓填格
- Out of scope: 运行时

## Steps

1. 剔除侧墙整模投影
2. 仅保留贴地接触三角
3. 必须落在基座 Mesh 投影内才涂黑

## Success criteria

- [x] 工具版本标记 contact-v3
- [ ] 用户重导后黑区为接触轮廓而非大方块

## Notes

- 旧 _e.png 仍是俯视版，必须重新生成
- 窗口标题含 contact-v3
