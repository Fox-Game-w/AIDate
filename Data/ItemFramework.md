# 火焰纹章 · 道具底层框架配置表

面向 FE GBA（圣魔之光石向）可扩展设计。  
**静态配置** = 道具模板；**运行时** = 单位背包中的一件实例（耐久、掉落标记等）。

---

## 1. 类型与枚举

### 1.1 `itemKind`（大类）

| 值 | 含义 | 说明 |
|----|------|------|
| `weapon` | 武器 | 进入战斗；耗耐久（除无限耐久） |
| `staff` | 杖 | 辅助/治疗/状态；通常走杖命中与经验规则 |
| `consumable` | 消耗品 | 回复药、状态药、促进剂等 |
| `equipment` | 装备/饰品 | 常驻效果（如能力 +、特技） |
| `key` | 钥匙 | 开门/宝箱/章节道具 |
| `treasure` | 贵重品 | 卖金、剧情交换、无法使用 |
| `dragonstone` | 龙石等变身类 | 特殊武器轨；可单独 kind |
| `other` | 其它 | 扩展兜底 |

### 1.2 `weaponType`（仅武器/杖子集）

| 值 | 中文 | 对应职业武器栏 |
|----|------|----------------|
| `sword` | 剑 | Sword |
| `lance` | 枪 | Lance |
| `axe` | 斧 | Axe |
| `bow` | 弓 | Bow |
| `magicAnima` | 理魔法 | Anima |
| `magicLight` | 光魔法 | Light |
| `magicDark` | 暗魔法 | Dark |
| `staff` | 杖 | Staff |
| `monster` | 魔物专用 | 可选 |
| `none` | 无 | 非武器 |

### 1.3 `weaponRank`（使用需求）

| 值 | 等级 | 数值建议（内部比较用） |
|----|------|------------------------|
| `E` | E | 1 |
| `D` | D | 2 |
| `C` | C | 3 |
| `B` | B | 4 |
| `A` | A | 5 |
| `S` | S | 6 |
| `none` | 无要求 | 0 |

单位当前武器等级 ≥ `reqWeaponRank` 才可装备/使用。

### 1.4 `itemTags`（可多选，字符串数组）

| tag | 含义 |
|-----|------|
| `brave` | 二连击 |
| `devil` | 修罗系自伤风险 |
| `reverseWeaponTriangle` | 武器相克逆转 |
| `magicWeapon` | 物理武器按魔攻结算（部分游戏设定） |
| `effectiveArmor` | 对铠有效 |
| `effectiveCavalry` | 对骑有效 |
| `effectiveFlying` | 对飞有效（弓默认常带） |
| `effectiveDragon` | 对龙有效 |
| `effectiveMonster` | 对魔物有效 |
| `unsellable` | 不可卖 |
| `unbreakable` | 无限耐久 |
| `indestructible` | 不可破坏且常不耗（剧情） |
| `lockedToCharacter` | 角色专用（看 `lockCharacterIds`） |
| `lockedToClass` | 职业限定（看 `lockClassIds`） |
| `healing` | 回复类 |
| `statBoost` | 永久/战斗中属性提升 |
| `statusInflict` | 施加状态 |
| `statusCure` | 解除状态 |
| `warp` | 传送等战场特殊 |

### 1.5 `useTarget`（使用对象）

| 值 | 含义 |
|----|------|
| `none` | 不可主动使用（纯装备/贵重） |
| `self` | 仅自身 |
| `ally` | 友军 |
| `enemy` | 敌军 |
| `anyUnit` | 任意单位 |
| `tile` | 格子/门/宝箱 |

---

## 2. 静态配置表 · 字段定义（ItemDefinition）

一行 = 一种道具模板。建议表名：`items` / 文件：`Data/items.json`。

