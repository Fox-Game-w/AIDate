# Plan1

- **Date**: 2026-08-06
- **Time**: 17:40 (local)
- **Project**: AIDate / 火焰纹章体系研究
- **Session goal**: 定义并落地「火焰纹章 · 职业」底层框架（数据模型 + 规则接口 + 扩展点）

## Scope

- In scope:
  - 职业（Class / Job）核心数据模型
  - 能力值、成长、武器适性、移动/地形、晋升关系
  - 与单位（Unit）实例的挂接方式（base class + 运行时成长）
  - 规则计算入口：命中/必杀/伤害等所需的「职业侧」输入
  - 可配置数据格式（ScriptableObject / JSON / CSV 任选一种默认）
  - 预留 FE8《圣魔之光石》职业表对齐点
- Out of scope（本 Plan 不实现）:
  - 完整战场 / 地图 / AI
  - 完整剧情与支援系统 UI
  - 直接嵌入任天堂原版 ROM 素材与商业资源
  - 全游戏章节内容

## Steps

1. **定术语与边界**
   - Class：职业模板（静态配置）
   - Unit：单位实例（等级、当前属性、持有职业）
   - Promotion：晋升链 / 转职条件
   - 明确与「角色身份（Character）」分离：同一角色可升迁换职

2. **设计职业静态表字段（底层核心）**
   - 标识：`classId`、显示名、是否飞行/骑兵等 tag
   - 基础能力：HP/Str/Mag/Skl/Spd/Lck/Def/Res/Con/Mov（按 FE GBA 习惯）
   - 能力上限（caps）
   - 成长率（class growth，可选叠加）
   - 武器等级上限 / 武器适性等级（Sword~Dark 等）
   - 移动类型与地形代价引用
   - 战斗动画 id / 地图行走图 id（仅引用，不绑死资源）
   - 晋升：`promotesTo[]`、最低等级、所需道具（如英雄之证）

3. **设计运行时接口**
   - `IClassData`：只读配置访问
   - `IUnitStats`：当前属性读写
   - `ClassResolver`：由 unit → 当前职业配置
   - `PromotionService`：检查可否晋升 / 执行晋升（属性重置或 FE 式保留）
   - `StatFormulas` 输入侧：职业提供 base、caps、bonus（职技/状态等后续扩展）

4. **选型落地载体**
   - 优先：若在 Unity 工程 → ScriptableObject（`ClassDefinition`）+ 可选 JSON 导入
   - 无 Unity 时：纯 C# 数据类 + JSON 表，放在引擎无关的 `Core/` 层
   - 参考工程（继续改用）：`GBAFireEmblemInUnity` / `Fire-Emblem-Unity` / `EmblemForge`；逻辑对照：`fireemblem8u`

5. **最小可验证原型**
   - 录入 3～5 个示例职业（如领主、剑士、修女、战士、龙骑士简化版）
   - 单位挂职后正确读出：移动力、武器可持、能力上限
   - 单测或编辑器调试窗口：打印单位战斗用中间值（攻击、命中预览依赖的属性）

6. **文档与后续 Plan 衔接**
   - 在本 Plan 完成后列出缺口 → 下一份 Plan（战斗公式 / 道具 / 地图移动）
   - Bug 产出写入 `Bug/BugN.md`，不阻塞框架骨架提交

## Success criteria

- [ ] 有清晰的职业数据模型（字段表 + 代码类型定义）
- [ ] Unit 与 Class 解耦：换职不重建整个角色对象
- [ ] 晋升链可配置、可校验
- [ ] 至少 3 个示例职业 + 1 条读档/加载路径可用
- [ ] `Plan/` `Bug/` 经 git 推送到 AIDate 远程
- [ ] 不依赖非法分发的 ROM 二进制作为运行时资源

## Notes

- 命名建议代码侧用英文：`ClassDefinition`、`UnitRecord`、`PromotionRule`；文档可中英对照。
- FE8 对照优先级：职业表 → 晋升 → 移动类型 → 武器等级；动画与 UI 置后。
- 个人日志仓库：https://github.com/Fox-Game-w/AIDate.git（本地 `~/AIDate`）。
- 本 Plan 只定「职业底层框架」；具体实现若选 Unity 工程，需 `move_agent_to_root` 进项目后再写代码。

## Suggested module sketch

```
Core/
  Class/
    ClassId.cs
    ClassDefinition.cs      // 静态数据
    ClassTags.cs            // Flying, Mounted, Armor...
    WeaponRank.cs
    PromotionRule.cs
  Unit/
    UnitRecord.cs           // 实例：level, exp, stats, classId
    StatBlock.cs
  Services/
    ClassDatabase.cs        // 加载/查询
    PromotionService.cs
    StatCalculator.cs       // 预留，战斗 Plan 再填
Data/
  classes.json              // 或 SO 资源
```
