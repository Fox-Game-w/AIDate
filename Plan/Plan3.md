# Plan3

- **Date**: 2026-08-06
- **Time**: 20:19 (local)
- **Project**: Cursor 配置 / home workspace
- **Continues**: none
- **Session goal**: 排查中转场景下无法添加 gpt-5.6 自定义模型

## Scope

- In scope:
  - 中转 + Override Base URL
  - 与 Cursor 内置模型名冲突（gpt-5.6）
  - 别名添加与网关侧映射
- Out of scope:
  - 代填真实 API Key
  - 修改 Cursor 内部源码

## Steps

1. 确认用户为中转 + 想加 gpt-5.6 — done
2. 说明内置名冲突：须用唯一别名（如 gpt-5.6-relay）
3. 说明网关需认别名或做映射
4. 写 Bug 记录；git 同步（shell 可用时）

## Success criteria

- [x] 定位根因：与 Cursor 内置 GPT-5.6 重名
- [ ] 用户用别名成功 Add Custom Model 并聊天可用
- [ ] Plan/Bug git push（shell 恢复后）

## Notes

- Forum: https://forum.cursor.com/t/cursor-cannot-connect-to-the-third-party-relay-station/164487
- Shell sandbox 不可用时 push 延后。
