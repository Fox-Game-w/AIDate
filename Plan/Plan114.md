# Plan114

- **Date**: 2026-09-10
- **Time**: 09:51
- **Project**: noob/Client/Unity
- **Continues**: Plan113.md
- **Session goal**: 高分辨率生成后压缩为 16×16 输出

## Approach

1. 仍用「输出分辨率」做精细栅格（默认 256）
2. 生成后块压缩到固定 `FinalMapSize=16`（块内任一黑格→黑，避免丢占用）
3. 保存 PNG / 预览 / importer 均为 16×16；状态注明 生成分辨率→16
