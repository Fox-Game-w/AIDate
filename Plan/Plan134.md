# Plan134

- **Date**: 2026-09-17
- **Time**: 17:25
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: Plan133
- **Session goal**: 怪物组改为随机组合，仅约束当量=16，不再固定全用类型2

## Steps

1. 重写 build_group_for_attr：枚举/随机合法类型组合
2. 校验全量当量与组合多样性
3. 重新打包 exe

## Success criteria

- [x] 纯 2×类型2 约占 2.9%，其余为随机合法组合
- [x] 3662 关当量均为 16；exe 已重新打包（dist / v2）
