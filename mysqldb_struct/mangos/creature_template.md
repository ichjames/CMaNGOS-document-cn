**\`creature_template_classic\` 表**

此表包含生物（Creature）的模板描述。每一个在世界上生成的 [creature](https://github.com/cmangos/issues/wiki/creature) 都是此表中一个生物模板的实例。

这意味着每一个 [creature](https://github.com/cmangos/issues/wiki/creature) **必须** 在此表中定义。

**结构**

| 字段 | 类型 | 为空 | 键 | 默认值 | 额外 | 中文说明 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [Entry](https://github.com/cmangos/issues/wiki/creature_template_classic#entry) | mediumint(8) unsigned | NO | PRI | 0 | | 生物编号（唯一标识） |
| [Name](https://github.com/cmangos/issues/wiki/creature_template_classic#name) | char(100) | NO |  | 0 | | 生物名称 |
| [SubName](https://github.com/cmangos/issues/wiki/creature_template_classic#subname) | char(100) | YES |  | Null | | 生物头衔/子名称（显示在名称下方的 \< \> 内） |
| [MinLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#minlevel) | tinyint(3) unsigned | YES |  | 1 | | 生物最低等级 |
| [MaxLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#maxlevel) | tinyint(3) unsigned | YES |  | 1 | | 生物最高等级 |
| [ModelId1](https://github.com/cmangos/issues/wiki/creature_template_classic#modelid1) | mediumint(8) unsigned | NO |  | 0 | | 主要显示模型ID 1 |
| [ModelId2](https://github.com/cmangos/issues/wiki/creature_template_classic#modelid2) | mediumint(8) unsigned | NO |  | 0 | | 备用显示模型ID 2 |
| [ModelId3](https://github.com/cmangos/issues/wiki/creature_template_classic#modelid3) | mediumint(8) unsigned | NO |  | 0 | | 备用显示模型ID 3 |
| [ModelId4](https://github.com/cmangos/issues/wiki/creature_template_classic#modelid4) | mediumint(8) unsigned | NO |  | 0 | | 备用显示模型ID 4 |
| [Faction](https://github.com/cmangos/issues/wiki/creature_template_classic#faction) | smallint(5) unsigned | NO |  | 0 | | 生物阵营模板ID |
| [Scale](https://github.com/cmangos/issues/wiki/creature_template_classic#scale) | float | NO |  | 0 | | 模型缩放大小（0则使用DBC默认值） |
| [Family](https://github.com/cmangos/issues/wiki/creature_template_classic#family) | tinyint(4) | YES |  | 0 | | 生物家族（仅对野兽类有效） |
| [CreatureType](https://github.com/cmangos/issues/wiki/creature_template_classic#creaturetype) | tinyint(3) unsigned | NO |  | 0 | | 生物类型（人形、野兽、亡灵等） |
| [InhabitType](https://github.com/cmangos/issues/wiki/creature_template_classic#inhabittype) | tinyint(3) unsigned | NO |  | 3 | | 栖息类型（地面、水中、飞行等） |
| [RegenerateStats](https://github.com/cmangos/issues/wiki/creature_template_classic#regeneratestats) | tinyint(3) unsigned | NO |  | 1 | | 生命/法力值回复标志 |
| [RacialLeader](https://github.com/cmangos/issues/wiki/creature_template_classic#racialleader) | tinyint(3) unsigned | NO |  | 0 | | 是否为种族领袖（击杀奖励荣誉） |
| [NpcFlags](https://github.com/cmangos/issues/wiki/creature_template_classic#npcflags) | int(10) unsigned | NO |  | 0 | | NPC功能标志位掩码（任务、商人、训练师等） |
| [UnitFlags](https://github.com/cmangos/issues/wiki/creature_template_classic#unitflags) | int(10) unsigned | NO |  | 0 | | 单位标志位掩码（控制选中、攻击、移动等状态） |
| [DynamicFlags](https://github.com/cmangos/issues/wiki/creature_template_classic#dynamicflags) | int(10) unsigned | NO |  | 0 | | 动态标志位掩码（控制尸体可拾取、被标记等临时状态） |
| [ExtraFlags](https://github.com/cmangos/issues/wiki/creature_template_classic#extraflags) | int(10) unsigned | NO |  | 0 | | 生物额外标志位掩码（免疫、守卫、无经验等特殊属性） |
| [CreatureTypeFlags](https://github.com/cmangos/issues/wiki/creature_template_classic#creaturetypeflags) | int(10) unsigned | YES |  | 0 | | 生物类型标志位掩码（可驯服、可采集等） |
| [StaticFlags1](https://github.com/cmangos/issues/wiki/creature_template_classic#staticflags1) | int(10) unsigned | YES |  | 0 | | 静态标志1 |
| [StaticFlags2](https://github.com/cmangos/issues/wiki/creature_template_classic#staticflags2) | int(10) unsigned | YES |  | 0 | | 静态标志2 |
| [StaticFlags3](https://github.com/cmangos/issues/wiki/creature_template_classic#staticflags3) | int(10) unsigned | YES |  | 0 | | 静态标志3 |
| [StaticFlags4](https://github.com/cmangos/issues/wiki/creature_template_classic#staticflags4) | int(10) unsigned | YES |  | 0 | | 静态标志4 |
| [SpeedWalk](https://github.com/cmangos/issues/wiki/creature_template_classic#speedwalk) | float | YES |  | 1 | | 行走速度（覆盖模型默认值） |
| [SpeedRun](https://github.com/cmangos/issues/wiki/creature_template_classic#speedrun) | float | YES |  | 1.14286 | | 奔跑速度（覆盖模型默认值） |
| [Detection](https://github.com/cmangos/issues/wiki/creature_template_classic#detection) | int | NO |  | 20 | | 警戒/仇恨范围 |
| [CallForHelp](https://github.com/cmangos/issues/wiki/creature_template_classic#callforhelp) | int | NO |  | 0 | | 呼叫帮助范围 |
| [Pursuit](https://github.com/cmangos/issues/wiki/creature_template_classic#pursuit) | int | NO |  | 0 | | 追击范围/脱离战斗距离 |
| [Leash](https://github.com/cmangos/issues/wiki/creature_template_classic#leash) | int | NO |  | 0 | | 活动半径（拴绳）限制 |
| [Timeout](https://github.com/cmangos/issues/wiki/creature_template_classic#timeout) | int | NO |  | 0 | | （功能待确认） |
| [UnitClass](https://github.com/cmangos/issues/wiki/creature_template_classic#unitclass) | int unsigned | NO |  | 0 | | 生物职业（决定基础属性成长） |
| [Rank](https://github.com/cmangos/issues/wiki/creature_template_classic#rank) | tinyint(3) unsigned | YES |  | 0 | | 生物等级（普通、精英、稀有、世界BOSS等） |
| [HealthMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#healthmultiplier) | float | NO |  | 1.0 | | 生命值倍率（用于计算最终生命值） |
| [PowerMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#manamultiplier) | float | NO |  | 1.0 | | 法力值（能量值）倍率（用于计算最终法力值） |
| [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#damagemultiplier) | float | NO |  | 1 | | 伤害倍率（用于计算最终伤害） |
| [DamageVariance](https://github.com/cmangos/issues/wiki/creature_template_classic#damagevariance) | float | NO |  | 1 | | 伤害浮动系数（用于控制最小/最大伤害范围） |
| [ArmorMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#armormultiplier) | float | NO |  | 1 | | 护甲值倍率（用于计算最终护甲值） |
| [ExperienceMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#experiencemultiplier) | float | NO |  | 1 | | 经验值倍率（暂未使用） |
| [MinLevelHealth](https://github.com/cmangos/issues/wiki/creature_template_classic#minlevelhealth) | int(10) unsigned | YES |  | 0 | | 最低等级生命值（旧字段，核心已自动计算） |
| [MaxLevelHealth](https://github.com/cmangos/issues/wiki/creature_template_classic#maxlevelhealth) | int(10) unsigned | YES |  | 0 | | 最高等级生命值（旧字段，核心已自动计算） |
| [MinLevelMana](https://github.com/cmangos/issues/wiki/creature_template_classic#minlevelmana) | int(10) unsigned | YES |  | 0 | | 最低等级法力值（旧字段，核心已自动计算） |
| [MaxLevelMana](https://github.com/cmangos/issues/wiki/creature_template_classic#maxlevelmana) | int(10) unsigned | YES |  | 0 | | 最高等级法力值（旧字段，核心已自动计算） |
| [MinMeleeDmg](https://github.com/cmangos/issues/wiki/creature_template_classic#minmeleedmg) | float | YES |  | 0 | | 最小近战伤害（旧字段，核心已自动计算） |
| [MaxMeleeDmg](https://github.com/cmangos/issues/wiki/creature_template_classic#maxmeleedmg) | float | YES |  | 0 | | 最大近战伤害（旧字段，核心已自动计算） |
| [MinRangedDmg](https://github.com/cmangos/issues/wiki/creature_template_classic#minrangeddmg) | float | NO |  | 0 | | 最小远程伤害（旧字段，核心已自动计算） |
| [MaxRangedDmg](https://github.com/cmangos/issues/wiki/creature_template_classic#maxrangeddmg) | float | NO |  | 0 | | 最大远程伤害（旧字段，核心已自动计算） |
| [Armor](https://github.com/cmangos/issues/wiki/creature_template_classic#armor) | mediumint(8) unsigned | NO |  | 0 | | 护甲值（旧字段，核心已自动计算） |
| [MeleeAttackPower](https://github.com/cmangos/issues/wiki/creature_template_classic#meleeattackpower) | int(10) unsigned | NO |  | 0 | | 近战攻击强度（旧字段，核心已自动计算） |
| [RangedAttackPower](https://github.com/cmangos/issues/wiki/creature_template_classic#rangedattackpower) | smallint(5) unsigned | NO |  | 0 | | 远程攻击强度（旧字段，核心已自动计算） |
| [MeleeBaseAttackTime](https://github.com/cmangos/issues/wiki/creature_template_classic#meleebaseattacktime) | int(10) unsigned | YES |  | 0 | | 近战基础攻击间隔（毫秒） |
| [RangedBaseAttackTime](https://github.com/cmangos/issues/wiki/creature_template_classic#rangedbaseattacktime) | int(10) unsigned | YES |  | 0 | | 远程基础攻击间隔（毫秒） |
| [DamageSchool](https://github.com/cmangos/issues/wiki/creature_template_classic#damageschool) | tinyint(4) | NO |  | 0 | | 近战伤害类型（物理、火焰、冰霜等） |
| [MinLootGold](https://github.com/cmangos/issues/wiki/creature_template_classic#minlootgold) | mediumint(8) unsigned | NO |  | 0 | | 最小掉落金钱（铜币） |
| [MaxLootGold](https://github.com/cmangos/issues/wiki/creature_template_classic#maxlootgold) | mediumint(8) unsigned | NO |  | 0 | | 最大掉落金钱（铜币） |
| [LootId](https://github.com/cmangos/issues/wiki/creature_template_classic#lootid) | mediumint(8) unsigned | NO |  | 0 | | 普通掉落模板ID |
| [PickpocketLootId](https://github.com/cmangos/issues/wiki/creature_template_classic#pickpocketlootid) | mediumint(8) unsigned | NO |  | 0 | | 偷窃掉落模板ID |
| [SkinningLootId](https://github.com/cmangos/issues/wiki/creature_template_classic#skinninglootid) | mediumint(8) unsigned | NO |  | 0 | | 剥皮（及采药/采矿/工程）掉落模板ID |
| [KillCredit1](https://github.com/cmangos/issues/wiki/creature_template_classic#killcredit1) | int(11) unsigned | NO |  | 0 | | 击杀计数生物编号1（用于任务进度） |
| [KillCredit2](https://github.com/cmangos/issues/wiki/creature_template_classic#killcredit2) | int(11) unsigned | NO |  | 0 | | 击杀计数生物编号2（用于任务进度） |
| [MechanicImmuneMask](https://github.com/cmangos/issues/wiki/creature_template_classic#mechanicimmunemask) | int(10) unsigned | NO |  | 0 | | 法术效果免疫掩码（嘲讽、恐惧、昏迷等） |
| [SchoolImmuneMask](https://github.com/cmangos/issues/wiki/creature_template_classic#schoolimmunemask) | int(10) unsigned | NO |  | 0 | | 法术学派免疫掩码（火焰、冰霜、暗影等） |
| [ResistanceHoly](https://github.com/cmangos/issues/wiki/creature_template_classic#resistanceholy) | int(10) unsigned | NO |  | 0 | | 神圣抗性 |
| [ResistanceFire](https://github.com/cmangos/issues/wiki/creature_template_classic#resistancefire) | smallint(5) | NO |  | 0 | | 火焰抗性 |
| [ResistanceNature](https://github.com/cmangos/issues/wiki/creature_template_classic#resistancenature) | smallint(5) | NO |  | 0 | | 自然抗性 |
| [ResistanceFrost](https://github.com/cmangos/issues/wiki/creature_template_classic#resistancefrost) | smallint(5) | NO |  | 0 | | 冰霜抗性 |
| [ResistanceShadow](https://github.com/cmangos/issues/wiki/creature_template_classic#resistanceshadow) | smallint(5) | NO |  | 0 | | 暗影抗性 |
| [ResistanceArcane](https://github.com/cmangos/issues/wiki/creature_template_classic#resistancearcane) | smallint(5) | NO |  | 0 | | 奥术抗性 |
| [PetSpellDataId](https://github.com/cmangos/issues/wiki/creature_template_classic#petspelldataid) | mediumint(8) unsigned | NO |  | 0 | | 宠物法术数据ID（客户端显示用） |
| [MovementType](https://github.com/cmangos/issues/wiki/creature_template_classic#movementtype) | tinyint(3) unsigned | NO |  | 0 | | 移动类型（站立、随机移动、路径移动等） |
| [TrainerType](https://github.com/cmangos/issues/wiki/creature_template_classic#trainertype) | tinyint(4) | YES |  | 0 | | 训练师类型（职业、骑术、专业技能、宠物） |
| [TrainerSpell](https://github.com/cmangos/issues/wiki/creature_template_classic#trainerspell) | mediumint(8) unsigned | YES |  | 0 | | 训练师前提法术（专业技能训练师需先学会此法术） |
| [TrainerClass](https://github.com/cmangos/issues/wiki/creature_template_classic#trainerclass) | tinyint(3) unsigned | YES |  | 0 | | 训练师职业要求（职业训练师和宠物训练师用） |
| [TrainerRace](https://github.com/cmangos/issues/wiki/creature_template_classic#trainerrace) | tinyint(3) unsigned | YES |  | 0 | | 训练师种族要求（骑术训练师用） |
| [TrainerTemplateId](https://github.com/cmangos/issues/wiki/creature_template_classic#trainertemplateid) | mediumint(8) unsigned | NO |  | 0 | | 训练师模板ID |
| [VendorTemplateId](https://github.com/cmangos/issues/wiki/creature_template_classic#vendortemplateid) | mediumint(8) unsigned | NO |  | 0 | | 商人模板ID |
| [GossipMenuId](https://github.com/cmangos/issues/wiki/creature_template_classic#gossipmenuid) | mediumint(8) unsigned | YES |  | 0 | | 对话菜单ID |
| [InteractionPauseTimer](https://github.com/cmangos/issues/wiki/creature_template_classic#InteractionPauseTimer) | int(10) unsigned | NO |  | -1 | | 对话后暂停路径移动的等待时间（毫秒） |
| [VisibilityDistanceType](https://github.com/cmangos/issues/wiki/creature_template_classic#visibilityDistanceType) | tinyint(4) | YES |  | 0 | | 可见距离类型 |
| [CorpseDecay](https://github.com/cmangos/issues/wiki/creature_template_classic#CorpseDecay) | int(10) unsigned | NO |  | 0 | | 尸体消失时间（秒） |
| [SpellList](https://github.com/cmangos/issues/wiki/creature_template_classic#SpellList) | int(11) | NO |  | 0 | | 生物法术列表ID |
| [EquipmentTemplateId](https://github.com/cmangos/issues/wiki/creature_template_classic#equipmenttemplateid) | mediumint(8) unsigned | NO |  | 0 | | 装备模板ID |
| [Civilian](https://github.com/cmangos/issues/wiki/creature_template_classic#civilian) | tinyint(3) unsigned | YES |  | 0 | | 是否为平民（影响荣誉击杀判定） |
| [AIName](https://github.com/cmangos/issues/wiki/creature_template_classic#ainame) | char(64) | NO |  |  | | 人工智能（AI）系统名称 |
| [ScriptName](https://github.com/cmangos/issues/wiki/creature_template_classic#scriptname) | char(64) | NO |  |  | | 核心脚本（SD2）名称 |

**字段描述**

**Entry**

这是经典版数据库中所有生物的主要 NPC 编号。由于经典版中不存在 HeroicEntry 或 DifficultyEntry，因此不需要 [\`creature\`.\`SpawnMask\`](https://github.com/cmangos/issues/wiki/creature#SpawnMask)。

**Name**

生物的基础名称。

**SubName**

生物的副名称或头衔，显示在生物名称下方的 \< \> 内。

**MinLevel**

如果生物有等级范围，则此为最低等级。对于单一等级的生物，MinLevel = MaxLevel。

**MaxLevel**

如果生物有等级范围，则此为最高等级。对于单一等级的生物，MinLevel = MaxLevel。

**ModelId1**

客户端应用于此生物的主要图形模型。这是一个 [Creature_Model_Info.Entry](https://github.com/cmangos/issues/wiki/Creature_Model_Info#Entry)。

**ModelId2**

客户端应用于此生物的可选额外图形模型。这是一个 [Creature_Model_Info.Entry](https://github.com/cmangos/issues/wiki/Creature_Model_Info#Entry)。

**ModelId3**

客户端应用于此生物的可选额外图形模型。这是一个 [Creature_Model_Info.Entry](https://github.com/cmangos/issues/wiki/Creature_Model_Info#Entry)。

**ModelId4**

客户端应用于此生物的可选额外图形模型。这是一个 [Creature_Model_Info.Entry](https://github.com/cmangos/issues/wiki/Creature_Model_Info#Entry)。

**Faction**

生物的阵营。参见 [FactionTemplate.dbc](https://github.com/cmangos/issues/wiki/FactionTemplate.dbc)。注意，即使多个阵营名称相同，它们之间的相互关系也可能不同。

注意：此字段也控制生物的家族援助机制。只有相同阵营的生物才会互相援助。

**Scale**

如果此值非零，则定义生物在游戏中显示模型大小的手动覆盖值。如果为零，生物将使用从 DBC 中获取的默认模型大小。

**Family**

定义此生物所属的家族。仅在 [CreatureType](https://github.com/cmangos/issues/wiki/creature_template_classic#CreatureType) 为 1（野兽）时使用。

| ID | 家族 | ID | 家族 | ID | 家族 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 狼 | 15 | 地狱卫士 | 29 | 灵翼龙 |
| 2 | 豹 | 16 | 蝎子 | 30 | 蛇 |
| 3 | 蜘蛛 | 17 | 海龟 | 31 | 蛾 |
| 4 | 熊 | 18 | 小鬼 | 32 | 奇美拉 |
| 5 | 野猪 | 19 | 蝙蝠 | 33 | 魔暴龙 |
| 6 | 鳄鱼 | 20 | 土狼 | 34 | 食尸鬼 |
| 7 | 食腐鸟 | 21 | 猛禽 | 35 | 其拉虫 |
| 8 | 螃蟹 | 22 | 风蛇 | 36 | 蠕虫 |
| 9 | 猩猩 | 23 | 遥控器 | 37 | 犀牛 |
| 10 | 迅猛龙 | 24 | 恶魔卫士 | 38 | 黄蜂 |
| 11 | 陆行鸟 | 25 | 龙鹰 | 39 | 熔岩犬 |
| 12 | 地狱猎犬 | 26 | 掠食者 | 40 | 灵魂兽 |
| 13 | 虚空行者 | 27 | 迁跃兽 |  |
| 14 | 魅魔 | 28 | 孢子蝠 |  |

**CreatureType**

此字段定义此 NPC 的生物类型。

| ID | 类型 |
| :--- | :--- |
| 0 | 无 |
| 1 | 野兽 |
| 2 | 龙类 |
| 3 | 恶魔 |
| 4 | 元素生物 |
| 5 | 巨人 |
| 6 | 亡灵 |
| 7 | 人形生物 |
| 8 | 小动物 |
| 9 | 机械 |
| 10 | 未指定 |
| 11 | 图腾 |
| 12 | 非战斗宠物 |
| 13 | 气体云雾 |

**InhabitType**

此字段控制生物可以移动、追击和攻击的区域。
NPC 仅限于在此类型上移动：

| ID | 类型 |
| :--- | :--- |
| 1 | 仅地面移动 |
| 2 | 仅水中移动 |
| 3 | 地面和水上移动 |
| 4 | 总是飞行 |
| 5 | 在地面上空总是飞行 |
| 6 | 在水面上空总是飞行 |
| 7 | 在任何东西上空总是飞行（但也可以行走和游泳） |

**RegenerateStats**

此字段控制生物是否应该回复其生命值/状态（数据标志）。

| 值 | 位 | 名称 | 描述 |
| :--- | :--- | :--- | :--- |
| 0 | 0x000 | - | NPC **不**回复状态 |
| 1 | 0x001 | REGEN_FLAG_HEALTH_IN_COMBAT | NPC **在战斗中**回复生命值 |
| 2 | 0x002 | REGEN_FLAG_HEALTH | NPC **回复**生命值 |
| 4 | 0x004 | REGEN_FLAG_POWER_IN_COMBAT | NPC **在战斗中**回复能量（法力值） |
| 8 | 0x008 | REGEN_FLAG_POWER | NPC **回复**能量（法力值） |
| 14 | 0x00E | REGEN_FLAG_HEALTH+REGEN_FLAG_POWER_IN_COMBAT+REGEN_FLAG_POWER | 默认值 |

**RacialLeader**

此字段是一个布尔标志，指示该生物是否为种族领袖。击杀种族领袖奖励 100 点荣誉点数。

| 值 | 描述 |
| :--- | :--- |
| 0 | NPC **不是**种族领袖 |
| 1 | NPC **是**种族领袖 |

**NpcFlags**

此字段是一个位掩码，表示分配给该生物的 NPC 标志。每一位控制一个不同的标志，要组合标志，可以将所需的每个标志相加，从而激活相应的位。

***请注意，以下值仅对经典版有效！对于 TBC 和 WotLK，请查看它们各自的维基页面（[creature_template_tbc](https://github.com/cmangos/issues/wiki/creature_template_tbc)（2.4.3）[creature_template](https://github.com/cmangos/issues/wiki/creature_template)（3.3.5a）)***

| 位掩码 | 值 | 标志 | 注释 |
| :--- | :--- | :--- | :--- |
| 0x00000000 | 0 | UNIT_NPC_FLAG_NONE | 无 |
| 0x00000001 | 1 | UNIT_NPC_FLAG_GOSSIP | 如果生物有更多对话选项，添加此标志以显示菜单。 |
| 0x00000002 | 2 | UNIT_NPC_FLAG_QUESTGIVER | 任何给予或接收任务的生物都需要有此标志。 |
| 0x00000004 | 4 | UNIT_NPC_FLAG_VENDOR | **TBC+ 使用 128** -- 任何出售物品的生物都需要有此标志。 |
| 0x00000008 | 8 | UNIT_NPC_FLAG_FLIGHTMASTER | **TBC+ 使用 8192** -- 任何作为飞行管理员的生物都有此标志。 |
| 0x00000010 | 16 | UNIT_NPC_FLAG_TRAINER | 允许生物拥有训练师列表来教授法术。 |
| 0x00000020 | 32 | UNIT_NPC_FLAG_SPIRITHEALER | **TBC+ 使用 16384** -- 使生物对活着的角色不可见，并具有复活功能。 |
| 0x00000040 | 64 | UNIT_NPC_FLAG_SPIRITGUIDE | **TBC+ 使用 32768** |
| 0x00000080 | 128 | UNIT_NPC_FLAG_INNKEEPER | **TBC+ 使用 65536** -- 带有此标志的生物可以设置炉石位置。 |
| 0x00000100 | 256 | UNIT_NPC_FLAG_BANKER | **TBC+ 使用 131072** -- 带有此标志的生物可以显示银行界面。 |
| 0x00000200 | 512 | UNIT_NPC_FLAG_PETITIONER | **TBC+ 使用 262144** -- 公会申请表 |
| 0x00000400 | 1024 | UNIT_NPC_FLAG_TABARDDESIGNER | **TBC+ 使用 524288** -- 允许设计公会战袍。 |
| 0x00000800 | 2048 | UNIT_NPC_FLAG_BATTLEMASTER | **TBC+ 使用 1048576** -- 带有此标志的生物将玩家传送至战场。 |
| 0x00001000 | 4096 | UNIT_NPC_FLAG_AUCTIONEER | **TBC+ 使用 2097152** -- 允许生物显示拍卖行列表。 |
| 0x00002000 | 8192 | UNIT_NPC_FLAG_STABLEMASTER | **TBC+ 使用 4194304** -- 有为猎人寄存宠物的选项。 |
| 0x00004000 | 16384 | UNIT_NPC_FLAG_REPAIR | **TBC+ 使用 4096** -- 带有此标志的生物可以修理物品。 |
| 0x20000000 | 536870912 | UNIT_NPC_FLAG_OUTDOORPVP | 自定义标志！ -- 用于户外 PvP 生物 |

示例：
如果你想要一个 NPC 既是任务给予者 (2)，又是商人 (4)，并且还能修理 (16384)，你只需将特定的标志相加：
2 + 4 + 16384 = 16390。
NpcFlags = 16390

**UnitFlags**

此字段允许手动将单位标志应用于 NPC。这是一个位掩码字段，要应用多个标志，只需将不同的标志相加即可。

一些已知的可能标志有：

| 位掩码 | 十进制 | 名称 | 注释 |
| :--- | :--- | :--- | :--- |
| 0x00000001 | 1 | UNIT_FLAG_UNK_0 | 禁用移动检查，可能与失去客户端控制数据包配对。我们用它来为 GM 模式添加自定义悬崖行走，直到知道实际用例。 |
| 0x00000002 | 2 | UNIT_FLAG_SPAWNING | 正在生成 -- 其他用途是错误的 |
| 0x00000004 | 4 | UNIT_FLAG_CLIENT_CONTROL_LOST | 服务器脚本发起的未指定的通用失去控制，禁用移动检查，与失去客户端控制数据包配对。 |
| 0x00000008 | 8 | UNIT_FLAG_PLAYER_CONTROLLED | 玩家、宠物、图腾、守护者、伙伴、被魅惑单位、任何与玩家相关的单位 |
| 0x00000010 | 16 | UNIT_FLAG_PET_RENAME | 旧宠物重命名：在 TBC+ 中移至 UNIT_FIELD_BYTES_2,2 |
| 0x00000020 | 32 | UNIT_FLAG_PET_ABANDON | 旧宠物放弃：在 TBC+ 中移至 UNIT_FIELD_BYTES_2,2 |
| 0x00000040 | 64 | UNIT_FLAG_UNK_6 | 与移动相关？常与 UNIT_FLAG_SWIMMING 配对 |
| 0x00000080 | 128 | UNIT_FLAG_NOT_ATTACKABLE_1 | TBC+ |
| 0x00000100 | 256 | UNIT_FLAG_IMMUNE_TO_PLAYER | 目标对玩家免疫 |
| 0x00000200 | 512 | UNIT_FLAG_IMMUNE_TO_NPC | 目标对非玩家角色免疫 |
| 0x00000400 | 1024 | UNIT_FLAG_LOOTING | TBC+ |
| 0x00000800 | 2048 | UNIT_FLAG_PET_IN_COMBAT | TBC+ |
| 0x00001000 | 4096 | UNIT_FLAG_PVP | 允许对其施放物品法术。在 3.0.3 中更改 |
| 0x00002000 | 8192 | UNIT_FLAG_SILENCED | 被沉默，2.1.1 |
| 0x00004000 | 16384 | UNIT_FLAG_PERSUADED | 被说服，2.0.8 |
| 0x00008000 | 32768 | UNIT_FLAG_SWIMMING | 控制水中游泳动画 -- **待确认：是动态还是静态** |
| 0x00010000 | 65536 | UNIT_FLAG_UNTARGETABLE | 无法被攻击或法术选为目标 |
| 0x00020000 | 131072 | UNIT_FLAG_PACIFIED | 被安抚，3.0.3 |
| 0x00040000 | 262144 | UNIT_FLAG_STUNNED | 单位受眩晕影响，禁用转向和平移移动 |
| 0x00080000 | 524288 | UNIT_FLAG_IN_COMBAT | 在战斗中 |
| 0x00100000 | 1048576 | UNIT_FLAG_TAXI_FLIGHT | 单位在乘坐飞行器，与重复的失去客户端控制数据包配对（可能是遗留的服务器端 hack）。客户端禁用飞行途中不允许的任何法术施放。 |
| 0x00200000 | 2097152 | UNIT_FLAG_DISARMED | TBC+ |
| 0x00400000 | 4194304 | UNIT_FLAG_CONFUSED | 单位受迷惑移动影响，禁用移动检查，与失去客户端控制数据包配对。 |
| 0x00800000 | 8388608 | UNIT_FLAG_FLEEING | 单位受逃跑移动影响，禁用移动检查，与失去客户端控制数据包配对。 |
| 0x01000000 | 16777216 | UNIT_FLAG_POSSESSED | 单位被另一个单位远程控制，禁用移动检查，与失去客户端控制数据包配对。新主人被允许使用近战攻击，并且不能通过鼠标在世界上选择此单位（就像它是自己的角色一样）。 |
| 0x02000000 | 33554432 | UNIT_FLAG_UNINTERACTIBLE | 无法通过鼠标选择 |
| 0x04000000 | 67108864 | UNIT_FLAG_SKINNABLE | 可剥皮 |
| 0x08000000 | 134217728 | UNIT_FLAG_AURAS_VISIBLE | 魔法侦测 |
| 0x10000000 | 268435456 | UNIT_FLAG_UNK_28 |  |
| 0x20000000 | 536870912 | UNIT_FLAG_PREVENT_ANIM | 用于假死法术 |
| 0x40000000 | 1073741824 | UNIT_FLAG_SHEATHE | 收起武器 |
| 0x80000000 | 2147483648 | UNIT_FLAG_IMMUNE | 设置可剥皮图标并改变肖像颜色（在 2.4.3 中无影响） |

**DynamicFlags**

此字段标志控制生物的外观。这些标志值可以相加组合以获得任何期望的组合。

一些已知的标志值：

| 标志 | 名称 | 注释 |
| :--- | :--- | :--- |
| 0 | UNIT_DYNFLAG_NONE | 无 |
| 1 | UNIT_DYNFLAG_LOOTABLE | 可拾取 |
| 2 | UNIT_DYNFLAG_TRACK_UNIT | 追踪单位 |
| 4 | UNIT_DYNFLAG_TAPPED | Lua_UnitIsTapped -- 使生物名称显示为灰色（用于模拟已归属生物）??? |
| 8 | UNIT_DYNFLAG_TAPPED_BY_PLAYER | Lua_UnitIsTappedByPlayer -- 被玩家归属 |
| 16 | UNIT_DYNFLAG_SPECIALINFO | 显示生物基本状态（生命值、伤害、抗性、可驯服）。 |
| 32 | UNIT_DYNFLAG_DEAD | 使生物显示为死亡状态（这**不会**使生物名称变灰） |
| 64 | UNIT_DYNFLAG_REFER_A_FRIEND | 招募好友 |
| 128 | UNIT_DYNFLAG_TAPPED_BY_ALL_THREAT_LIST | Lua_UnitIsTappedByAllThreatList -- 被所有仇恨列表中的玩家归属 |

**ExtraFlags**

此字段控制应用于某些 NPC 特定属性的标志。

| 位 | 十六进制 | 名称 | 描述 |
| :--- | :--- | :--- | :--- |
| 1 | 0x00000001 | CREATURE_EXTRA_FLAG_INSTANCE_BIND | 生物击杀将实例与击杀者及其队伍绑定 |
| 2 | 0x00000002 | CREATURE_EXTRA_FLAG_NO_AGGRO_ON_SIGHT | 无视视野仇恨（忽略阵营/声望敌对） |
| 4 | 0x00000004 | CREATURE_EXTRA_FLAG_NO_PARRY | 生物不能招架 |
| 8 | 0x00000008 | CREATURE_EXTRA_FLAG_NO_PARRY_HASTEN | 生物不能在招架时反击 |
| 16 | 0x00000010 | CREATURE_EXTRA_FLAG_NO_BLOCK | 生物不能格挡 |
| 32 | 0x00000020 | CREATURE_EXTRA_FLAG_NO_CRUSH | 生物不能造成碾压攻击 |
| 64 | 0x00000040 | CREATURE_EXTRA_FLAG_NO_XP_AT_KILL | 生物击杀不提供经验值 |
| 128 | 0x00000080 | CREATURE_EXTRA_FLAG_INVISIBLE | 生物对玩家总是隐形（ mostly trigger creatures） |
| 256 | 0x00000100 | CREATURE_EXTRA_FLAG_REUSE |  |
| 512 | 0x00000200 | CREATURE_EXTRA_FLAG_AGGRO_ZONE | 生物在获得仇恨时与区域内的所有单位进入战斗 |
| 1024 | 0x00000400 | CREATURE_EXTRA_FLAG_GUARD | 生物是守卫 |
| 2048 | 0x00000800 | CREATURE_EXTRA_FLAG_NO_CALL_ASSIST | 生物在获得仇恨时不应呼叫援助 |
| 4096 | 0x00001000 | CREATURE_EXTRA_FLAG_ACTIVE | 生物是活动对象。将加载此生物的网格并将其设置为活动状态 |
| 8192 | 0x00002000 | CREATURE_EXTRA_FLAG_MMAP_FORCE_ENABLE | 强制生物使用 MMaps |
| 16384 | 0x00004000 | CREATURE_EXTRA_FLAG_MMAP_FORCE_DISABLE | 强制生物**不**使用 MMaps |
| 32768 | 0x00008000 | CREATURE_EXTRA_FLAG_WALK_IN_WATER | 强制生物在水中行走，即使它能游泳 |
| 65536 | 0x00010000 | CREATURE_EXTRA_FLAG_CIVILIAN | CreatureInfo→civilian 的替代品（因为 Civilian 列在资料片中被移除） |
| 131072 | 0x00020000 | CREATURE_EXTRA_FLAG_NO_MELEE | 生物不能进行近战攻击 |
| 262144 | 0x00040000 | NOT_IMPLEMENTED_CREATURE_EXTRA_FLAG_FAR_VIEW | 具有远视距的生物（未实现） |
| 524288 | 0x00080000 | CREATURE_EXTRA_FLAG_FORCE_ATTACKING_CAPABILITY | 对于不可攻击、不可选为目标但仍应能够攻击的生物，设置 SetForceAttackingCapability(true); |
| 1048576 | 0x00100000 | CREATURE_EXTRA_FLAG_DYNGUID | 临时过渡标志 -- 此编号的生成使用动态 GUID 系统 |
| 2097152 | 0x00200000 | CREATURE_EXTRA_FLAG_COUNT_SPAWNS | 在地图*中计数生物生成 |
| 4194304 | 0x00400000 | CREATURE_EXTRA_FLAG_IGNORE_FEIGN_DEATH | 忽略假死 |
| 8388608 | 0x00800000 | CREATURE_EXTRA_FLAG_DUAL_WIELD_FORCED | 生物总是双持（即使未装备武器） |
| 16777216 | 0x01000000 | CREATURE_EXTRA_FLAG_NO_SKILL_GAINS | 不给予攻击者武器技能提升 |

**CreatureTypeFlags**

此字段控制一个怪物是否可采矿或可采药。如果使用了这些标志中的任何一个，则当它被采药/采矿时给予的战利品将存储在 [Skinning_Loot_Template](https://github.com/cmangos/issues/wiki/Skinning_Loot_Template) 表中。除了这两个标志，此字段在服务器端没有特殊意义。

它将在 SMSG_CREATURE_QUERY_RESPONSE 中发送给客户端。源自 CreatureStaticFlags。

| 标志 | 名称 | 注释 |
| :--- | :--- | :--- |
| 1 | CREATURE_TYPEFLAGS_TAMEABLE | 使怪物可驯服（必须是野兽并且设置了家族） |
| 2 | CREATURE_TYPEFLAGS_GHOST_VISIBLE | 设置玩家是幽灵时**也**能看到的生物。客户端在 CanInteract 函数中使用，无法被攻击 |
| 4 | CREATURE_TYPEFLAGS_UNK3 | 为鼠标提示设置 "BOSS" 标志 |
| 8 | CREATURE_TYPEFLAGS_UNK4 |  |
| 16 | CREATURE_TYPEFLAGS_UNK5 | 在客户端鼠标提示中控制与生物阵营相关的内容 |
| 32 | CREATURE_TYPEFLAGS_UNK6 | 与声音有关 |
| 64 | CREATURE_TYPEFLAGS_UNK7 | 与可攻击/不可攻击带有法术的生物有关 |
| 128 | CREATURE_TYPEFLAGS_INTERACT_DEAD | 与单位交互/任务状态请求有关 |
| 136 | CREATURE_TYPEFLAGS_NON_PVP_PLAYER |  |
| 256 | CREATURE_TYPEFLAGS_HERBLOOT | 使怪物尸体可采药 -- 使用剥皮战利品字段 |
| 512 | CREATURE_TYPEFLAGS_MININGLOOT | 使怪物尸体可采矿 -- 使用剥皮战利品字段 |
| 1024 | CREATURE_TYPEFLAGS_ANIMATION_UNK11 | 不清楚，但客户端使用 |
| 2048 | CREATURE_TYPEFLAGS_ANIMATION_UNK12 | 与在坐骑上施法的可能性有关 |
| 4096 | CREATURE_TYPEFLAGS_CAN_ASSIST | 可以在战斗中援助任何玩家或队伍。通常见于护送 NPC |
| 8192 | CREATURE_TYPEFLAGS_UNK14 | 从 Lua_PetHasActionBar 中的调用检查 |
| 16384 | CREATURE_TYPEFLAGS_UNK15 | Lua_UnitGUID，如果设置了此标志，客户端执行 guid_low &= 0xFF000000 |
| 32768 | CREATURE_TYPEFLAGS_ENGINEERLOOT | 使怪物尸体可工程学拆卸 -- 使用剥皮战利品字段 |

**StaticFlags1**

**StaticFlags2**

**StaticFlags3**

**StaticFlags4**

[Creature Static Flags](https://github.com/cmangos/issues/wiki/CreatureStaticFlags)

**SpeedWalk**

此字段控制 NPC 行走时的移动速度。此值来自嗅探数据包数据。
注意：仅当模型的默认 SpeedWalk 对于 creature_template.entry 不正确时，才应使用此字段作为覆盖。（ [creature_model_info.SpeedWalk](https://github.com/cmangos/issues/wiki/creature_model_info#SpeedWalk) ）

`SpeedWalk` = (嗅探值 / 2.5)

（默认值为：1）

**SpeedRun**

此字段控制 NPC 奔跑时的移动速度。此值来自嗅探数据包数据。
注意：仅当模型的默认 SpeedRun 对于 creature_template.entry 不正确时，才应使用此字段作为覆盖。（ [creature_model_info.SpeedRun](https://github.com/cmangos/issues/wiki/creature_model_info#SpeedRun) ）

`SpeedRun` = (嗅探值 / 7)

（默认值为：1.14286）

**Detection**

仇恨范围，更多信息待补充。

（默认值为：20）

**CallForHelp**

（默认值为：10）-- CreatureFamilyAssistanceRadius mangosd.conf

**Pursuit**

更多信息待补充。

**Leash**

更多信息待补充。

**UnitClass**

NPC 单位职业。此字段是一个关键值，决定了 NPC 的基础属性系统。

NPC 的单位职业是一个基石值，用于 [Creature_Template_Classlevelstats](https://github.com/cmangos/issues/wiki/Creature_Template_Classlevelstats) 来确定 NPC 的属性。

此值包含在嗅探数据中：UNIT_FIELD_BYTES_0_1 -- SMSG_UPDATE_OBJECT 中的 UNIT_BYTES_0_OFFSET_CLASS

| **枚举 UnitBytes0Offsets** | **名称** |
| :--- | :--- |
| UNIT_BYTES_0_OFFSET_RACE | 0 |
| UNIT_BYTES_0_OFFSET_CLASS | 1 |
| UNIT_BYTES_0_OFFSET_GENDER | 2 |
| UNIT_BYTES_0_OFFSET_POWER_TYPE | 3 |

NPC 属性指的是：（生命值/法力值/伤害/护甲）。

| ID | 名称 | 注释 |
| :--- | :--- | :--- |
| 1 | CLASS_WARRIOR | 战士 |
| 2 | CLASS_PALADIN | 圣骑士 |
| 4 | CLASS_ROGUE | 潜行者 (wotlk+) |
| 8 | CLASS_MAGE | 法师 |

它是确定 NPC 职业等级属性的关键字段。

注意：通常**只有**载具是 Class=4

战士：没有法力值，生命值和伤害最高。
圣骑士：拥有少量法力值，生命值和伤害略低于战士。
潜行者：（目前知之甚少，但似乎都是载具）
法师：拥有大量法力值，但生命值和伤害非常低。

**Rank**

此字段决定 NPC 的等级 -- 枚举 CreatureEliteType：

| 等级 | 名称 | 注释 |
| :--- | :--- | :--- |
| 0 | CREATURE_ELITE_NORMAL | 普通 |
| 1 | CREATURE_ELITE_ELITE | 精英 -- 更高的伤害，更多的生命值，更好的战利品。 |
| 2 | CREATURE_ELITE_RAREELITE | 稀有精英 -- 稀有怪物，但具有精英的伤害和生命值。 |
| 3 | CREATURE_ELITE_WORLDBOSS | 世界首领 -- 最高等级，最好的战利品，最长的刷新时间。 |
| 4 | CREATURE_ELITE_RARE | 稀有 -- 战利品稍好，刷新时间较长。 |
| 5 | CREATURE_UNKNOWN | 未知 -- 在 2.2.3 中发现用于 2 个怪物 |

**HealthMultiplier**

此值来自 WDB 和嗅探数据。这是计算 NPC 特定生命值的**主要**数据库值。NPC 有各种 HealthMultipliers，但通常是相当四舍五入的值。

（注意：地下城/团队副本/世界首领通常具有非常大且通常非常四舍五入的值）

这是用于乘以 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) 中的 BaseHealthExp? 值以计算 NPC 最终生命值的乘数。

公式：
MinLevelHealth = **四舍五入** (BaseHealthExp? * HealthMultiplier)
MaxLevelHealth = **四舍五入** (BaseHealthExp? * HealthMultiplier)

示例：

| 字段 | 值 | 注释 |
| :--- | :--- | :--- |
| [Entry](https://github.com/cmangos/issues/wiki/creature_template_classic#Entry) | 871 | 盐鳞战士 |
| [MinLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#MinLevel) | 35 | (嗅探数据) |
| [MaxLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#MaxLevel) | 36 | (嗅探数据) |
| [MinLevelHealth](https://github.com/cmangos/issues/wiki/creature_template_classic#MinLevelHealth) | 1403 | (嗅探数据) |
| [MaxLevelHealth](https://github.com/cmangos/issues/wiki/creature_template_classic#MaxLevelHealth) | 1469 | (嗅探数据) |
| [UnitClass](https://github.com/cmangos/issues/wiki/creature_template_classic#UnitClass) | 1 | (嗅探数据) |
| [HealthMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#HealthMultiplier) | 1.15 | (嗅探数据) |

35 级 BaseHealthExp0: 1220
（来自 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) -- 根据嗅探数据和广泛研究计算出的基础生命值）

36 级 BaseHealthExp0: 1277
（来自 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) -- 根据嗅探数据和广泛研究计算出的基础生命值）

MinLevelHealth = **四舍五入** (1220*1.15) = 1403 (1403)
MaxLevelHealth = **四舍五入** (1277*1.15) = 1468.55 (1469)

**PowerMultiplier**

此值来自 WDB 和嗅探数据。这是计算 NPC 特定法力值的**主要**数据库值。所有 NPC 的 PowerMultipliers 都有很好的四舍五入值。

UNIT_FIELD_BYTES_0_3 (4), UNIT_BYTES_0_OFFSET_POWER_TYPE

这是用于乘以 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) 中的 BaseMana 值以计算 NPC 最终法力值的乘数。

注意：与生命值和伤害不同，基础法力值**不**随资料片版本缩放。
注意：对于使用法力之外其他能量的 NPC，它将反映该能量。

公式：
MinLevelMana = **四舍五入** (BaseMana * ManaMultiplier)
MaxLevelMana = **四舍五入** (BaseMana * ManaMultiplier)

示例：

| 字段 | 值 | 注释 |
| :--- | :--- | :--- |
| [Entry](https://github.com/cmangos/issues/wiki/creature_template_classic#Entry) | 7335 | 死亡头颅地卜师 |
| [MinLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#MinLevel) | 35 | (嗅探数据) |
| [MaxLevel](https://github.com/cmangos/issues/wiki/creature_template_classic#MaxLevel) | 35 | (嗅探数据) |
| [MinLevelMana](https://github.com/cmangos/issues/wiki/creature_template_classic#MinLevelMana) | 5360 | (嗅探数据) |
| [MaxLevelMana](https://github.com/cmangos/issues/wiki/creature_template_classic#MaxLevelMana) | 5360 | (嗅探数据) |
| [UnitClass](https://github.com/cmangos/issues/wiki/creature_template_classic#UnitClass) | 8 | (嗅探数据) |
| [PowerMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#ManaMultiplier) | 2 | (嗅探数据) |

35 级 BaseMana: 2680
（来自 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) -- 根据嗅探数据和广泛研究计算出的基础法力值）

MinLevelMana = **四舍五入** (2680*2) = 5360 (5360)
MaxLevelMana = **四舍五入** (2680*2) = 5360 (5360)

**DamageMultiplier**

此字段是调整和设置 NPC 最小/最大伤害值的**主要**字段。

伤害计算公式

最小近战伤害 = (((Creature_Template_Classlevelstats.BaseDamageExp? * Creature_Template.DamageVariance) + (Creature_Template_Classlevelstats.BaseMeleeAttackPower / 14)) * (Creature_Template.BaseMeleeAttackTime / 1000)) * Creature_Template.Dmg_Multiplier

最大近战伤害 = ((((Creature_Template_Classlevelstats.BaseDamageExp? * Creature_Template.DamageVariance) * 1.5) + (Creature_Template_Classlevelstats.BaseMeleeAttackPower / 14)) * (Creature_Template.BaseMeleeAttackTime / 1000)) * Creature_Template.Dmg_Multiplier

一些 NPC 应用了伤害倍率来将其伤害提高到同等级普通 NPC 之上。

我相信人们会问... **为什么**除了简单的伤害倍率之外，还需要更多的东西来提升 NPC 伤害？这是唯一合乎逻辑的答案。对于一些 NPC（如首领），他们的倍率在 20 - 75 范围内，最小和最大伤害值可能会波动到**非常**大的范围。所以暴雪所做的是创建一个由 2 个值组成的系数系统，以帮助控制最大伤害值，因此如果你需要为 NPC 设置一个固定的最小/最大伤害，它可以缩放基础伤害，以便在通过公式计算后，最小和最大伤害值将在所需范围内。伤害方差用于降低最大伤害值。对于**没有**改变伤害方差的 NPC，使用的默认值是 1（正常方差 = 1）。

---

这里是一个 NPC 近战伤害计算的示例
---
Nexus-Prince Shaffar = 单位职业 2 (BOSS)
66 级: BaseDamage = 78.472 / 近战攻击强度 = 266 / 基础近战攻击时间 = 2000
怪物图鉴最小伤害: 1136
怪物图鉴最大伤害: 1593
伤害方差: 1.0 (无方差)
伤害倍率: 5.83 (计算值)

CalculatedMinMeleeDmg=**四舍五入** + (基础近战攻击强度 / 14)) * (基础攻击时间/1000)) * 伤害倍率
= ((((78.472 * 1.0) + (266/14)) * (2000/1000)) * 5.83
= (((78.472) + 19) * 2) = 194.944 * 5.83 = 1136.52352

CalculatedMaxMeleeDmg=**四舍五入** * 1.5) + (基础近战攻击强度 / 14)) * (基础攻击时间/1000)) * 伤害倍率
= ((((78.472 * 1.0) * 1.5) + (266/14)) * (2000/1000)) * 5.83
= (((117.708) + 19) * 2) = 273.416 * 5.83 = 1594.01528

怪物图鉴列出 Sneed 的伤害范围为 97 -- 129。他每 2 秒攻击一次（未经证实）。根据上面的公式 ...

97 = X * ((9.6823) + (70 / 14)) * (2000 / 1000)
129 = X * ((9.6823 * 1.5) + (70 / 14)) * (2000 / 1000)

注意：

可能会出现非常轻微的 1 或 2 点伤害舍入错误... 这是因为在计算中生成基础伤害值时进行了四舍五入。

**DamageVariance**

伤害方差是伤害计算中用于限制最小/最大伤害范围的系数。

默认值为 1（正常） ===> 参见 [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#DamageMultiplier) 获取更多信息。

**ArmorMultiplier**

此值是用于乘以 Creature_Template_Classlevelstats 中 BaseArmor 值的倍率值。

大多数普通 NPC = 1

**ExperienceMultiplier**

注意：此字段当前未被核心使用（未来实现）

**MinLevelHealth**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最低等级生命值现在使用 [HealthMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#HealthMultiplier) 计算。

核心现在自动实时计算此值。

**MaxLevelHealth**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最高等级生命值现在使用 [HealthMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#HealthMultiplier) 计算。

核心现在自动实时计算此值。

**MinLevelMana**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最低等级法力值现在使用 [PowerMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#PowerMultiplier) 计算。

核心现在自动实时计算此值。

**MaxLevelMana**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最高等级法力值现在使用 [PowerMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#PowerMultiplier) 计算。

核心现在自动实时计算此值。

**MinMeleeDmg**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最小近战伤害现在使用 [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#DamageMultiplier) 计算。

核心现在自动实时计算此值。

**MaxMeleeDmg**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最大近战伤害现在使用 [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#DamageMultiplier) 计算。

核心现在自动实时计算此值。

**MinRangedDmg**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最小远程伤害现在使用 [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#DamageMultiplier) 计算。

核心现在自动实时计算此值。

**MaxRangedDmg**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
（仍然是一个很好的字段）

最大远程伤害现在使用 [DamageMultiplier](https://github.com/cmangos/issues/wiki/creature_template_classic#DamageMultiplier) 计算。

核心现在自动实时计算此值。

**Armor**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
数据库开发人员：建议在此字段中应用 MaxLevel 的护甲值以供参考

（旧系统未正确计算不同 NPC 等级的护甲值）

核心现在自动实时计算此值。

**MeleeAttackPower**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
数据库开发人员：建议在此字段中应用 MaxLevel 的值以供参考

核心现在从 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) 获取值

（旧系统未正确计算伤害计算的值）

**RangedAttackPower**

注意：此字段不再被核心使用 -- 为数据库开发人员保留
数据库开发人员：建议在此字段中应用 MaxLevel 的值以供参考

核心现在从 [Creature_Template_ClassLevelStats](https://github.com/cmangos/issues/wiki/Creature_Template_ClassLevelStats) 获取值

（旧系统未正确计算伤害计算的值）

**MeleeBaseAttackTime**

NPC 的近战攻击时间，单位为毫秒。此字段由嗅探数据填充。

此字段用作最小/最大近战伤害公式计算的一部分。

**RangedBaseAttackTime**

NPC 的远程攻击时间，单位为毫秒。此字段由嗅探数据填充。

此字段用作最小/最大远程伤害公式计算的一部分。

**DamageSchool**

NPC 的近战伤害类型。所有近战伤害将作为此处设置的此法术学派伤害完成。

注意：0（正常）= 物理伤害

| ID | 名称 |
| :--- | :--- |
| 0 | SPELL_SCHOOL_NORMAL (物理) |
| 1 | SPELL_SCHOOL_HOLY (神圣) |
| 2 | SPELL_SCHOOL_FIRE (火焰) |
| 3 | SPELL_SCHOOL_NATURE (自然) |
| 4 | SPELL_SCHOOL_FROST (冰霜) |
| 5 | SPELL_SCHOOL_SHADOW (暗影) |
| 6 | SPELL_SCHOOL_ARCANE (奥术) |

**MinLootGold**

NPC 被杀死时掉落的最小可能金钱，单位为铜币。

NPC 将掉落介于 MinLootGold 和 MaxLootGold 之间的随机值。

注意：
1 = 1 铜币
100 = 1 银币
10000 = 1 金币

**MaxLootGold**

NPC 被杀死时掉落的最大可能金钱，单位为铜币。

NPC 将掉落介于 MinLootGold 和 MaxLootGold 之间的随机值。

注意：
1 = 1 铜币
100 = 1 银币
10000 = 1 金币

**LootId**

此 NPC 用于生成战利品的战利品模板的 ID。
参见 [creature_loot_template.entry](https://github.com/cmangos/issues/wiki/creature_loot_template#entry)

**PickpocketLootId**

此 NPC 应用于生成偷窃战利品的偷窃战利品模板的 ID。
参见 [pickpocketing_loot_template.entry](https://github.com/cmangos/issues/wiki/pickpocketing_loot_template#entry)

**SkinningLootId**

此 NPC 应用于生成剥皮战利品的剥皮战利品模板的 ID。
参见 [skinning_loot_template.entry](https://github.com/cmangos/issues/wiki/skinning_loot_template#entry)

CreatureTypeFlags 可以定义拾取生物所需的专业。

| 类型 | 信息 |
| :--- | :--- |
| CREATURE_TYPEFLAGS_HERBLOOT | 使怪物尸体可采药 -- 使用剥皮战利品字段 |
| CREATURE_TYPEFLAGS_MININGLOOT | 使怪物尸体可采矿 -- 使用剥皮战利品字段 |
| CREATURE_TYPEFLAGS_ENGINEERLOOT | 使怪物尸体可工程学拆卸 -- 使用剥皮战利品字段 |

对于这些其他类型，也使用 Skinning_Loot_Template 来生成这些其他专业的战利品。

**KillCredit1**

在 NPC 死亡时分配任务击杀计数的额外生物模板编号。
注意：某些任务需要额外的任务击杀计数。

**KillCredit2**

在 NPC 死亡时分配任务击杀计数的额外生物模板编号。
注意：某些任务需要额外的任务击杀计数。

**MechanicImmuneMask**

这使得 NPC 对特定的法术机制免疫。参见 Spell.dbc 中第 effect_X_mechanic_id 行。

使用来自 SpellMechanic.dbc 的引用。

| 位 | 类型 | 位 | 类型 |
| :--- | :--- | :--- | :--- |
| 1 | MECHANIC_CHARM (魅惑) | 32768 | MECHANIC_BANDAGE (绷带) |
| 2 | MECHANIC_CONFUSED (迷惑) | 65536 | MECHANIC_POLYMORPH (变形) |
| 4 | MECHANIC_DISARM (缴械) | 131072 | MECHANIC_BANISH (放逐) |
| 8 | MECHANIC_DISTRACT (扰乱) | 262144 | MECHANIC_SHIELD (护盾) |
| 16 | MECHANIC_FEAR (恐惧) | 524288 | MECHANIC_SHACKLE (禁锢) |
| 32 | MECHANIC_FUMBLE (失手) | 1048576 | MECHANIC_MOUNT (乘骑) |
| 64 | MECHANIC_ROOT (定身) | 2097152 | MECHANIC_PERSUADE (说服) |
| 128 | MECHANIC_PACIFY (安抚) | 4194304 | MECHANIC_TURN (转身) |
| 256 | MECHANIC_SILENCE (沉默) | 8388608 | MECHANIC_HORROR (恐慌) |
| 512 | MECHANIC_SLEEP (睡眠) | 16777216 | MECHANIC_INVULNERABILITY (无敌) |
| 1024 | MECHANIC_SNARE (诱捕) | 33554432 | MECHANIC_INTERRUPT (打断) |
| 2048 | MECHANIC_STUN (昏迷) | 67108864 | MECHANIC_DAZE (眩晕) |
| 4096 | MECHANIC_FREEZE (冻结) | 134217728 | MECHANIC_DISCOVERY (发现) |
| 8192 | MECHANIC_KNOCKOUT (击倒) | 268435456 | MECHANIC_IMMUNE_SHIELD (免疫护盾) |
| 16384 | MECHANIC_BLEED (流血) | 536870912 | MECHANIC_SAPPED (被闷棍) |

要组合免疫，只需相加数值。免疫所有对应值 1073741823。

**SchoolImmuneMask**

这使得 NPC 对特定的法术学派免疫。

| 类型 | 位掩码 |
| :--- | :--- |
| SPELL_SCHOOL_NORMAL (物理) | 1 |
| SPELL_SCHOOL_HOLY (神圣) | 2 |
| SPELL_SCHOOL_FIRE (火焰) | 4 |
| SPELL_SCHOOL_NATURE (自然) | 8 |
| SPELL_SCHOOL_FROST (冰霜) | 16 |
| SPELL_SCHOOL_SHADOW (暗影) | 32 |
| SPELL_SCHOOL_ARCANE (奥术) | 64 |

要组合法术学派免疫，只需相加数值。免疫所有对应值 127。

**ResistanceHoly**

NPC 的额外神圣法术抗性值。

**ResistanceFire**

NPC 的额外火焰法术抗性值。

**ResistanceNature**

NPC 的额外自然法术抗性值。

**ResistanceFrost**

NPC 的额外冰霜法术抗性值。

**ResistanceShadow**

NPC 的额外暗影法术抗性值。

**ResistanceArcane**

NPC 的额外奥术法术抗性值。

**PetSpellDataId**

在客户端显示宠物拥有哪些法术的 ID。

注意：此值来自 DBC（未确认）

**MovementType**

NPC 的默认移动类型。

| ID | 名称 | 类型 |
| :--- | :--- | :--- |
| 0 | IDLE_MOTION_TYPE | 空闲 -- 站立不动（固定） |
| 1 | RANDOM_MOTION_TYPE | 随机移动 -- 在生成距离半径内随机移动 |
| 2 | WAYPOINT_MOTION_TYPE | 路径点移动 -- 沿着定义的路径点路径移动 |
| 3 | PATH_MOTION_TYPE | 循环样条 |
| 4 | LINEAR_WP_MOTION_TYPE | 移动点 1,2,3,2,1 |

**TrainerType**

如果 NPC 是训练师（设置了训练师 NPCFlag），则此字段控制 NPC 是哪种训练师。

注意：必须同时填写此字段和相关字段，训练师才能正常工作。

| ID | 类型 | 相关字段 | 注释 |
| :--- | :--- | :--- | :--- |
| 0 | TRAINER_TYPE_CLASS | trainer_class | 训练职业法术 |
| 1 | TRAINER_TYPE_MOUNTS | trainer_race | 训练骑术技能 |
| 2 | TRAINER_TYPE_TRADESKILLS | trainer_spell | 训练专业技能 |
| 3 | TRAINER_TYPE_PETS | trainer_class | 训练宠物技能 |

**TrainerSpell**

如果 NPC 是教授专业技能的训练师（[trainer_type](https://github.com/cmangos/issues/wiki/creature_template#trainer_type) == 2），则玩家必须已经知道此处指定的法术 ID 才能与此 NPC 交谈。

**TrainerClass**

如果 NPC 是职业训练师或宠物训练师（[trainer_type](https://github.com/cmangos/issues/wiki/creature_template#trainer_type) == 0 或 3），则玩家的职业必须与此处指定的值相同才能与此训练师交谈。对于宠物训练师，此值必须为 3（猎人）。
参见 [character.class](https://github.com/cmangos/issues/wiki/character#class)

**TrainerRace**

如果 NPC 是坐骑训练师（[trainer_type](https://github.com/cmangos/issues/wiki/creature_template#trainer_type) == 1），则玩家的种族必须与此处指定的值相同才能与此训练师交谈。
参见 [character.race](https://github.com/cmangos/issues/wiki/character#race)

**TrainerTemplateId**

此 id 指的是 [npc_trainer_template](https://github.com/cmangos/issues/wiki/npc_trainer_template)。

**VendorTemplateId**

此 id 指的是 [npc_vendor_template](https://github.com/cmangos/issues/wiki/npc_vendor_template)。

**EquipmentTemplateId**

此生物应显示的默认装备的 ID。
参见 [creature_equip_template.entry](https://github.com/cmangos/issues/wiki/creature_equip_template#entry)

**GossipMenuId**

对 [gossip_menu_id](https://github.com/cmangos/issues/wiki/gossip_menu) 的引用。

**visibilityDistanceType**

| 位 | 名称 | 描述 |
| :--- | :--- | :--- |
| 0 | DEFAULT_VISIBILITY_DISTANCE | 默认配置设置：100 码 |
| 1 | VISIBILITY_DISTANCE_TINY | 25 码 |
| 2 | VISIBILITY_DISTANCE_SMALL | 50 码 |
| 3 | VISIBILITY_DISTANCE_LARGE | 200 码 |
| 4 | VISIBILITY_DISTANCE_GIGANTIC | 400 码 |
| 5 | MAX_VISIBILITY_DISTANCE | 533.33333 码 |

**CorpseDecay**

尸体消失前的时间，单位为秒。

**SpellList**

[creature_spell_list](https://github.com/cmangos/issues/wiki/creature_spell_list)

**Civilian**

用于定义荣誉/非荣誉击杀。

| ID | 注释 |
| :--- | :--- |
| 0 | 正常 |
| 1 | 平民 |

**AIName**

覆盖用于生物的 AI。

| 名称 | 描述 |
| :--- | :--- |
| NullAI | 空 AI，生物什么都不做。 |
| GuardAI | 城市守卫。 |
| PetAI | 生物是宠物。 |
| TotemAI | 生物从 spell1 字段施放法术，否则像 NullAI。 |
| EventAI | 生物使用 creature_ai_scripts (ACID)。 |
| GuardianAI | 生物是守护者（追随者） |
| PossessedAI | 被精神控制 |

**ScriptName**

此生物使用的 SD2 脚本名称（如果有）。这将脚本引擎中的脚本与此生物联系起来。