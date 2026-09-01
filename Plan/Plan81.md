# Plan81

- **Date**: 2026-09-01
- **Time**: 17:43
- **Project**: noob/Client/Unity
- **Continues**: none
- **Session goal**: 定位「黄金矿坑」配置表路径并回复用户

## Scope

- In scope:
  - 在 Unity 工程中查找黄金矿坑相关配置表
  - 记录主表与关联系统/功能解锁配置
- Out of scope:
  - 修改配置或玩法逻辑

## Steps

1. 搜索「黄金矿坑」及 ResourceTower / GoldPit 相关配置与代码
2. 确认主配置表与 TowerId / SystemId
3. 写入 Plan 并 git 同步
4. 向用户给出路径结论

## Success criteria

- [x] 找到黄金配置表路径
- [ ] Plan/Plan81.md 已提交并 push

## Notes

- 主表：`Assets/Bundles/Config/ResourceTower_ResourceTower.json`，TowerId=2 / TowerType=2
- 系统表：`System_System.json` SystemId=1135；功能解锁 FeatureId.GoldPit=1135
