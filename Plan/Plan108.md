# Plan108

- **Date**: 2026-09-09
- **Time**: 19:31
- **Project**: noob/Client/Unity
- **Continues**: Plan107.md
- **Session goal**: 接触面按模型实际轮廓填黑，不用方块划定

## Scope

- In scope: 接触三角按路面薄板裁剪后投影填格
- Out of scope: 改运行时 16 图尺寸约定

## Steps

1. Scene_/ExploreCopy04 三角与路面接触带求交裁剪
2. 仅用裁剪多边形 XZ 填格（点在多边形内）
3. 提高格内采样，按覆盖比例判定，避免整格方块膨胀

## Success criteria

- [x] 改为接触薄板裁剪多边形 + 覆盖比例填格 (contour-v2)

## Notes

- 仍输出 16x16；轮廓精度受像素格限制

