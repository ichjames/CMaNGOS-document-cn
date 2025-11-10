condition

 

通过此表和新条件，可以创建树状且非常复杂的组合条件（例如 拥有光环 && (拥有物品 || 拥有任务)）

用于：

- [DBScript](https://github.com/cmangos/issues/wiki/DBScripts)

- [gossip_menu](https://github.com/cmangos/issues/wiki/gossip_menu)

- [gossip_menu_option](https://github.com/cmangos/issues/wiki/gossip_menu_option)

- [npc_spellclick_spells](https://github.com/cmangos/issues/wiki/npc_spellclick_spells)

- [spell_area](https://github.com/cmangos/issues/wiki/spell_area)

**`conditions` 表**

**结构**

| **字段**                                                                       | **类型**         | **属性**   | **键** | **Null** | **默认值** |
| ------------------------------------------------------------------------------ | ---------------- | ---------- | ------ | -------- | ---------- |
| [condition_entry](https://github.com/cmangos/issues/wiki/Conditions#condition_entry) | mediumint(8) unsigned |            | 主键   | 是       | NULL       |
| [type](https://github.com/cmangos/issues/wiki/Conditions#type)                 | tinyint(3) signed |            |        | 否       | 0          |
| [value1](https://github.com/cmangos/issues/wiki/Conditions#value1)             | mediumint(8) unsigned |            |        | 否       | 0          |
| [value2](https://github.com/cmangos/issues/wiki/Conditions#value2)             | mediumint(8) unsigned |            |        | 否       | 0          |
| [value3](https://github.com/cmangos/issues/wiki/Conditions#value3)             | mediumint(8) unsigned |            |        | 否       | 0          |
| [value4](https://github.com/cmangos/issues/wiki/Conditions#value4)             | mediumint(8) unsigned |            |        | 否       | 0          |
| [flags](https://github.com/cmangos/issues/wiki/Conditions#flags)               | tinyint(3) unsigned |            |        | 否       | 0          |

**字段描述**

**condition_entry**

标识符\
为避免资料片之间的冲突，请使用：

| 版本       | **范围**        |
| ---------- | --------------- |
| 经典旧世： | **0 -- 9999**   |
| 燃烧的远征： | **10000 -- 19999** |
| 巫妖王之怒： | **20000 +**     |

**type**

条件的类型

**value1**

条件的第一个数据字段

**value2**

条件的第二个数据字段

**value3**

条件的第三个数据字段

**value4**

条件的第四个数据字段

**flags**

修改条件的标志，用于评估类型，例如反转结果或交换目标和来源。

| **十进制** | **十六进制** | **类型**                    | **描述**                             |
| ---------- | ------------ | --------------------------- | ------------------------------------ |
| 0          | 0×00         | 默认                        | 无效果                               |
| 1          | 0×01         | 条件标志_反转结果           | 反转条件的评估，例如要求拥有物品/光环而不是缺失它（并非所有条件都支持） |
| 2          | 0×02         | 条件标志_交换目标           | 在评估条件时交换来源和目标（并非所有条件都支持） |

标志可以累积。

**可能的条件类型**

这是[type](https://github.com/cmangos/issues/wiki/Conditions#type)中值的描述

| **类型值** | **条件**                    | **注释**                                     |
| ---------- | --------------------------- | -------------------------------------------- |
| -3         | 条件_非                     | 另一个condition_entry的组合的**非** *        |
| -2         | 条件_或                     | 2到4个其他condition_entry的**或**组合 *      |
| -1         | 条件_与                     | 2到4个其他condition_entry的**与**组合 *      |
| 0          | 条件_无                     | 无条件，始终返回真                           |
| 1          | 条件_光环                   | 目标必须拥有或缺失一个光环                   |
| 2          | 条件_物品                   | 玩家必须在背包中拥有或缺失一定数量的物品     |
| 3          | 条件_已装备物品             | 玩家必须装备了一件物品                       |
| 4          | 条件_区域ID                 | 玩家必须在特定区域/地带                      |
| 5          | 条件_声望等级_最小          | 玩家必须在特定阵营拥有至少某个声望等级       |
| 6          | 条件_阵营                   | 玩家必须属于指定阵营（联盟或部落）           |
| 7          | 条件_技能                   | 玩家必须拥有特定技能值                       |
| 8          | 条件_任务已奖励             | 玩家必须已完成某个任务                       |
| 9          | 条件_已接受任务             | 玩家必须在任务日志中有该任务且尚未完成       |
| 10         | 条件_银色黎明委任徽章光环   |                                              |
| 11         | 条件_PvP等级                | 玩家必须拥有荣誉等级（最低等级，最高等级）   |
| 12         | 条件_活跃游戏事件           | 事件必须活跃/非活跃                          |
| 13         | 条件_区域标志               |                                              |
| 14         | 条件_种族职业               | 具有特定种族或职业                           |
| 15         | 条件_等级                   | 具有特定等级                                 |
| 16         | 未使用                      | 已弃用，原为条件_无物品，被条件_物品 + 标志_反转结果替代 |
| 17         | 条件_法术                   | 知晓某个法术                                 |
| 18         | 条件_副本脚本               | 基于SD2的条件                                |
| 19         | 条件_任务可用               | 某个任务可用                                 |
| 20         | 条件_成就                   | 拥有或没有特定成就                           |
| 21         | 条件_成就_服务器            | 条件20的服务器范围版本                       |
| 22         | 条件_无任务                 | 尚未接受过某个任务                           |
| 23         | 条件_物品_含银行            | 检查背包或银行中是否存在所需数量的物品       |
| 24         | 未使用                      | 已弃用，原为条件_无物品_含银行，被条件_物品_含银行 + 标志_反转结果替代 |
| 25         | 未使用                      | 已弃用，原为条件_非活跃游戏事件，被条件_活跃游戏事件 + 标志_反转结果替代 |
| 26         | 条件_活跃假日               |                                              |
| 27         | 未使用                      | 已弃用，原为条件_非活跃假日，被条件_活跃假日 + 标志_反转结果替代 |
| 28         | 条件_可学习技能             | 检查玩家是否拥有足够高的技能等级，并可选择检查背包中是否有特定物品 |
| 29         | 条件_技能低于               |                                              |
| 30         | 条件_声望等级_最大          |                                              |
| 31         | 条件_已完成首领战           | 检查某个首领战是否已完成                     |
| 32         | 未使用                      | 已弃用，原为条件_来源光环，被条件_光环 + 标志_交换目标替代 |
| 33         | 条件_最后路径点             | 检查条件来源的路径点状态                     |
| 34         | 条件_经验获取者             | 检查玩家是否开启/关闭了经验获取              |
| 35         | 条件_性别                   | 检查玩家的性别                               |
| 36         | 条件_死亡或离开             |                                              |
| 37         | 条件_生物在范围内           |                                              |
| 38         | 条件_PvP脚本                |                                              |
| 39         | 条件_生成数量               | 返回地图上是否存在指定数量的生物条目         |
| 40         | 条件_世界脚本               | 检查给定世界状态的状态                       |
| 41         | 未使用                      | 已弃用，原为条件_性别_NPC，被条件_性别 + 标志_交换目标替代 |
| 42         | 条件_世界状态               | 检查地图中世界状态变量的值                   |

(*) 元条件类型 条件_与 (-1) 和 条件_或 (-2) 用法如下：value1 (作为condition_entry) **与**/**或** value2 (作为condition_entry) **与**/**或** value3 (作为condition_entry) **与**/**或** value4 (作为condition_entry)。通过这些元条件，可以创建树状且非常复杂的组合条件（例如 拥有光环 && (拥有物品 || 拥有任务)）

**可用条件类型的详细描述**

[value1](https://github.com/cmangos/issues/wiki/Conditions#value1)/[value2](https://github.com/cmangos/issues/wiki/Conditions#value2)/[value3](https://github.com/cmangos/issues/wiki/Conditions#value3)/[value4](https://github.com/cmangos/issues/wiki/Conditions#value4)中值的含义取决于条件的[类型](https://github.com/cmangos/issues/wiki/Possible-condition-types)

- 条件_非 (-3)
  - value1: condition_entry
  - 必须拥有比value1更高的condition_entry
  - 返回**非**条件（value1的条件）

- 条件_或 (-2)
  - value1: condition_entry
  - value2: condition_entry
  - value3: condition_entry (可选)
  - value4: condition_entry (可选)
  - 必须拥有比value1、value2、value3和value4更高的condition_entry
  - 返回条件（value1的条件）**或**条件（value2的条件）**或**条件（value3的条件）**或**条件（value4的条件）

- 条件_与 (-1)
  - value1: condition_entry
  - value2: condition_entry
  - value3: condition_entry (可选)
  - value4: condition_entry (可选)
  - 必须拥有比value1、value2、value3和value4更高的condition_entry
  - 返回条件（value1的条件）**与**条件（value2的条件）**与**条件（value3的条件）**与**条件（value4的条件）

- 条件_无 (0)
  - 无条件——始终满足

- 条件_光环 (1)
  - value1: 光环来源的法术ID
  - value2: 施加光环的法术效果索引（0、1或2）
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_反转结果 或 标志_交换目标
  - 返回目标是否拥有光环。如果 &标志_反转结果：返回目标是否没有光环。如果 &标志_交换目标：返回来源是否拥有光环（如果 &标志_反转结果则没有），评估来源而不是目标（通常来源是NPC，目标是玩家）

- 条件_物品 (2)
  - value1: 物品ID
  - value2: 数量
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_反转结果
  - 返回玩家背包中是否拥有数量个物品。如果 &标志_反转结果：返回玩家背包中是否没有数量个物品

- 条件_已装备物品 (3)
  - value1: 物品ID
  - 返回玩家是否装备了一件物品

- 条件_区域ID (4)
  - value1: 区域ID
  - value2: 0, 1 (0: 在（子）区域内, 1: 不在（子）区域内)
  - 返回玩家是否（或是否不，取决于value2）在某个区域/地带

- 条件_声望等级_最小 (5)
  - value1: 阵营ID
  - value2: 最低等级
  - 返回玩家在给定阵营是否拥有至少（>=）最低等级

| **ID** | **等级** |
| ------ | -------- |
| 0      | 仇恨     |
| 1      | 敌对     |
| 2      | 冷淡     |
| 3      | 中立     |
| 4      | 友好     |
| 5      | 尊敬     |
| 6      | 崇敬     |
| 7      | 崇拜     |

- 条件_阵营 (6)
  - value1: 玩家阵营（469——联盟，67——部落）
  - 返回玩家是否拥有value1的阵营

- 条件_技能 (7)
  - value1: 技能ID (SkillLine.dbc)
  - value2: 所需技能值
  - 返回玩家是否拥有该技能ID的值

- 条件_任务已奖励 (8)
  - value1: 任务ID
  - 返回玩家是否已获得任务奖励

- 条件_已接受任务 (9)
  - value1: 任务ID
  - value2:

| 值 | 描述                                     |
| -- | ---------------------------------------- |
| 0  | 如果任务已接受则返回真，无论是否完成     |
| 1  | 如果任务已接受但未完成则返回真           |
| 2  | 如果任务已接受并完成则返回真             |

- 条件_银色黎明委任徽章光环 (10)
  - 返回玩家是否有任何银色黎明委任徽章光环激活 (17670,23930,24198,29112,29113)

- 条件_活跃游戏事件 (12)
  - value1: [事件](https://github.com/cmangos/issues/wiki/game_event)
  - value2: 未使用
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_反转结果
  - 返回事件是否活跃。如果 &标志_反转结果：返回游戏事件是否不活跃

- 条件_区域标志 (13)
  - value1: 区域标志
  - value2: 不拥有的标志
  - 返回当前区域中是否存在区域标志（如果区域标志设置 != 0）**并且**当前区域中是否不存在不拥有的标志（如果不拥有的标志 != 0）

- 条件_种族职业 (14)
  - value1: 种族掩码
  - value2: 职业掩码
  - 返回玩家是否为该种族（如果种族掩码设置 != 0）**并且**玩家是否为该职业（如果职业掩码 != 0）

| **掩码** | **种族**   |
| -------- | ---------- |
| 1        | 人类       |
| 2        | 兽人       |
| 4        | 矮人       |
| 8        | 暗夜精灵   |
| 16       | 亡灵       |
| 32       | 牛头人     |
| 64       | 侏儒       |
| 128      | 巨魔       |
| 512      | 血精灵     |
| 1024     | 德莱尼     |

| **掩码** | **职业**     |
| -------- | ------------ |
| 1        | 战士         |
| 2        | 圣骑士       |
| 4        | 猎人         |
| 8        | 潜行者       |
| 16       | 牧师         |
| 32       | 死亡骑士     |
| 64       | 萨满祭司     |
| 128      | 法师         |
| 256      | 术士         |
| 1024     | 德鲁伊       |

- 条件_等级 (15)
  - value1: 等级
  - value2: 0: 等于, 1: 等于或高于, 2: 等于或低于
  - 返回玩家是否拥有/高于/低于该等级

- 条件_法术 (17)
  - value1: 法术ID
  - value2: 0: 拥有法术, 1: 没有法术
  - 返回玩家是否（没有）学习了一个法术

- 条件_副本脚本 (18)
  - value1: 副本条件ID (参见 InstanceData.h 枚举 InstanceConditionIDs)
  - 返回当前副本的副本脚本函数 CheckConditionCriteriaMeet 的结果（必须为此类副本实现）
  - 为了与副本脚本"通信"，预定义了一些副本条件ID，可以使用：
    - 用于困难模式掉落 (0 普通; 1,2... 困难,更困难... 模式)
      - 副本条件ID_普通模式 = 0,
      - 副本条件ID_困难模式 = 1,
      - 副本条件ID_困难模式2 = 2,
      - 副本条件ID_困难模式3 = 3,
      - 副本条件ID_困难模式4 = 4,
    - 检查副本正在为哪个阵营执行脚本
      - 副本条件ID_阵营_部落 = 67,
      - 副本条件ID_阵营_联盟 = 469,

- 条件_任务可用 (19)
  - value1: 任务ID
  - 返回玩家是否可以开始一个任务（即接受任务的所有要求，如前置任务，是否满足）

- 条件_成就 (20)
  - value1: 成就ID
  - value2: 0: 拥有成就, 1: 没有成就
  - 返回玩家是否（没有）获得了一个成就

- 条件_成就_服务器 (21)
  - value1: 成就ID
  - value2: 0: 拥有成就, 1: 没有成就
  - 返回服务器上是否有任何玩家（没有）获得了一个成就

- 条件_无任务 (22)
  - value1: 任务ID
  - 返回玩家是否既未接受也从未完成过一个任务

- 条件_物品_含银行 (23)
  - value1: 物品ID
  - value2: 数量
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_反转结果
  - 返回玩家是否拥有至少数量的物品（包括银行中存放的物品）。如果 &标志_反转结果：返回玩家是否拥有少于数量的物品（包括银行中存放的物品）

- 条件_活跃假日 (26)
  - value1: 假日ID
  - value2: 未使用
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_反转结果
  - 返回假日是否活跃。如果 &标志_反转结果：返回假日是否不活跃

- 条件_可学习技能 (28)
  - value1: 法术ID
  - value2: 0 或 物品ID
  - 返回玩家是否可以学习技能（使用 SkillLineAbility 中的最低技能值）
  - 可以额外定义物品ID，以检查玩家在背包或银行中是否有一个（1）该物品
  - 当玩家拥有该法术或拥有该物品（如果已定义）时，条件返回假

- 条件_技能低于 (29)
  - value1: 技能ID
  - value2: 技能值
  - 返回玩家是否拥有技能skill_id且技能小于（且不等于）skill_value（对于skill_value > 1）
  - 如果skill_value == 1，那么如果玩家没有技能skill_id则返回真

- 条件_声望等级_最大 (30)
  - value1: 阵营ID
  - value2: 最高等级
  - 返回玩家在某个阵营的声望是否至多（<=）为最高等级

| **ID** | **等级** |
| ------ | -------- |
| 0      | 仇恨     |
| 1      | 敌对     |
| 2      | 冷淡     |
| 3      | 中立     |
| 4      | 友好     |
| 5      | 尊敬     |
| 6      | 崇敬     |
| 7      | 崇拜     |

- 条件_已完成首领战 (31)
  - value1: 首领战ID (DungeonEncounter(dbc).id)
  - value2: 首领战ID2 (DungeonEncounter(dbc).id)
  - 返回首领战ID是否完成（如果提供了首领战ID2，则将返回首领战ID已完成**或**首领战ID2已完成）

- 条件_最后路径点 (33)
  - value1: 路径点ID
  - value2: 0 = 精确, 1: 路径点 <= 路径点ID, 2: 路径点 > 路径点ID
  - 返回条件的来源是否在/已经到达/已经经过某个路径点

- 条件_经验获取者 (34)
  - value1: 0, 1 (0: 经验关闭, 1: 经验开启)
  - 返回玩家是否关闭/开启了他的经验获取

- 条件_性别 (35)
  - value1: 0=男性, 1=女性, 2=无 (参见枚举 Gender)
  - value2: 未使用
  - value3: 未使用
  - value4: 未使用
  - flags: 标志_交换目标
  - 返回玩家是男性还是女性（无性别不会发生）。如果 &标志_交换目标：如果来源NPC模型的性别等于value1则返回真。模型性别在creature_model_info.gender中定义

- 条件_死亡或离开 (36)
  - value1: 0=玩家死亡, 1=玩家死亡（队伍死亡）, 2=副本中的玩家死亡, 3=生物死亡
  - value2: 可选范围
  - 返回玩家/玩家的队伍/副本中的所有玩家/或生物是否死亡或离开了地图
  - 如果提供了可选范围，则如果玩家[们]超出范围，条件也会失败

- 条件_生物在范围内 (37)
  - value1: 生物条目
  - value2: 范围
  - 返回在给定范围内是否找到给定条目的生物

- 条件_PvP脚本 (38)
  - value1: 户外PvP脚本的区域ID
  - value2: 户外PvP条件ID (在实际脚本中定义)
  - 返回户外PvP脚本函数 IsConditionFulfilled 的结果（必须为所需的脚本实现）

- 条件_生成数量 (39)
  - value1: [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry)
  - value2: 地图上存在指定生物的最小数量，条件返回真
  - 如果地图上的生物数量大于或等于指定数量，则条件返回真
  - 注意：value1中指定的生物必须具有额外标志 CREATURE_EXTRA_FLAG_COUNT_SPAWNS！

- 条件_世界脚本 (40)
  - value1: 来自 WorldState.h 枚举 Conditions 的传送器世界状态
  - value2: 来自 WorldState.cpp 枚举的事件状态值
  - 如果给定传送器的世界状态等于预期的事件状态，则条件返回真

- 条件_世界状态 (42)
  - value1: 世界状态变量ID——必须已定义worldstate_name表条目——另请参见src/Game/World/WorldStateDefines.h获取官方变量
  - value2: 操作符号，来自 src/Game/Globals/Conditions.h 中的枚举 WorldStateConditionSign
  - value3: 其他操作数
  - 如果给定地图的世界状态变量操作为真，则条件返回真
  - 示例：10000; =; 0 ——当10000为零时为真