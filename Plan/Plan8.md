# Plan8

- **Date**: 2026-08-08
- **Time**: 13:41 (local)
- **Project**: home / FE8 职业系统设计咨询
- **Continues**: Plan7.md
- **Session goal**: 梳理复刻《火焰纹章：圣魔之光石》职业系统所需的配置表与模块清单

## Scope

- In scope:
  - FE8 职业/转职/武器等级/职阶能力相关配置表与运行时模块划分
  - 给出可落地的表结构与模块依赖关系
- Out of scope:
  - 具体工程脚手架与数值填表
  - 战斗公式/关卡/支援等非职业核心系统的完整实现

## Steps

1. 加载既有 Plan/Bug 上下文并写入本 Plan
2. 按 FE8 机制拆解：基础职阶、分支转职、见习职、职阶能力、武器限制、移动类型
3. 输出配置表清单 + 模块清单 + 依赖关系
4. 如用户要开工，再确认项目路径并 `move_agent_to_root`

## Success criteria

- [x] 已读取最新 Plan（Plan7）
- [ ] 用户获得可直接开工的配置表与模块清单
- [ ] Plan/Bug 已 commit + push

## Notes

- 承接 Plan7（问候待命）；本会话转为 FE8 职业系统架构答疑
- 开放 Bug：Bug1（中转 API 自定义模型）与本题无关
