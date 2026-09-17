# Plan133

- **Date**: 2026-09-17
- **Time**: 17:20
- **Project**: d:\Tools\MainMonsterGroupGenerator
- **Continues**: Plan132
- **Session goal**: 完成主线怪物组生成器验证与 exe 打包

## Scope

- In scope: dry-run 全量生成、当量校验、PyInstaller 打包、样本输出确认
- Out of scope: 写入游戏服正式 MonsterGroup 表

## Steps

1. [x] 对默认 Monster/Copy 路径执行 generate_all（3662 关全成功）
2. [x] 校验每组当量 = 16（2×类型2）
3. [x] PyInstaller onefile 产出 MainMonsterGroupGenerator.exe
4. [x] 样本输出格式：`关卡ID|怪物ID，数|…`（中文逗号）

## Success criteria

- [x] `d:\Tools\MainMonsterGroupGenerator\MainMonsterGroupGenerator.exe` 已生成
- [x] 试跑 130 Copy / 3662 Level，fail=0，unknown_remarks=[]
- [x] 样例输出见 `output_monster_groups.txt` / `.xlsx`

## Notes

- 优先组成为 2 只 MonsterType=2；池不足时用 1/6/5 补足
- 地形：草地/沙漠/雪地/熔岩/沼泽 ← Copy 备注第4列
