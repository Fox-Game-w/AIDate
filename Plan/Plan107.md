# Plan107

- **Date**: 2026-09-09
- **Time**: 19:19
- **Project**: noob/Client/Unity
- **Continues**: Plan106.md
- **Session goal**: 黑区仅 Scene_/ExploreCopy04 与基座接触面

## Scope

- In scope: 按名称前缀过滤 + 基座接触面填黑
- Out of scope: Copy_* 等其它子物体

## Steps

1. 只收集 Scene_ / ExploreCopy04 开头物体三角
2. 筛贴近 Copy_01_road_01_01 的接触三角
3. 在基座画布上按实际投影填黑

## Success criteria

- [x] 工具 scene-contact-v1
- [ ] 用户重导验证接近 03_02_e 风格且仅山石类

## Notes

- 匹配自身/父级/Mesh 名；接触距离默认 0.35
