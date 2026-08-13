# Bug3

- **Date**: 2026-08-13
- **Time**: 12:29 (local)
- **Project**: AIDate 会话日志同步
- **Related plan**: Plan28.md
- **Status**: fixed

## Summary

改用 PowerShell 调用 Git Bash 后，嵌套引号导致提交消息未正确传给 `git commit -m`；文件已经暂存，但没有产生提交或推送。

## Environment

- OS / shell: Windows 10 / PowerShell 5 调用 Git for Windows Bash
- Branch / commit: AIDate main
- Command or repro steps: 从 PowerShell 传入包含 Bash heredoc 与多层引号的 `bash -lc` 字符串

## Expected

通过 Git Bash 的 heredoc 生成提交消息并完成提交。

## Actual

Git 报告终端不可交互且未设置 EDITOR，说明 `-m` 最终未获得有效消息；Plan28 与 Bug2 停留在暂存区。

## Error output

```
error: Terminal is dumb, but EDITOR unset
Please supply the message using either -m or -F option.
```

## Suspected cause

PowerShell、Bash 和命令包装层的三层引号共同改写了 `$(cat <<EOF ...)`，使提交消息参数丢失。

## Fix / next action

- [x] 保留已暂存文件，不使用 amend 或清理暂存区
- [x] 使用 PowerShell here-string 直接构造多行提交消息
- [x] 将 Bug3 一并暂存后创建新提交并推送
