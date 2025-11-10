**表 \`dbscripts_on_xxx\`**

这些表的手动参考位于 [doc/script_commands.txt](https://github.com/cmangos/mangos-wotlk/blob/master/doc/script_commands.txt) 文件。

此表格式用于不同的表，以控制由不同动作激活的可能脚本：

- **dbscripts_on_quest_start:**\
  保存玩家接受任务时激活的脚本。\
  来源：任务给予者（生物）；目标：玩家；脚本执行按来源唯一。\
  ID 使用方式如下：任务编号

------------------------------------------------------------------------

- **dbscripts_on_quest_end:**\
  保存玩家完成任务时激活的脚本。\
  来源：任务交付者（生物）；目标：玩家；脚本执行按来源唯一。\
  ID 使用方式如下：任务编号

------------------------------------------------------------------------

- **dbscripts_on_creature_movement:**\
  保存 NPC 移动时激活的脚本。\
  来源：移动的生物；目标：移动的生物。\
  ID 使用方式如下：生物编号 * 100 + (1 -- 99)

------------------------------------------------------------------------

- **dbscripts_on_creature_death:**\
  保存生物死亡时激活的脚本。\
  来源：被杀的生物；目标：负责的杀手（单位或玩家）。\
  ID 使用方式如下：生物编号

------------------------------------------------------------------------

- **dbscripts_on_gossip:**\
  保存在 gossip_menu_option 或 gossip_menu 上激活的脚本。

  - 对于 gossip_menu -- 来源：玩家；目标： gossip 持有者（生物或游戏对象）；脚本执行按目标唯一。

  - 对于 gossip_menu_option 且 gossip 持有者是生物时 -- 来源：gossip 持有者（生物）；目标：玩家；脚本执行按来源唯一。

  - 对于 gossip_menu_option 且 gossip 持有者是游戏对象时 -- 来源：玩家；目标：gossip 持有者（游戏对象）；脚本执行按目标唯一。\
    ID 使用方式如下：gossip_menu / gossip_menu_option * 100 + (1-99)

------------------------------------------------------------------------

- **dbscripts_on_spell:**\
  保存可以由具有以下法术效果的法术激活的脚本：

  - SPELL_EFFECT_DUMMY (3) （法术效果_假人）

  - SPELL_EFFECT_TRIGGER_SPELL (64) （法术效果_触发法术）-- 仅适用于缺失的触发法术

  - SPELL_EFFECT_SCRIPT_EFFECT (77) （法术效果_脚本效果）\
    来源：施法者；目标：目标。\
    ID 使用方式如下：法术编号

------------------------------------------------------------------------

- **dbscripts_on_event:**\
  保存当事件被法术、游戏对象或飞行点激活时触发的脚本。\
  以下法术效果和游戏对象可以激活事件：

  - SPELL_EFFECT_SEND_EVENT (61) （法术效果_发送事件）

  - GAMEOBJECT_TYPE_CHEST (3) （游戏对象类型_箱子）

  - GAMEOBJECT_TYPE_GOOBER (10) （游戏对象类型_土灵对象）

  - GAMEOBJECT_TYPE_TRANSPORT (11) （游戏对象类型_运输工具）[尚未支持]

  - GAMEOBJECT_TYPE_CAMERA (13) （游戏对象类型_摄像机）

  - GAMEOBJECT_TYPE_MO_TRANSPORT (15) （游戏对象类型_移动运输工具）[部分支持]

  - GAMEOBJECT_TYPE_FLAGDROP (26) （游戏对象类型_掉落旗帜）[尚未支持]

  - GAMEOBJECT_TYPE_CAPTURE_POINT (29) （游戏对象类型_占领点）

  - GAMEOBJECT_TYPE_DESTRUCTIBLE_BUILDING (33) （游戏对象类型_可摧毁建筑）\
    来源、目标和脚本执行可能因事件激活来源而异。\
    ID 使用方式如下：EffectMiscValueA: 事件编号

------------------------------------------------------------------------

- **dbscripts_on_go_\[template\]_use:**\
  保存由游戏对象激活的可能脚本。\
  来源：对象使用者（单位）；目标：游戏对象。

  - dbscripts_on_go_template_use 可用于任何类型的游戏对象。

  - dbscripts_on_go_use 仅可用于 GAMEOBJECT_TYPE_DOOR (0) （门）和 GAMEOBJECT_TYPE_BUTTON (1) （按钮）\
    ID 使用方式如下：(gameobject.guid) / (gameobject_tempate.entry)，应尽可能使用 entry（编号）

------------------------------------------------------------------------

- **dbscript_random_templates**\
  保存可由 AI 或其他数据库脚本激活的脚本。\
  ID 使用方式如下：

  - 经典旧世: 0 -- 9999

  - 燃烧的远征: 10000 -- 19999

  - 巫妖王之怒: 20000 +\
    来源和目标由启动它的机制定义。

保存 **类型 = 0 时的 [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id)** 或保存 **类型 = 1 时的 dbscripts_on_relay.id**

------------------------------------------------------------------------

- **dbscripts_on_relay:**\
  保存可由 AI 或其他数据库脚本激活的脚本。\
  ID 使用方式如下：

  - 经典旧世: 0 -- 9999

  - 燃烧的远征: 10000 -- 19999

  - 巫妖王之怒: 20000 +\
    来源和目标由启动它的机制定义。

------------------------------------------------------------------------

- **其他启动数据库脚本的方式**

- 对于 creature_ai_scripts -- ACTION_T_TEXT_NEW.param3 用于启动 dbscript_random_templates.type = 0, [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id)

- 对于 creature_ai_scripts -- ACTION_T_START_RELAY_SCRIPT 用于启动 type = 2, dbscripts_on_relay

- 对于 SCRIPT_COMMAND_TALK 用于启动 dbscript_random_templates.type = 0, [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id)

- 对于 SCRIPT_COMMAND_START_RELAY_SCRIPT 用于启动 type = 2, dbscripts_on_relay

------------------------------------------------------------------------

**注意：**\
此表中的一条记录可能有多行，因为一个脚本可能执行不止一个动作。\
此外，脚本可能执行的每个动作都可以附加一个单独的[延迟](https://github.com/cmangos/issues/wiki/dbscripts#delay)。\
在这种情况下，核心将在正确的[延迟](https://github.com/cmangos/issues/wiki/dbscripts#delay)和[优先级](https://github.com/cmangos/issues/wiki/dbscripts#priority)后激活相应的动作。

**结构**

| 字段                                                                       | 类型                  | 允许空 | 键     | 默认值 | 额外                                                                        |
| -------------------------------------------------------------------------- | --------------------- | ------ | ------ | ------ | --------------------------------------------------------------------------- |
| [id](https://github.com/cmangos/issues/wiki/dbscripts#id)                  | int(8) unsigned       | NO     |        | 0      |                                                                             |
| [delay](https://github.com/cmangos/issues/wiki/dbscripts#delay)            | int(10) unsigned      | NO     |        | 0      |                                                                             |
| [priority](https://github.com/cmangos/issues/wiki/dbscripts#priority)      | int(11) unsigned      | NO     |        | 0      |                                                                             |
| [command](https://github.com/cmangos/issues/wiki/dbscripts#command)        | mediumint(8) unsigned | NO     |        | 0      |                                                                             |
| [datalong](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)   | int(10) unsigned      | NO     |        | 0      |                                                                             |
| [datalong2](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)  | int(10) unsigned      | NO     |        | 0      |                                                                             |
| [datalong3](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)  | int(11) unsigned      | NO     |        | 0      |                                                                             |
| [buddy_entry](https://github.com/cmangos/issues/wiki/dbscripts#buddy_entry)| int(10) unsigned      | NO     |        | 0      |                                                                             |
| [search_radius](https://github.com/cmangos/issues/wiki/dbscripts#search_radius)| int(10) unsigned   | NO     |        | 0      |                                                                             |
| [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)  | int(10) unsigned      | NO     |        | 0      |                                                                             |
| [dataint](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)    | int(11)               | NO     |        | 0      |                                                                             |
| [dataint2](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)   | int(11)               | NO     |        | 0      |                                                                             |
| [dataint3](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)   | int(11)               | NO     |        | 0      |                                                                             |
| [dataint4](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)   | int(11)               | NO     |        | 0      |                                                                             |
| [datafloat](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)  | float                 | NO     |        | 0      |                                                                             |
| [x](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)          | float                 | NO     |        | 0      |                                                                             |
| [y](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)          | float                 | NO     |        | 0      |                                                                             |
| [z](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)          | float                 | NO     |        | 0      |                                                                             |
| [o](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)          | float                 | NO     |        | 0      |                                                                             |
| [speed](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)      | float                 | NO     |        | 0      |                                                                             |
| [condition_id](https://github.com/cmangos/issues/wiki/dbscripts#condition_id)| mediumint(8) unsigned| NO     |        | 0      | [condition](https://github.com/cmangos/issues/wiki/Conditions#condition_entry) |
| [comments](https://github.com/cmangos/issues/wiki/dbscripts#otherfields)   | VARCHAR               | NO     |        | NULL   |                                                                             |

**字段描述**

**id**

对于 **dbscripts_on_creature_death**，它是生物的编号。参见 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry)。\
对于 **dbscripts_on_creature_movement**，它是路径点的[脚本编号](https://github.com/cmangos/issues/wiki/Creature_movement#script_id)。（生物编号 * 100 + (1 -- 99)）例如：编号 = 474 * 100 + (1-99) = 474101 -- 474199

- **正确** 的 ID 字段格式如下：生物编号 + 2 位脚本 ID（从 01 开始）。示例：生物 1234 有几个移动脚本，所以 1234+01 = 123401 ... 123402 ..等等

对于 **dbscripts_on_event**，它是事件编号。目前不存在完整的事件列表。在任何情况下，事件编号直接从游戏对象 WDB 数据或法术效果数据中获取。如果游戏对象和法术都激活同一个事件，则 ID 将匹配。\
对于 **dbscripts_on_go_template_use**，它是按钮/杠杆的编号。参见 [gameobject_template.entry](https://github.com/cmangos/issues/wiki/gameobject_template#entry)。\
对于 **dbscripts_on_go_use**，它是按钮/杠杆的 GUID。参见 [gameobject.guid](https://github.com/cmangos/issues/wiki/gameobject#guid)。\
对于 **dbscripts_on_gossip**，它是 gossip 选项的[动作脚本编号](https://github.com/cmangos/issues/wiki/Gossip_menu_option#action_script_id)。

- **正确** 的 ID 字段格式如下：GossipID + 2 位脚本 ID（从 01 开始）。示例：生物 1234 有几个 gossip 脚本，所以 1234+01 = 123401 ... 123402 ..等等

对于 **dbscripts_on_quest_end**，它是在任务模板定义中 [CompleteScript](https://github.com/cmangos/issues/wiki/quest_template#CompleteScript) 使用的 ID。\
对于 **dbscripts_on_quest_start**，它是在任务模板定义中 [StartScript](https://github.com/cmangos/issues/wiki/quest_template#StartScript) 使用的 ID。

对于 **dbscript_random_templates**，它是唯一 ID
- (经典旧世 0-9999, 燃烧的远征 10k-19999, 巫妖王之怒 20K+)

对于 **dbscripts_on_relay**，它是唯一 ID
- (经典旧世 0-9999, 燃烧的远征 10k-19999, 巫妖王之怒 20K+)

对于 **dbscripts_on_spell**，它是法术编号。参见 [spell_template.Id](https://github.com/cmangos/issues/wiki/spell_template#Id)

**delay**

当前脚本步骤激活前的延迟（毫秒）。0 表示立即。

注意：延迟对于具有相同 ID 的脚本是累积的。\
示例：脚本 1 有 5 秒（5000 毫秒）延迟，然后如果你希望脚本 2 在 3 秒（3000 毫秒）后触发，你将在序列中的脚本 2 使用延迟值 8000（5000+3000）。

**priority**

事件的优先级，如果延迟相同，数字越小优先级越高。用于调整同时发生的事件的执行顺序。

**condition_id**

决定是否执行此行的[条件](https://github.com/cmangos/issues/wiki/Conditions#condition_entry)。

**comments**

对所执行行的描述，"谁做了什么"。

**command**

在 [delay](https://github.com/cmangos/issues/wiki/dbscripts#delay) 毫秒过后，脚本执行的动作类型。此字段的值会影响需要设置哪些其他字段。

可以使用以下命令（枚举 ScriptCommand）：

| **命令** | **名称**                           | **描述**                                                     |
| -------- | ---------------------------------- | ------------------------------------------------------------ |
| 0        | SCRIPT_COMMAND_TALK                | 生物 说话/耳语/大喊/表情文字。                              |
| 1        | SCRIPT_COMMAND_EMOTE               | 在玩家/生物上播放表情。                                      |
| 2        | SCRIPT_COMMAND_FIELD_SET           | 更改玩家指定索引处的值。                                     |
| 3        | SCRIPT_COMMAND_MOVE_TO             | 将生物重新定位到目的地。                                     |
| 4        | SCRIPT_COMMAND_FLAG_SET            | 打开玩家指定索引处标志字段的位。                             |
| 5        | SCRIPT_COMMAND_FLAG_REMOVE         | 关闭玩家指定索引处标志字段的位。                             |
| 6        | SCRIPT_COMMAND_TELEPORT_TO         | 将玩家传送到一个位置。                                       |
| 7        | SCRIPT_COMMAND_QUEST_EXPLORED      | 满足任务的探索要求。                                         |
| 8        | SCRIPT_COMMAND_KILL_CREDIT         | 满足任务的击杀计数要求。                                     |
| 9        | SCRIPT_COMMAND_RESPAWN_GAMEOBJECT  | 生成一个已消失的游戏对象。                                   |
| 10       | SCRIPT_COMMAND_TEMP_SPAWN_CREATURE | 临时召唤一个生物。                                           |
| 11       | SCRIPT_COMMAND_OPEN_DOOR           | 打开一个门游戏对象（类型 == 0）。                            |
| 12       | SCRIPT_COMMAND_CLOSE_DOOR          | 关闭一个门游戏对象（类型 == 0）。                            |
| 13       | SCRIPT_COMMAND_ACTIVATE_OBJECT     | 激活（使用）一个游戏对象。                                   |
| 14       | SCRIPT_COMMAND_REMOVE_AURA         | 移除一个法术造成的光环。                                     |
| 15       | SCRIPT_COMMAND_CAST_SPELL          | 施放一个法术。                                               |
| 16       | SCRIPT_COMMAND_PLAY_SOUND          | 播放一个音效。                                               |
| 17       | SCRIPT_COMMAND_CREATE_ITEM         | 创建一个物品。                                               |
| 18       | SCRIPT_COMMAND_DESPAWN_SELF        | 在一段延迟后使一个生物消失。                                 |
| 19       | SCRIPT_COMMAND_PLAY_MOVIE          | 向目标玩家播放一部影片。                                     |
| 20       | SCRIPT_COMMAND_MOVEMENT            | 改变生物的移动类型（闲置、随机、路径点）。                   |
| 21       | SCRIPT_COMMAND_SET_ACTIVEOBJECT    | 将一个生物设置为活动对象。                                   |
| 22       | SCRIPT_COMMAND_SET_FACTION         | 改变生物的阵营。                                             |
| 23       | SCRIPT_COMMAND_MORPH_TO_ENTRY_OR_MODEL | 将一个生物变形为给定的模型。                             |
| 24       | SCRIPT_COMMAND_MOUNT_TO_ENTRY_OR_MODEL | 为生物装备坐骑或卸下坐骑（根据坐骑编号或模型）。         |
| 25       | SCRIPT_COMMAND_SET_RUN             | 使生物开始或停止奔跑。                                       |
| 26       | SCRIPT_COMMAND_ATTACK_START        | 使生物攻击半径内的目标。                                     |
| 27       | SCRIPT_COMMAND_GO_LOCK_STATE       | 更改游戏对象的锁定或交互标志。                               |
| 28       | SCRIPT_COMMAND_STAND_STATE         | 改变生物的站立状态。                                         |
| 29       | SCRIPT_COMMAND_MODIFY_NPC_FLAGS    | 改变生物的 NPC 标志。                                        |
| 30       | SCRIPT_COMMAND_SEND_TAXI_PATH      | 将玩家送上指定的飞行路径。                                   |
| 31       | SCRIPT_COMMAND_TERMINATE_SCRIPT    | 如果给定的生物编号满足条件，则停止脚本执行。                 |
| 32       | SCRIPT_COMMAND_PAUSE_WAYPOINTS     | 暂停或恢复路径点移动。                                       |
| 33       | SCRIPT_COMMAND_XP_USER             | 启用或禁用玩家的经验获取。 -- **仅巫妖王之怒**               |
| 34       | SCRIPT_COMMAND_TERMINATE_COND      | 当给定条件满足时停止脚本执行。                               |
| 35       | SCRIPT_COMMAND_SEND_AI_EVENT       | 向来源周围指定半径内的 EventAI 发送给定的 AI 事件。          |
| 36       | SCRIPT_COMMAND_SET_FACING          | 将结果来源转向结果目标。                                     |
| 37       | SCRIPT_COMMAND_MOVE_DYNAMIC        | 将结果来源移动到结果目标周围的随机点或移动到结果目标。       |
| 38       | SCRIPT_COMMAND_SEND_MAIL           | 从结果来源向结果目标发送邮件、金钱。                         |
| 39       | SCRIPT_COMMAND_SET_HOVER           | 使生物开始或停止飞行（悬停）。                               |
| 40       | SCRIPT_COMMAND_DESPAWN_GO          | 使一个游戏对象消失。                                         |
| 41       | SCRIPT_COMMAND_RESPAWN             | 重生一个生物。                                               |
| 42       | SCRIPT_COMMAND_SET_EQUIPMENT_SLOTS | 更改结果来源的装备槽。                                       |
| 43       | SCRIPT_COMMAND_RESET_GO            | 重置一个游戏对象。                                           |
| 44       | SCRIPT_COMMAND_UPDATE_TEMPLATE     | 更新生物编号。                                               |
| 45       | SCRIPT_COMMAND_START_RELAY_SCRIPT  | 启动中继脚本或中继模板。                                     |
| 46       | SCRIPT_COMMAND_CAST_CUSTOM_SPELL   | 结果来源 = 单位，对结果目标 = 单位施放法术                   |
| 47       | SCRIPT_COMMAND_INTERRUPT_SPELL     | 结果来源 = 单位，中断特定槽位的法术                          |
| 48       | SCRIPT_COMMAND_MODIFY_UNIT_FLAGS   | 改变生物的单位标志。                                         |
| 49       | SCRIPT_COMMAND_SET_DATA_64         | 设置实例数据（如果存在）-- datalong -- 参数1 datalong2 -- 参数2 |
| 50       | SCRIPT_COMMAND_ZONE_PULSE          | 脉冲区域进入战斗并攻击最近的敌人                             |
| 52       | SCRIPT_COMMAND_SET_GOSSIP_MENU     | 更改生物的默认 gossip 菜单编号。                             |
| 53       | SCRIPT_COMMAND_SET_WORLDSTATE      | 将世界状态变量更改为特定值。                                 |
| 54       | SCRIPT_COMMAND_SET_SHEATHE         | 更改生物的（sheatheState）（b2_0_sheath, UNIT_FIELD_BYTES_2,0） |
| 55       | SCRIPT_COMMAND_SET_STRING_ID       | 为世界对象设置或取消 string_id                               |

**buddy_entry**

除了需要玩家（如 KILL_CREDIT）的命令外，其他命令都支持伙伴概念。

这意味着如果提供了 buddy_entry 的编号，除了上面列出的来源和目标之外，还可以使用一个"伙伴"。

三者（originalSource, originalTarget, buddy）中的哪一个将在 [command](https://github.com/cmangos/issues/wiki/dbscripts#command) 中被使用，取决于 [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)（枚举 ScriptInfoDataFlags）。请注意，某些命令（如 EMOTE）仅对结果来源执行动作。

当使用 SCRIPT_FLAG_BUDDY_BY_STRING_ID 时 -- buddy_entry 是 [StringId](https://github.com/cmangos/issues/wiki/string_id#id) -- 优先于池、生成组、编号和 GUID 定位，并在设置时启用法术生成和脚本定位。

[data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) \|SCRIPT_FLAG_BUDDY_AS_TARGET 0×01\|SCRIPT_FLAG_REVERSE_DIRECTION 0×02\|SCRIPT_FLAG_SOURCE_TARGETS_SELF 0×04\| 的可能组合：

其中 "A → B" 表示 [command](https://github.com/cmangos/issues/wiki/dbscripts#command) 从 A 执行，以 B 为目标。

| 值 | A → B                      | 注释                                                         |
| -- | -------------------------- | ------------------------------------------------------------ |
| 0  | originalSource / buddyIfProvided → originalTarget | 默认                                                         |
| 1  | originalSource → buddy     | SCRIPT_FLAG_BUDDY_AS_TARGET                                  |
| 2  | originalTarget → originalSource / buddyIfProvided | SCRIPT_FLAG_REVERSE_DIRECTION                                |
| 3  | buddy → originalSource     | SCRIPT_FLAG_BUDDY_AS_TARGET + SCRIPT_FLAG_REVERSE_DIRECTION  |
| 4  | originalSource / buddyIfProvided → originalSource / buddyIfProvided | SCRIPT_FLAG_SOURCE_TARGETS_SELF                              |
| 5  | originalSource → originalSource | SCRIPT_FLAG_BUDDY_AS_TARGET + SCRIPT_FLAG_SOURCE_TARGETS_SELF |
| 6  | originalTarget → originalTarget | SCRIPT_FLAG_REVERSE_DIRECTION + SCRIPT_FLAG_SOURCE_TARGETS_SELF |
| 7  | buddy → buddy              | SCRIPT_FLAG_BUDDY_AS_TARGET + SCRIPT_FLAG_REVERSE_DIRECTION + SCRIPT_FLAG_SOURCE_TARGETS_SELF |

**search_radius**

执行数据库脚本的实体将在此半径范围内搜索 [buddy_entry](https://github.com/cmangos/issues/wiki/dbscripts#buddy_entry) 中定义的伙伴。

| & data_flags                      | 描述                                                                           |
| --------------------------------- | ------------------------------------------------------------------------------ |
| & SCRIPT_FLAG_BUDDY_BY_GUID       | 使用 [creature.guid](https://github.com/cmangos/issues/wiki/creature#guid) 而不是 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry) |
| & SCRIPT_FLAG_BUDDY_IS_DESPAWNED  | 死亡或已消失的 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry) |
| & SCRIPT_FLAG_BUDDY_BY_POOL       | 使用 [pool_creature.pool_entry](https://github.com/cmangos/issues/wiki/pool_creature#pool_entry) 而不是 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry) |
| & SCRIPT_FLAG_BUDDY_BY_SPAWN_GROUP| 伙伴是 [spawn_group](https://github.com/cmangos/issues/wiki/spawn_group) 的一部分 |
| & SCRIPT_FLAG_BUDDY_BY_GO         | 使用 [gameobject_template.entry](https://github.com/cmangos/issues/wiki/gameobject_template#entry) 而不是 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry) |

**data_flags**

定义在 "enum ScriptInfoDataFlags" 中

| 十进制 | 十六进制 | 类型                             | 描述                                                                                           |
| ------ | -------- | -------------------------------- | ---------------------------------------------------------------------------------------------- |
| 0      | 0×000    | DEFAULT                          | s/b → t                                                                                        |
| 1      | 0×001    | SCRIPT_FLAG_BUDDY_AS_TARGET      | s → b                                                                                          |
| 2      | 0×002    | SCRIPT_FLAG_REVERSE_DIRECTION    | t\* → s\* (\* 先前标志评估后的结果)                                                              |
| 4      | 0×004    | SCRIPT_FLAG_SOURCE_TARGETS_SELF  | s\* → s\* (\* 先前标志评估后的结果)                                                              |
| 8      | 0×008    | SCRIPT_FLAG_COMMAND_ADDITIONAL   | 仅对某些命令可能。                                                                             |
| 16     | 0×010    | SCRIPT_FLAG_BUDDY_BY_GUID        | 将 [search_radius](https://github.com/cmangos/issues/wiki/dbscripts#search_radius) 解释为 [buddy_entry](https://github.com/cmangos/issues/wiki/dbscripts#buddy_entry) GUID。 |
| 32     | 0×020    | SCRIPT_FLAG_BUDDY_IS_PET         | 不搜索 NPC，而是搜索宠物。                                                                     |
| 64     | 0×040    | SCRIPT_FLAG_BUDDY_IS_DESPAWNED   | 搜索已消失或死亡的生物。                                                                       |
| 128    | 0×080    | SCRIPT_FLAG_BUDDY_BY_POOL        | 伙伴应该是池的一部分                                                                           |
| 256    | 0×100    | SCRIPT_FLAG_BUDDY_BY_SPAWN_GROUP | 伙伴来自生成组                                                                                 |
| 512    | 0×200    | SCRIPT_FLAG_ALL_ELIGIBLE_BUDDIES | 多来源/多目标 -- 将为每个符合条件的伙伴执行                                                     |
| 1024   | 0×400    | SCRIPT_FLAG_BUDDY_BY_GO          | 通过游戏对象获取伙伴（对于可以同时以生物和游戏对象为目标的命令）                                 |
| 2048   | 0×800    | SCRIPT_FLAG_BUDDY_BY_STRING_ID   | 通过 [StringId](https://github.com/cmangos/issues/wiki/string_id#id) 定位实体（生物或游戏对象） |

**用法**

根据所使用的 [command](https://github.com/cmangos/issues/wiki/dbscripts#command)（枚举 ScriptCommand），字段的含义和用途可能有所不同：

- **SCRIPT_COMMAND_TALK = 0**

  - 文本的所有信息（类型、语言、关联音效、表情）都存储在 [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id) 表中。

  - datalong: [dbscript_random_templates.id](https://github.com/cmangos/issues/wiki/dbscript_random_templates#id) -- 将在给定模板中的所有 [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id) 之间随机选择。

  - dataint -- dataint4: 生物将说的文本 ID。参见 [broadcast_text.id](https://github.com/cmangos/issues/wiki/broadcast_text#id)。如果填充了不止一个 dataint 字段，文本将被随机使用。

- **SCRIPT_COMMAND_EMOTE = 1**

  - datalong: 要播放的[表情编号](https://github.com/cmangos/issues/wiki/Emote)。

  - dataint -- dataint4: 除了 datalong 之外，用于在 datalong + dataint -- dataint4 之间随机选择表情。

  - 结果来源必须是一个单位。

- **SCRIPT_COMMAND_FIELD_SET = 2** -- **已弃用** -- 例如使用 SCRIPT_COMMAND_MODIFY_UNIT_FLAGS

  - datalong: 字段的索引。

  - datalong2: 要放置在该索引处的值。

- **SCRIPT_COMMAND_MOVE_TO = 3**

  - datalong: dbscripts_on_relay id -- 为与此脚本相同的来源和目标执行。

  - datalong2: 移动的长度。计算方式为 travel_speed\*100。使用 0 表示生物默认移动。

  - datalong3: [枚举 ForcedMovement](https://github.com/cmangos/issues/wiki/dbscripts#ForcedMovement)

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 将把生物传送到给定位置。

  - x: 要移动到的 X 坐标。如果位置非常接近当前位置，或者 x=y=z=0，则只改变朝向。

  - y: 要移动到的 Y 坐标。

  - z: 要移动到的 Z 坐标。如果 x=y=0 且 z !=0，则只改变 Z 位置（新值将添加到当前 'z' 位置）。

  - o: 要面对的朝向。

  - 结果来源必须是一个生物。\
    *附注：如果位置非常接近当前位置，或者 x=y=z=0，则只改变朝向。*

- **SCRIPT_COMMAND_FLAG_SET = 4** -- **已弃用** -- 例如使用 SCRIPT_COMMAND_MODIFY_UNIT_FLAGS

  - datalong: 要设置的字段索引。

  - datalong2: 要设置的标志位。

| **类型**               | 经典旧世 | 燃烧的远征 | 巫妖王之怒 | 描述                     |
| ---------------------- | -------- | ---------- | ---------- | ------------------------ |
| UNIT_FIELD_HEALTH      | 22       | 22         | 24         | 生命值                   |
| UNIT_FIELD_POWER1      | 23       | 23         | 25         | 法力值                   |
| UNIT_FIELD_LEVEL       | 34       | 34         | 54         | 等级                     |
| UNIT_FIELD_FLAGS       |          |            |            | **SCRIPT_COMMAND_MODIFY_UNIT_FLAGS** |
| UNIT_FIELD_BOUNDINGRADIUS | 129    | 150        | 65         | 边界半径                 |
| UNIT_FIELD_COMBATREACH | 130      | 151        | 66         | 战斗触及范围             |
| UNIT_FIELD_BYTES_1     |          |            |            | **SCRIPT_COMMAND_STAND_STATE** |
| UNIT_DYNAMIC_FLAGS     | 143      | 164        | 79         | 动态标志                 |
| UNIT_NPC_FLAGS         |          |            |            | **SCRIPT_COMMAND_MODIFY_NPC_FLAGS** |

更多示例可以在核心的 UpdateFields.h 中找到。

- **SCRIPT_COMMAND_FLAG_REMOVE = 5** -- **已弃用** -- 例如使用 SCRIPT_COMMAND_MODIFY_UNIT_FLAGS

  - datalong: 要取消设置的字段索引。

  - datalong2: 要取消设置的标志位。

- **SCRIPT_COMMAND_TELEPORT_TO = 6**

  - datalong: 目标地图编号。参见 [Map.dbc](https://github.com/cmangos/issues/wiki/Map.dbc)。

  - x: 传送目标 x 坐标。

  - y: 传送目标 y 坐标。

  - z: 传送目标 z 坐标。

  - o: 传送目标朝向。

  - 来源或目标必须是玩家。

- **SCRIPT_COMMAND_QUEST_EXPLORED = 7**

  - datalong: 应满足其外部状态的[任务编号](https://github.com/cmangos/issues/wiki/quest_template#entry)。

  - datalong2: 玩家与 NPC/对象的最大距离，脚本仍会生效。

  - 来源或目标必须是玩家。

- **SCRIPT_COMMAND_KILL_CREDIT = 8**

  - datalong: 任务的击杀计数编号（quest_template.ReqCreatureOrGOId 中的编号）。如果设置为 0，则使用生物来源或目标。

  - datalong2: 可以是 0 = 个人计数 或 1 = 团队计数。

  - 来源或目标必须是玩家。

- **SCRIPT_COMMAND_RESPAWN_GAMEOBJECT = 9**

  - datalong: 要重生的游戏对象的 GUID。参见 [gameobject.guid](https://github.com/cmangos/issues/wiki/gameobject#guid)。对于伙伴可以跳过。

  - datalong2: 消失时间（秒）。如果值 < 5 秒，则使用 5 秒。

- **SCRIPT_COMMAND_TEMP_SPAWN_CREATURE = 10**

  - datalong: 召唤的生物的编号，来自 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry)。

  - datalong2: 消失延迟（毫秒）。如果设置为 0，则生物只在被杀死时消失。

  - datalong3: 你希望生物立即开始移动的[路径编号](https://github.com/cmangos/issues/wiki/creature_movement_template#pathId)（如果 MovementType=2）。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 将把生物召唤为活动对象。

  - dataint: 设置奔跑（布尔值）。0 = 关闭（默认），1 = 打开。

  - dataint4 = creature_spawn_data_template 编号 -- 允许自定义阵营、模型、装备等。

  - x: 召唤目标 x 坐标。

  - y: 召唤目标 y 坐标。

  - z: 召唤目标 z 坐标。

  - o: 召唤目标朝向。

- **SCRIPT_COMMAND_OPEN_DOOR = 11**

  - datalong: 被激活的门的 GUID。它是 [gameobject.guid](https://github.com/cmangos/issues/wiki/gameobject#guid)。如果提供了伙伴，可以跳过。

  - datalong2: 再次关闭门之前的延迟。如果值 < 15 秒，则使用 15 秒。

  - datalong3: 替代状态 -- 布尔值 0 或 1。

- **SCRIPT_COMMAND_CLOSE_DOOR = 12**

  - datalong: 被激活的门的 GUID。它是 [gameobject.guid](https://github.com/cmangos/issues/wiki/gameobject#guid)。如果提供了伙伴，可以跳过。

  - datalong2: 再次打开门之前的延迟。如果值 < 15 秒，则使用 15 秒。

- **SCRIPT_COMMAND_ACTIVATE_OBJECT = 13**

  - 来源必须是一个单位，目标必须是一个游戏对象。

  - datalong: 动画编号；用于 [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL。默认为 0。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 将发送游戏对象动画，而不是标准的游戏对象 Use() 函数。

- **SCRIPT_COMMAND_REMOVE_AURA = 14**

  - datalong: [法术编号](https://github.com/cmangos/issues/wiki/spell_template#Id)。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 将仅从来源移除目标单位的光环。\
    警告 -- 如果与引导法术一起使用，不会中断引导。

- **SCRIPT_COMMAND_CAST_SPELL = 15**

  - datalong: [法术编号](https://github.com/cmangos/issues/wiki/spell_template#Id)。

  - datalong2: [TriggerCastFlags](https://github.com/cmangos/issues/wiki/dbscripts#TriggerCastFlags)

  - buddy_entry: 目标的[编号](https://github.com/cmangos/issues/wiki/creature_template#entry)

  - search_radius: 搜索 [buddy_entry](https://github.com/cmangos/issues/wiki/dbscripts#buddy_entry) 或特定 GUID 的 [guid](https://github.com/cmangos/issues/wiki/creature#guid) 的半径，如果设置了 [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags|16)。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8): 不向法术施放传递目标。

  - dataint -- dataint4 可选。如果其中一些设置为法术编号，则会在 datalong + dataint -- dataint4 中随机施放一个法术。

**TriggerCastFlags**

| **位** | **名称**                             | **描述**                                                     |
| ------ | ------------------------------------ | ------------------------------------------------------------ |
| 0      | TRIGGERED_NONE                       | 非触发                                                       |
| 1      | TRIGGERED_OLD_TRIGGERED              | 旧版布尔支持 待办：尽可能限制使用。                          |
| 2      | TRIGGERED_IGNORE_HIT_CALCULATION     | 在 SpellHitResult 中忽略计算命中                             |
| 4      | TRIGGERED_IGNORE_UNSELECTABLE_FLAG   | 在 CheckTarget 中忽略 UNIT_FLAG_NOT_SELECTABLE               |
| 8      | TRIGGERED_INSTANT_CAST               | 将忽略法术条目中设置的任何施法时间                           |
| 16     | TRIGGERED_AUTOREPEAT                 | 将向法术系统发出信号，表明这是内部自动重复调用               |
| 32     | TRIGGERED_IGNORE_UNATTACKABLE_FLAG   | 在 CheckTarget 中忽略 UNIT_FLAG_NOT_ATTACKABLE               |
| 64     | TRIGGERED_DO_NOT_PROC                | 来自脚本的法术不应触发 -- 例如 DBScripts                     |
| 128    | TRIGGERED_PET_CAST                   | 应通过宠物操作码报告错误的法术                               |
| 256    | TRIGGERED_NORMAL_COMBAT_CAST         | AI 需要被告知目标的变化 待办：更改为 TRIGGERED_NONE          |

- **SCRIPT_COMMAND_PLAY_SOUND = 16**

  - datalong: [音效编号](https://github.com/cmangos/issues/wiki/SoundEntries.dbc#Content)。

  - datalong2: 位掩码：0/1=目标玩家，0/2=随距离衰减，0/4=全地图，0/8=全区域；1\|2 = 3 是目标且随距离衰减。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8): 播放音乐而不是音效。

  - 来源可以是任何对象。目标可以是任何玩家。

- **SCRIPT_COMMAND_CREATE_ITEM = 17**

  - datalong: [物品编号](https://github.com/cmangos/issues/wiki/item_template#Content)。

  - datalong2: 数量。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8): 从玩家处移除指定数量的该物品。

  - 来源或目标必须是玩家。

- **SCRIPT_COMMAND_DESPAWN_SELF = 18**

  - datalong: 消失延迟（毫秒）。

  - 结果来源必须是一个生物。

  - 使目标消失。

- **SCRIPT_COMMAND_PLAY_MOVIE = 19**

  - datalong: 向目标玩家播放一部[影片编号](https://github.com/cmangos/issues/wiki/Movie.dbc#Content)。

  - 目标必须是玩家。

- **SCRIPT_COMMAND_MOVEMENT = 20**

  - datalong: 改变生物的[移动类型](https://github.com/cmangos/issues/wiki/creature_template#MovementType)。可能的值：0 = 闲置，1 = 随机移动，2 = 路径点移动，3 = 循环样条移动（枚举 MovementGeneratorType）。

  - datalong2: 随机移动 (1) 的[生成距离](https://github.com/cmangos/issues/wiki/creature#spawndist) 或路径点移动 (2) 的 [creature_movement_template.pathId](https://github.com/cmangos/issues/wiki/creature_movement_template#pathId)。

  - datalong3: 计时器（毫秒）-- 与 MoveRandomAroundPoint 结合使用以触发使用 TimedWanderMovementGenerator。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 将在当前位置周围设置随机移动。

  - dataint: [枚举 ForcedMovement](https://github.com/cmangos/issues/wiki/dbscripts#ForcedMovement)

  - 结果来源必须是一个生物。

**ForcedMovement**

| **值** | **名称**             | **描述** |
| ------ | -------------------- | -------- |
| 0      | FORCED_MOVEMENT_NONE | 默认     |
| 1      | FORCED_MOVEMENT_WALK | 行走     |
| 2      | FORCED_MOVEMENT_RUN  | 奔跑     |
| 3      | FORCED_MOVEMENT_FLIGHT | 飞行   |

- **SCRIPT_COMMAND_SET_ACTIVEOBJECT = 21**

  - datalong: 0 = 关闭，1 = 打开。根据 datalong 值将一个生物设置为活动对象。

  - 结果来源必须是生物。

- **SCRIPT_COMMAND_SET_FACTION = 22**

  - datalong: [阵营编号](https://github.com/cmangos/issues/wiki/FactionTemplate.dbc)。如果设置为 0，将从 creature_template 恢复原始阵营。

  - 结果来源必须是一个生物。

  - datalong2: [枚举 TemporaryFactionFlags](https://github.com/cmangos/issues/wiki/dbscripts#TemporaryFactionFlags)

**TemporaryFactionFlags**

| 位 | 十六进制 | 描述                            | 备注                                                       |
| -- | -------- | ------------------------------- | ---------------------------------------------------------- |
| 0  | 0×00     | TEMPFACTION_NONE                | 当在临时阵营更改中未使用任何标志时，阵营将是持久的。一旦更改，将需要手动更改回默认/另一个阵营。 |
| 1  | 0×01     | TEMPFACTION_RESTORE_RESPAWN     | 在重生时恢复默认阵营。                                     |
| 2  | 0×02     | TEMPFACTION_RESTORE_COMBAT_STOP | 在 CombatStop() 时恢复（发生在生物死亡、脱离战斗或自定义脚本等情况下）。 |
| 4  | 0×04     | TEMPFACTION_RESTORE_REACH_HOME  | 在返回家园移动（脱离战斗）时到达家园时恢复，如果尚未在 CombatStop() 时完成。 |
| 8  | 0×08     | TEMPFACTION_TOGGLE_NON_ATTACKABLE | 当阵营更改时移除 UNIT_FLAG_NON_ATTACKABLE(0×02)（在临时阵营移除时重新应用）。 |
| 16 | 0×10     | TEMPFACTION_TOGGLE_IMMUNE_TO_PLAYER | 当阵营更改时移除 UNIT_FLAG_IMMUNE_TO_PLAYER(0×100)（在临时阵营移除时重新应用）。 |
| 32 | 0×20     | TEMPFACTION_TOGGLE_IMMUNE_TO_NPC | 当阵营更改时移除 UNIT_FLAG_IMMUNE_TO_NPC(0×200)（在临时阵营移除时重新应用）。 |
| 64 | 0×40     | TEMPFACTION_TOGGLE_PACIFIED     | 当阵营更改时移除 UNIT_FLAG_PACIFIED(0×20000)（在临时阵营移除时重新应用）。 |
| 128| 0×80     | TEMPFACTION_TOGGLE_NOT_SELECTABLE | 当阵营更改时移除 UNIT_FLAG_NOT_SELECTABLE(0×2000000)（在临时阵营移除时重新应用）。 |

- **SCRIPT_COMMAND_MORPH_TO_ENTRY_OR_MODEL = 23**

  - datalong: 生物[编号](https://github.com/cmangos/issues/wiki/creature_template#entry) 或[模型编号](https://github.com/cmangos/issues/wiki/creature_template#modelid)（取决于 [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)）。如果设置为 0，则生物将解除变形。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 以显式使用 datalong 值作为 model_id。

  - 结果来源必须是一个生物。

- **SCRIPT_COMMAND_MOUNT_TO_ENTRY_OR_MODEL = 24**

  - datalong: 生物[编号](https://github.com/cmangos/issues/wiki/creature_template#entry) 或[模型编号](https://github.com/cmangos/issues/wiki/creature_template#modelid)（取决于 [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)）。如果设置为 0，则生物将卸下坐骑。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 以显式使用 datalong 值作为 model_id。

  - 结果来源必须是生物。

- **SCRIPT_COMMAND_SET_RUN = 25**

  - datalong: 设置奔跑为 1 = 开启 或 0 = 关闭。

  - 结果来源必须是一个生物。

- **SCRIPT_COMMAND_ATTACK_START = 26**

  - 结果来源必须是一个生物，结果目标必须是一个单位。

- **SCRIPT_COMMAND_GO_LOCK_STATE = 27**

  - 结果来源必须是游戏对象。

  - datalong:

| 位 | 十六进制 | 名称                   |
| -- | -------- | ---------------------- |
| 1  | 0×01     | flag_go_lock           |
| 2  | 0×02     | flag_go_unlock         |
| 4  | 0×04     | flag_go_nonInteract    |
| 8  | 0×08     | flag_go_interact       |

- **SCRIPT_COMMAND_STAND_STATE = 28**

  - 结果来源必须是一个生物。

  - datalong: [枚举 UnitStandStateType](https://github.com/cmangos/issues/wiki/dbscripts#UnitStandStateType)

**UnitStandStateType**

| 位 | 名称                      | 注释                         |
| -- | ------------------------- | ---------------------------- |
| 0  | UNIT_STAND_STATE_STAND    | 正常行为                     |
| 1  | UNIT_STAND_STATE_SIT      | 坐在地上                     |
| 2  | UNIT_STAND_STATE_SIT_CHAIR | 坐在普通椅子上               |
| 3  | UNIT_STAND_STATE_SLEEP    | 睡眠                         |
| 4  | UNIT_STAND_STATE_SIT_LOW_CHAIR | 坐在矮椅子上           |
| 5  | UNIT_STAND_STATE_SIT_MEDIUM_CHAIR | 坐在中等椅子上     |
| 6  | UNIT_STAND_STATE_SIT_HIGH_CHAIR | 坐在高椅子上           |
| 7  | UNIT_STAND_STATE_DEAD     | 装死                         |
| 8  | UNIT_STAND_STATE_KNEEL    | 跪下                         |
| 9  | UNIT_STAND_STATE_CUSTOM   | 取决于模型动画。潜入、冻结、隐藏、冬眠、休息 |

- **SCRIPT_COMMAND_MODIFY_NPC_FLAGS = 29**

  - 结果来源必须是一个生物。

  - datalong: NPC 标志。

  - datalong2: 0 移除，1 添加。

- **SCRIPT_COMMAND_SEND_TAXI_PATH = 30**

  - datalong: [飞行路径编号](https://github.com/cmangos/issues/wiki/TaxiPath.dbc#Content)。

  - 来源或目标必须是玩家。

- **SCRIPT_COMMAND_TERMINATE_SCRIPT = 31**

  - datalong: 如果提供了[生物编号](https://github.com/cmangos/issues/wiki/creature_template#entry)。（或者如果是 SCRIPT_FLAG_BUDDY_BY_POOL 则为池 ID）

  - datalong2: 搜索距离。

  - datalong3: 池编号

  - dataint: 更改当前路径点移动类型的[等待时间](https://github.com/cmangos/issues/wiki/creature_movement#waittime)（毫秒）。负值将减少时间。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)

| & data_flags                            | 描述                                   |
| --------------------------------------- | -------------------------------------- |
| & SCRIPT_FLAG_COMMAND_ADDITIONAL 8 0×08 | 如果找到生物且存活，则终止脚本。       |
| ! SCRIPT_FLAG_COMMAND_ADDITIONAL        | 如果未找到生物或生物未存活，则终止脚本。 |

- 当与 GUID 或编号搜索一起使用时，也可以通过 SCRIPT_FLAG_BUDDY_BY_GO 搜索游戏对象 GUID。

- **SCRIPT_COMMAND_PAUSE_WAYPOINTS = 32**

  - datalong: 0 恢复路径点，1 暂停路径点。

  - 结果来源或目标必须是一个生物。

- **SCRIPT_COMMAND_XP_USER = 33** --- 仅巫妖王之怒

  - datalong: 设置经验获取为 1 = 开启 或 0 = 关闭。

  - 来源或目标必须是玩家。\
    *附注：仅在巫妖王之怒版本中可用。*

- **SCRIPT_COMMAND_TERMINATE_CONDITION = 34**

  - datalong: 要检查的[条件编号](https://github.com/cmangos/issues/wiki/conditions#condition_entry)。

  - datalong2: 要为玩家标记为失败的[任务编号](https://github.com/cmangos/issues/wiki/quest_template#entry)（如果提供）。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags)

| & data_flags                               | 描述                       |
| ------------------------------------------ | -------------------------- |
| & SCRIPT_FLAG_COMMAND_ADDITIONAL 8 0×08    | 当条件为 false 时终止。    |
| ! SCRIPT_FLAG_COMMAND_ADDITIONAL           | 当条件为 true 时终止。     |

- **SCRIPT_COMMAND_SEND_AI_EVENT = 35**

  - datalong: [AIEventType](https://github.com/cmangos/issues/wiki/dbscripts#AIEventType)。仅接受 EventAI 事件。支持的类型参见 CreatureAI.h "enum AIEventType"。

  - datalong2: 半径。如果未提供半径且目标是生物，则向目标发送 AIEvent。

  - datalong3: miscvalue -- uint32 -- 用于 ReceiveAIEvent 处理程序。

  - 来源和目标必须是生物。

**AIEventType**

| 值  | 名称                      | 注释                                                         |
| --- | ------------------------- | ------------------------------------------------------------ |
| 0   | AI_EVENT_JUST_DIED        | 发送者 = 被杀的 Npc，调用者 = 杀手                           |
| 1   | AI_EVENT_CRITICAL_HEALTH  | 发送者 = 受伤的 Npc，调用者 = 伤害制造者 -- 预期在 10% 生命值时发送 |
| 2   | AI_EVENT_LOST_HEALTH      | 发送者 = 受伤的 Npc，调用者 = 伤害制造者 -- 预期在 50% 生命值时发送 |
| 3   | AI_EVENT_LOST_SOME_HEALTH | 发送者 = 受伤的 Npc，调用者 = 伤害制造者 -- 预期在 90% 生命值时发送 |
| 4   | AI_EVENT_GOT_FULL_HEALTH  | 发送者 = 被治疗的 Npc，调用者 = 治疗者                       |
| 5   | AI_EVENT_CUSTOM_EVENTAI_A | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |
| 6   | AI_EVENT_CUSTOM_EVENTAI_B | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |
| 7   | AI_EVENT_GOT_CCED         | 发送者 = 被控制的 Npc，调用者 = 施放控制效果的法术施放者     |
| 8   | AI_EVENT_CUSTOM_EVENTAI_C | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |
| 9   | AI_EVENT_CUSTOM_EVENTAI_D | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |
| 10  | AI_EVENT_CUSTOM_EVENTAI_E | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |
| 11  | AI_EVENT_CUSTOM_EVENTAI_F | 发送者 = 抛出自定义事件的 Npc，调用者 = TARGET_T_ACTION_INVOKER（如果存在） |

- **SCRIPT_COMMAND_SET_FACING = 36**

  - 结果来源必须是一个生物；结果目标必须是一个世界对象。

  - datalong != 0 重置朝向。

| & data_flags                          | 描述                                                                 |
| ------------------------------------- | -------------------------------------------------------------------- |
| & SCRIPT_FLAG_COMMAND_ADDITIONAL 8 0×08 | 同时将 resultingSource 的 TargetGuid 设置为 resultingTarget（**必须**是生物/玩家） |

- **SCRIPT_COMMAND_MOVE_DYNAMIC = 37**

  - 结果来源必须是一个生物；结果目标必须是一个世界对象。

  - datalong = 0: 将结果来源移向结果目标。

  - datalong != 0: 将结果来源移动到结果目标周围 datalong2 和 datalong 之间的随机点。

  - datalong3 = 精确接触点距离，当你想在距离目标这个距离内就停止移动时使用。

  - orientation != 0: 在结果目标的朝向方向上获取一个随机点。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 在结果目标→GetOrientation + orientation 的方向上获取一个点。

  - 对于 resulting target == resulting source 且 orientation == 0 的情况，这将意味着 resulting source 向前移动。

  - dataint: [枚举 ForcedMovement](https://github.com/cmangos/issues/wiki/dbscripts#ForcedMovement)

  - dataint2: dbscripts_on_relay id。

- **SCRIPT_COMMAND_SEND_MAIL = 38**

  - 结果来源应该是一个生物或 NULL。结果目标必须是玩家。

  - datalong = 邮件模板编号 (mail_template_dbc + mail_loot_template)。

  - datalong2: 替代发送者编号。用作发送邮件的发送者编号。

  - datalong3: 金钱。

  - dataint: 延迟 (>= 0)（秒）。

- **SCRIPT_COMMAND_SET_HOVER = 39**

  - 结果来源必须是一个生物。

  - datalong = 布尔值 0=关闭，1=打开。

  - [data_flags](https://github.com/cmangos/issues/wiki/dbscripts#data_flags) & SCRIPT_FLAG_COMMAND_ADDITIONAL (8) 设置/取消字节标志 UNIT_BYTE1_FLAG_FLY_ANIM。

- **SCRIPT_COMMAND_DESPAWN_GO = 40**

  - 结果目标必须是一个游戏对象。请注意，并非所有游戏对象类型都支持此命令。

  - datalong = 消失延迟。

- **SCRIPT_COMMAND_RESPAWN = 41**

  - resultingSource = 生物。需要 SCRIPT_FLAG_BUDDY_IS_DESPAWNED 来查找死亡或已消失的目标。

- **SCRIPT_COMMAND_SET_EQUIPMENT_SLOTS = 42**

  - 结果来源必须是一个生物。

  - datalong = resetDefault: 布尔值 0=false, 1=true。

  - dataint = 主手槽位。

  - dataint2 = 副手槽位。

  - dataint3 = 远程槽位。

- **SCRIPT_COMMAND_RESET_GO = 43**

  - 结果目标必须是一个游戏对象。仅适用于门或按钮类型的游戏对象（游戏对象类型 0 和 1）。

- **SCRIPT_COMMAND_UPDATE_TEMPLATE = 44**

  - 结果来源必须是一个生物。

  - datalong = 新的生物编号。必须与当前编号不同。

  - datalong2 = 为其更新编号的阵营。0 = 联盟，1 = 部落。不允许其他值。

- **SCRIPT_COMMAND_START_RELAY_SCRIPT= 45**

  - 结果来源必须是一个单位。目标不是强制性的。

  - datalong = 应启动的 dbscripts_on_relay.id。

  - datalong2 = 应启动的 dbscript_random_templates.id。优先于 dbscripts_on_relay.id。

- **SCRIPT_COMMAND_CAST_CUSTOM_SPELL= 46**

  - 结果来源必须是一个单位。目标是单位。

  - datalong = 法术编号。

  - datalong2 = 施放标志, 枚举 [TriggerCastFlags](https://github.com/cmangos/issues/wiki/dbscripts#TriggerCastFlags)。

  - dataint -- dataint3 定义法术的 &bp 值。至少需要一个字段。

- **SCRIPT_COMMAND_INTERRUPT_SPELL= 47**

  - 结果来源必须是一个单位。

  - datalong = [枚举 CurrentSpellTypes](https://github.com/cmangos/issues/wiki/dbscripts#CurrentSpellTypes)

**CurrentSpellTypes**

| 值  | 名称                     |
| --- | ------------------------ |
| 0   | CURRENT_MELEE_SPELL      |
| 1   | CURRENT_GENERIC_SPELL    |
| 2   | CURRENT_AUTOREPEAT_SPELL |
| 3   | CURRENT_CHANNELED_SPELL  |

- **SCRIPT_COMMAND_MODIFY_UNIT_FLAGS = 48**

  - 结果来源必须是一个生物。

  - datalong: 单位标志。

  - datalong2: 0 移除，1 添加。

- **SCRIPT_COMMAND_SET_DATA_64 = 49**

  - 设置实例数据（如果存在）

  - datalong -- 设置数据 参数1

  - datalong2 -- 设置数据 参数2

- **SCRIPT_COMMAND_ZONE_PULSE = 50**

  - 脉冲区域进入战斗并攻击最近的敌人。

- **SCRIPT_COMMAND_SET_GOSSIP_MENU = 52**

  - 结果目标必须是一个生物。

  - datalong: gossipMenuId。

- **SCRIPT_COMMAND_SET_WORLDSTATE = 53**

  - 在当前地图中将世界状态变量设置为新值。

  - dataint = 世界状态变量编号 -- 必须已定义 worldstate_name 条目。

  - dataint2 = 新值。

- **SCRIPT_COMMAND_SET_SHEATHE= 54**

  - 更改生物的（sheatheState）。

  - datalong = 枚举 SheathState。

| 位  | 名称                 | 注释                       |
| --- | -------------------- | -------------------------- |
| 0   | SHEATH_STATE_UNARMED | 所有武器收鞘               |
| 1   | SHEATH_STATE_MELEE   | 近战武器出鞘               |
| 2   | SHEATH_STATE_RANGED  | 远程武器出鞘               |

- **SCRIPT_COMMAND_SET_STRING_ID = 55**

  - 为世界对象设置或移除 [string_id#id](https://github.com/cmangos/issues/wiki/string_id)。

  - datalong = string_id 编号。

  - datalong2 = 应用 -- 0 移除，1 添加。