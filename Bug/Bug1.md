# Bug1

- **Date**: 2026-08-06
- **Time**: 20:22 (local)
- **Project**: Cursor 配置 / 中转 API
- **Related plan**: Plan3.md
- **Status**: open

## Summary

中转站场景下无法在 Cursor Models 中添加名为 `gpt-5.6` 的自定义模型（Add Custom Model 无效或仍走 Cursor 官方路由）。

## Environment

- OS / shell: Windows 10
- Cursor Models + Override OpenAI Base URL（第三方中转）
- 目标模型名：`gpt-5.6` / `gpt5.6`

## Expected

可把中转提供的 `gpt-5.6` 加为自定义模型，请求走 Base URL + 自带 Key。

## Actual

与 Cursor 内置模型 `GPT-5.6` 重名时，自定义添加不生效；请求仍可能走 Cursor 自带路由而非 BYOK/中转。

## Error output

```
（用户描述：无法添加 gpt5.6；论坛同类：Add Custom Model 不创建条目）
```

## Suspected cause

自定义模型 ID 与 Cursor 内置目录冲突；Refresh Model List 也不会拉取中转 `/v1/models`。

## Fix / next action

- [ ] 使用不与内置重名的别名添加，例如 `gpt-5.6-relay`
- [ ] 在中转控制台把该别名映射到真实 `gpt-5.6`（若中转要求请求体 model 必须是官方 id）
- [ ] 聊天模型选择器选别名模型，勿选 Cursor 自带 GPT-5.6
- [ ] 网络异常时试 HTTP Compatibility Mode → HTTP/1.1
