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

已确认（2026-08-17 14:13）：本机 **没有任何进程 LISTEN 在 8080/6500**；`uv`/`uvx` 不在 PATH；Cursor MCP catalog 为空。插件默认连 `ws://127.0.0.1:8080/hub/plugin`，对端未启动 → `Unable to connect to the remote server`。

## Fix / workaround

1. `Window > MCP for Unity` → **Auto-Setup**（会提示装 Python/`uv`、写 Cursor 配置）
2. 点 **Start Local HTTP Server** / 确认 Server Status 为 Installed + 可连
3. **Unity Bridge** 设为 Running
4. 窗口里 HTTP URL 应对齐：`http://127.0.0.1:8080`（WebSocket 会变为 `ws://127.0.0.1:8080/hub/plugin`）
5. 若缺 `uv`：先装 [uv](https://github.com/astral-sh/uv)，再 Auto-Setup
6. 开启 Show Debug Logs 核对实际候选地址

## Prevention

使用前先开 Bridge / Auto-Setup；不要在服务未起时依赖 MCP 工具。
