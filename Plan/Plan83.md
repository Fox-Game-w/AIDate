# Plan83

- **Date**: 2026-09-03
- **Time**: 15:42
- **Project**: Tools/TowerFloorEditor (from TowerFloor.xlsx)
- **Continues**: none
- **Session goal**: 制作 TowerFloor 分页签编辑 exe：按 TowerType 分组、自动填行、合并导出

## Scope

- In scope:
  - 导入 TowerFloor.xlsx（第1类型行、第2格式行、第3备注行、第4起数据）
  - 按 TowerType 建页签；同页签共享指定列；自动 TowerFloorId/NextFloorId/TowerFloorNum
  - 可设行数增删；可加新页签；导出合并为一张表
- Out of scope:
  - 改游戏客户端逻辑；改原表公式语义以外的业务校验

## Steps

1. 解析 xlsx 结构与 TowerType 实际值
2. 用 Python + tkinter/openpyxl 实现 GUI 工具
3. 打包为 exe（PyInstaller）
4. 验证导入/调行数/导出

## Success criteria

- [x] 可导入现有 TowerFloor.xlsx 并按 TowerType 分页签
- [x] 调整行数时自动维护 Id/Next/Num 与共享列
- [x] 可新增页签并导出合并表
- [x] 产出可运行的 exe

## Notes

- 共享列：FightType, ElementTag, SpecialRewardShow, MonsterNum, CopyPlotArray, MapSize, ExportNavmesh, LimitTime, MonsterIdArr, WasteReward, CommonReward, EliteReward, BossReward, LimitMonIdReward, GoalType, CopyObjectList, SkillList
- NextFloorId = 本行 TowerFloorId+1；页签末行 NextFloorId 为空
- 产出路径：`d:\noob_excel\Tools\TowerFloorEditor\dist\TowerFloorEditor.exe`