| 字段 | 类型 | 必填 | 默认 | 说明 |
|------|------|------|------|------|
| `itemId` | string | 是 | — | 稳定 ID，如 `iron_sword` |
| `displayName` | string | 是 | — | 显示名 |
| `description` | string | 否 | `""` | 图鉴说明 |
| `itemKind` | enum | 是 | — | 见 1.1 |
| `weaponType` | enum | 条件 | `none` | 武器/杖必填 |
| `reqWeaponRank` | enum | 条件 | `none` | 需求武器等级 |
| `might` | int | 否 | `0` | 威力 Mt（武器/攻击杖） |
| `hit` | int | 否 | `0` | 命中 Hit |
| `crit` | int | 否 | `0` | 必杀 Crit |
| `weight` | int | 否 | `0` | 重量 Wt（影响攻速） |
| `minRange` | int | 否 | `1` | 最小射程 |
| `maxRange` | int | 否 | `1` | 最大射程 |
| `usesMax` | int | 否 | `0` | 最大耐久/使用次数；`0`+`unbreakable` = 无限 |
| `priceBuy` | int | 否 | `0` | 买入价；`0` 常表示非卖品 |
| `priceSell` | int | 否 | 自动 | 默认可 `priceBuy/2` |
| `expOnUse` | int | 否 | `0` | 使用/击破额外经验（杖等） |
| `wexpOnHit` | int | 否 | `1` | 命中时武器经验（武器） |
| `healHp` | int | 否 | `0` | 回复 HP 固定值 |
| `healHpPercent` | int | 否 | `0` | 按最大 HP 百分比回复 |
| `statBonus` | object | 否 | `{}` | 装备常驻：`{str,skl,spd,lck,def,res,mov,con,...}` |
| `growthBonus` | object | 否 | `{}` | 成长加成（稀有道具） |
| `statusOnHit` | string | 否 | `null` | 命中施加状态 id |
| `statusDuration` | int | 否 | `0` | 状态持续（回合） |
| `effectId` | string | 否 | `null` | 复杂效果脚本/表引用（传送、全域等） |
| `tags` | string[] | 否 | `[]` | 见 1.4 |
| `useTarget` | enum | 否 | 见 kind | 见 1.5 |
| `lockCharacterIds` | string[] | 否 | `[]` | 专用角色 |
| `lockClassIds` | string[] | 否 | `[]` | 限定职业 |
| `iconId` | string | 否 | `null` | UI 图标引用 |
| `weaponAnimId` | string | 否 | `null` | 战斗动画效果引用 |
| `sortOrder` | int | 否 | `0` | 图鉴/列表排序 |
| `flags` | object | 否 | `{}` | 扩展布尔：`canTrade`, `canDrop`, `isDebuffImmune` 等 |

### 2.1 `flags` 建议键

| 键 | 类型 | 说明 |
|----|------|------|
| `canTrade` | bool | 可否交易 |
| `canDrop` | bool | 击败后可掉落 |
| `canRepair` | bool | 可否修理 |
| `usesStaffFormula` | bool | 使用杖命中公式 |
| `isMagicDamage` | bool | 伤害走魔防 |
| `ignoreDefense` | bool | 忽视防御（剧情/特殊） |

---

## 3. 运行时实例表 · 字段定义（ItemInstance）

背包/掉落/商店货架中的「一件具体道具」。

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `instanceId` | string/long | 是 | 运行时唯一 id |
| `itemId` | string | 是 | 指向静态表 |
| `usesLeft` | int | 是 | 剩余耐久；无限耐久可固定 `-1` 或等于 `usesMax` 且不减 |
| `isDroppable` | bool | 否 | 本场击败是否掉落 |
| `isEquipped` | bool | 否 | 是否当前装备（每单位最多一把主武） |
| `ownerUnitId` | string | 否 | 所属单位；商店存可为 null |
| `forgeLevel` | int | 否 | 锻造等级（扩展） |
| `customName` | string | 否 | 锻造命名 |
| `sealed` | bool | 否 | 剧情封锁不可用 |

---

## 4. 关联与校验（与 Plan1 职业框架）

| 检查点 | 规则 |
|--------|------|
| 装备武器 | `unit.weaponRank[weaponType] >= item.reqWeaponRank` |
| 体格/负重 | 攻速 ≈ Spd − max(0, Wt − Con)（具体放战斗公式 Plan） |
| 角色专用 | `lockCharacterIds` 空或包含 `characterId` |
| 职业限定 | `lockClassIds` 空或包含 `classId` |
| 射程 | 攻击目标格子曼哈顿距离在 `[minRange,maxRange]` |
| 消耗 | 攻击命中或使用成功后 `usesLeft--`；至 0 销毁或破损态 |
| 弓 | 通常 `tags` 含 `effectiveFlying`；`minRange`≥2 |

---

## 5. 示例配置行（静态）

