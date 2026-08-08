# Plan5

- **Date**: 2026-08-07
- **Time**: 13:05 (local)
- **Project**: d:\序列帧（序列帧打包工具）
- **Continues**: none
- **Session goal**: 实现将多张图片打包为 Unity 可播放序列帧动画的工具

## Scope

- In scope:
  - 多图（每张1帧）打包为 spritesheet / 图集
  - 导出 Unity 可导入的动画资源（meta / clip / AnimationClip JSON 或 TexturePacker 兼容数据）
  - CLI 或简单脚本入口，可预览帧序与 FPS
- Out of scope:
  - 完整 Unity 编辑器插件 UI（可选后续）
  - 视频编解码、骨骼动画

## Steps

1. 加载既有 Plan 上下文与工作区 packer 代码
2. 完善 spritesheet 装箱与 unity 导出
3. 提供 CLI 入口与 README 用法
4. 验证导出路劲与格式
5. git add Plan/ → commit → push

## Success criteria

- [ ] 用户可用一键命令将图序列导出为 Unity 可播动画相关文件
- [ ] 写出 Plan5.md 并 push

## Notes

- 工作区已有 packer/spritesheet.py、unity_export.py
- 本机 Node 可用；Python 可能需安装 Pillow
