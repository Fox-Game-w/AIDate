# Bug7

- **Date**: 2026-08-17
- **Time**: 14:07 (local)
- **Project**: d:\noob\Client\Unity
- **Related plan**: Plan39.md
- **Status**: open

## Summary

Unity Editor 中 MCP for Unity 通过 WebSocket 连接 MCP 服务端失败：`Unable to connect to the remote server`。属环境/服务未启动或 URL 错误，非游戏业务逻辑异常。

## Environment

- OS / shell: Windows 10 / PowerShell
- Branch / commit (if known): n/a（Editor 插件 `Packages/com.coplaydev.unity-mcp`）
- Command or repro steps:
  1. Unity 打开带 MCP for Unity 的工程
  2. 插件尝试建立 WebSocket 连接
  3. Console 报 `MCP-FOR-UNITY: [WebSocket] Connection failed...`

## Expected

WebSocket 连上本地或配置的 MCP hub/bridge，工具可注册并通信。

## Actual

`EstablishConnectionAsync` 对候选 URI 全部 `ConnectAsync` 失败，最终 Detail: `Unable to connect to the remote server`。

## Root cause

（待确认）最可能：本机 MCP HTTP/Bridge 进程未运行、端口不对、或 Server URL 配错；次可能：防火墙/API Key。

## Fix / workaround

1. `Window > MCP for Unity` → Auto-Setup
2. 确认 Unity Bridge 为 Running；必要时 Start Bridge
3. 确认本地 HTTP Server / `uvx` MCP 服务已启动（默认 MCP 端口常见为 6500）
4. 核对 WebSocket/Server URL；远程模式再查 API Key
5. 开启 Show Debug Logs 看具体候选地址

## Prevention

使用前先开 Bridge / Auto-Setup；不要在服务未起时依赖 MCP 工具。