| itemId | displayName | itemKind | weaponType | req | Mt | Hit | Crit | Wt | Range | usesMax | priceBuy | tags / 效果摘要 |
|--------|-------------|----------|------------|-----|----|-----|------|----|-------|---------|----------|----------------|
| iron_sword | 铁剑 | weapon | sword | E | 5 | 90 | 0 | 5 | 1–1 | 46 | 460 | 基础剑 |
| steel_lance | 钢枪 | weapon | lance | D | 10 | 70 | 0 | 13 | 1–1 | 30 | 840 | 基础枪 |
| iron_axe | 铁斧 | weapon | axe | E | 8 | 75 | 0 | 10 | 1–1 | 45 | 360 | 基础斧 |
| iron_bow | 铁弓 | weapon | bow | E | 6 | 85 | 0 | 5 | 2–2 | 40 | 540 | +effectiveFlying |
| fire | 火焰 | weapon | magicAnima | E | 5 | 90 | 0 | 4 | 1–2 | 40 | 560 | isMagicDamage |
| heal | 治疗之杖 | staff | staff | E | 0 | 0 | 0 | 0 | 1–1 | 30 | 600 | heal ≈ 10+Mag；usesStaffFormula |
| vulnerary | 伤药 | consumable | none | none | 0 | 0 | 0 | 0 | — | 3 | 300 | healHp=10；useTarget=self |
| pure_water | 纯净水 | consumable | none | none | 0 | 0 | 0 | 0 | — | 3 | 900 | 临时 Res↑（effectId） |
| door_key | 门钥匙 | key | none | none | 0 | 0 | 0 | 0 | — | 1 | 50 | useTarget=tile |
| rapier | 细剑 | weapon | sword | E | 7 | 95 | 10 | 5 | 1–1 | 40 | 0 | effectiveArmor+Cavalry；lock 领主可选 |
| killing_edge | 必杀剑 | weapon | sword | C | 9 | 75 | 30 | 7 | 1–1 | 20 | 1300 | 高必杀 |
| brave_sword | 勇者之剑 | weapon | sword | B | 9 | 75 | 0 | 12 | 1–1 | 30 | 3000 | tag:brave |

> 数值为 **框架示例**，可按《圣魔》表再校准；实装时不要依赖未授权 ROM dump 当唯一数据源。

---

## 6. JSON 骨架示例

```json
{
  "items": [
    {
      "itemId": "iron_sword",
      "displayName": "铁剑",
      "description": "常见的铁制剑。",
      "itemKind": "weapon",
      "weaponType": "sword",
      "reqWeaponRank": "E",
      "might": 5,
      "hit": 90,
      "crit": 0,
      "weight": 5,
      "minRange": 1,
      "maxRange": 1,
      "usesMax": 46,
      "priceBuy": 460,
      "priceSell": 230,
      "wexpOnHit": 1,
      "tags": [],
      "useTarget": "enemy",
      "lockCharacterIds": [],
      "lockClassIds": [],
      "iconId": "icon_iron_sword",
      "flags": {
        "canTrade": true,
        "canDrop": true,
        "canRepair": true,
        "isMagicDamage": false
      }
    },
    {
      "itemId": "vulnerary",
      "displayName": "伤药",
      "itemKind": "consumable",
      "weaponType": "none",
      "reqWeaponRank": "none",
      "usesMax": 3,
      "priceBuy": 300,
      "healHp": 10,
      "tags": ["healing"],
      "useTarget": "self",
      "flags": { "canTrade": true, "canDrop": true }
    }
  ]
}
```

### 运行时实例示例

```json
{
  "instanceId": "inst_0001",
  "itemId": "iron_sword",
  "usesLeft": 40,
  "isDroppable": false,
  "isEquipped": true,
  "ownerUnitId": "unit_eirika"
}
```

---

## 7. 建议代码结构（与 Plan1 并列）

```
Core/
  Item/
    ItemId.cs
    ItemKind.cs
    WeaponType.cs
    WeaponRank.cs
    ItemDefinition.cs      // 静态
    ItemInstance.cs        // 运行时
    ItemDatabase.cs        // 加载/查询
    ItemUseService.cs      // 使用/消耗
    EquipService.cs        // 装备合法性
Data/
  items.json
```

---

## 8. 后续 Plan 衔接

| 主题 | 依赖本表 |
|------|----------|
| 战斗公式 | Mt/Hit/Crit/Wt/Range/tags |
| 商店 | priceBuy/Sell、库存 instance |
| 锻造 | forgeLevel、customName |
| 掉落 AI | isDroppable、flags.canDrop |

文档路径（相对 AIDate 根）：`Data/ItemFramework.md`
