# Plan142

- **Date**: 2026-09-17
- **Time**: 21:01
- **Project**: d:\noob\Client\Unity
- **Continues**: none
- **Session goal**: 诊断 RequestEnterCopy 回调 NullReferenceException

## Scope

- In scope: GameProtoHelper.cs:58 与回调链路
- Out of scope: 改协议/网络框架（除非确认需修）

## Steps

1. 读 RequestEnterCopy 回调
2. 判断可能为 null 的对象
3. 给出原因与排查建议

## Success criteria

- [x] 说明 NRE 触发点与常见原因

## Notes

- RemoveUnansweredMessage 超时回调 (999, null)
- RequestEnterCopy 未处理超时/空包，直接访问 msg.Explore
