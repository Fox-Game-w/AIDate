# Plan39

- **Date**: 2026-08-17
- **Time**: 14:07 (local)
- **Project**: d:\noob\Client\Unity
- **Continues**: none (new track)
- **Session goal**: 解释 Unity Console 中 MCP-FOR-UNITY WebSocket 连接失败含义与排查方向

## Scope

- In scope: 错误含义说明；对照官方 README / 插件源码的常见原因
- Out of scope: 改游戏业务代码；代为完成完整 MCP 安装调试（除非用户继续要求）

## Steps

1. 解读堆栈与 `Unable to connect to the remote server`
2. 对照 MCP for Unity 窗口 / Bridge / 本地服务启动步骤给出排查清单
3. 写入 Plan（及必要时 Bug）并 git sync

## Success criteria

- [x] 用户能理解这是「连不上 MCP 服务端/桥接」，不是业务脚本崩溃
- [x] 知道 Window > MCP for Unity 里该检查什么

## Notes

- 详情见 Bug7.md（环境连接类问题）
