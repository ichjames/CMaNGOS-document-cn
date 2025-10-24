**这是常规 'mangos' 数据库中的表列表**

(Reloadable) -- 表示在游戏内可以使用 `.reload` 命令重新加载。

(Core) -- 对这些表的更改由于其复杂性和关联性，需要提交并审查到 CMaNGOS-Core 代码库，**而非** CMaNGOS-DB 代码库。

(Classic) (TBC) (WotLK) (Cata) -- 表示自某个 CMaNGOS-Core 版本开始使用或仅用于某个特定版本。

| Table | Content | 中文翻译 |
| :--- | :--- | :--- |
| [ai_playerbot_enchants](https://github.com/cmangos/issues/wiki/ai_playerbot_enchants) | ? | ? |
| [ai_playerbot_help_texts](https://github.com/cmangos/issues/wiki/ai_playerbot_help_texts) | ? | ? |
| [ai_playerbot_named_location](https://github.com/cmangos/issues/wiki/ai_playerbot_named_location) | ? | ? |
| [ai_playerbot_rpg_races](https://github.com/cmangos/issues/wiki/ai_playerbot_rpg_races) | ? | ? |
| [ai_playerbot_texts](https://github.com/cmangos/issues/wiki/ai_playerbot_texts) | ? | ? |
| [ai_playerbot_texts_chance](https://github.com/cmangos/issues/wiki/ai_playerbot_texts_chance) | ? | ? |
| [ai_playerbot_travelnode](https://github.com/cmangos/issues/wiki/ai_playerbot_travelnode) | ? | ? |
| [ai_playerbot_travelnode_link](https://github.com/cmangos/issues/wiki/ai_playerbot_travelnode_link) | ? | ? |
| [ai_playerbot_travelnode_path](https://github.com/cmangos/issues/wiki/ai_playerbot_travelnode_path) | ? | ? |
| [ai_playerbot_weightscale_data](https://github.com/cmangos/issues/wiki/ai_playerbot_weightscale_data) | ? | ? |
| [ai_playerbot_weightscales](https://github.com/cmangos/issues/wiki/ai_playerbot_weightscales) | ? | ? |
| [ai_playerbot_zone_level](https://github.com/cmangos/issues/wiki/ai_playerbot_zone_level) | ? | ? |
| [achievement_criteria_requirement](https://github.com/cmangos/issues/wiki/achievement_criteria_requirement) | contains what need to be done to complete an achievement criteria. | 包含完成一项成就标准所需要达成的条件。 |
| [achievement_reward](https://github.com/cmangos/issues/wiki/achievement_reward) | contains the rewards for achievements added with Wrath of the Lichking. | 包含随巫妖王之怒版本增加的成就奖励。 |
| [areatrigger_involvedrelation](https://github.com/cmangos/issues/wiki/areatrigger_involvedrelation) (Reloadable) | Enable a trigger to finish one condition of a quest (explore) | 启用一个区域触发器来完成任务的某个条件（探索）。 |
| [areatrigger_tavern](https://github.com/cmangos/issues/wiki/areatrigger_tavern) (Reloadable) | Enable a trigger when player enters a city or tavern. This causes the player to enter a resting state. | 当玩家进入城市或旅店时启用触发器。这会使玩家进入休息状态。 |
| [areatrigger_teleport](https://github.com/cmangos/issues/wiki/areatrigger_teleport) (Reloadable) | contains all the teleport triggers definition. This table is used to complete .dbc file information. | 包含所有传送触发器的定义。此表用于补充 .dbc 文件信息。 |
| [battleground_events](https://github.com/cmangos/issues/wiki/battleground_events) | contains the description of battleground events. | 包含战场事件的描述。 |
| [battleground_template](https://github.com/cmangos/issues/wiki/battleground_template) | contains information about the different battlegrounds. | 包含关于不同战场的信息。 |
| [battlemaster_entry](https://github.com/cmangos/issues/wiki/battlemaster_entry) | holds information on which NPC can start what battleground or arena. | 保存关于哪些 NPC（战场军官）可以开启哪些战场或竞技场的信息。 |
| [broadcast_text](https://github.com/cmangos/issues/wiki/broadcast_text) | holds all the texts. | 保存所有的广播文本。 |
| [broadcast_text_locale](https://github.com/cmangos/issues/wiki/broadcast_text_locale) | holds translations for broadcast_text | 保存 broadcast_text 的本地化翻译。 |
| [combat_condition](https://github.com/cmangos/issues/wiki/combat_condition/) | holds complex checks for executing combat events on units for creature_spell_list | 保存用于为 creature_spell_list 在单位上执行战斗事件的复杂检查条件。 |
| [command](https://github.com/cmangos/issues/wiki/command) (Reloadable) | holds help and security information for commands. | 保存游戏内命令的帮助信息和安全等级（GM等级）要求。 |
| [conditions](https://github.com/cmangos/issues/wiki/conditions) | With this table and the new conditions it is possible to create tree like and very complicated combined conditions. | 通过此表和新条件系统，可以创建树状且非常复杂的组合条件。 |
| [creature](https://github.com/cmangos/issues/wiki/creature) | contains individual creature spawn data. Spawn of a creature is an instance of the creature object in the world. | 包含单个生物（NPC）的生成数据。生物的生成是生物模板在世界中的一个具体实例。 |
| [creature_addon](https://github.com/cmangos/issues/wiki/creature_template_addon) | defines different things that are applied on creature with a certain GUID when it is loaded. | 定义在加载具有特定 GUID（唯一标识）的生物实例时应用于其上的不同内容（如挂载、光环、站立状态等）。 |
| [creature_ai_scripts](https://github.com/cmangos/issues/wiki/creature_ai_scripts) (Reloadable) | ACID (Artificial Creature Intelligence Database) EventAI | ACID（人工智能生物数据库）EventAI 脚本。 |
| [creature_ai_summons](https://github.com/cmangos/issues/wiki/creature_ai_summons) (Reloadable) | is used to provide NPC support for an event using action 32 = ACTION_T_SUMMON as one of its Actions. | 用于为使用动作 32（召唤）作为其动作之一的事件AI脚本提供召唤生物的数据。 |
| [creature_battleground](https://github.com/cmangos/issues/wiki/creature_battleground) | contains the description of creatures spawned on battlegrounds. | 包含在战场上生成的生物的描述。 |
| [creature_conditional_spawn](https://github.com/cmangos/issues/wiki/creature_conditional_spawn) | contains creatures GUID that is spawned in INSTANCES depends of PLAYERS Faction Alliance/Horde. | 包含在副本中根据玩家阵营（联盟/部落）决定是否生成的生物 GUID。 |
| [creature_cooldowns](https://github.com/cmangos/issues/wiki/creature_cooldowns) | ? | ? |
| [creature_equip_template](https://github.com/cmangos/issues/wiki/creature_equip_template) | contains all equipment mobs can wear. | 包含所有生物可以穿戴的装备模板。 |
| [creature_immunities](https://github.com/cmangos/issues/wiki/creature_immunities) | Contains Immunities, that can not be set by MechanicImmuneMask (Taunt Immunity, Curse of Tongues Immunity) | 包含无法通过生物模板中的 MechanicImmuneMask（机制免疫掩码）设置的免疫效果（例如嘲讽免疫、舌结诅咒免疫）。 |
| [creature_involvedrelation](https://github.com/cmangos/issues/wiki/creature_involvedrelation) (Reloadable) | holds NPC quest ender relations on which NPCs finishes which quests. | 保存 NPC 任务结束者关系，即哪些 NPC 可以结束（完成）哪些任务。 |
| [creature_linking](https://github.com/cmangos/issues/wiki/creature_linking) | Creature Linking for Aggro/Respawn/Movement/Event by GUID | 通过 GUID 进行生物的仇恨、刷新、移动、事件等联动。 |
| [creature_linking_template](https://github.com/cmangos/issues/wiki/creature_linking_template) | Creature Linking for Aggro/Respawn/Movement/Event by ENTRY | 通过 ENTRY（生物模板编号）进行生物的仇恨、刷新、移动、事件等联动。 |
| [creature_loot_template](https://github.com/cmangos/issues/wiki/creature_loot_template) (Reloadable) | Creature Loot | 生物掉落模板。 |
| [creature_model_info](https://github.com/cmangos/issues/wiki/creature_model_info) | contains all models of mobs, their gender and other information that are model related. | 包含所有生物的模型数据、其性别以及其他与模型相关的信息（如碰撞大小、速度等）。 |
| [creature_model_race](https://github.com/cmangos/issues/wiki/creature_model_race) | contains data to override displayed models based on the race of the player. | 包含基于玩家种族来覆盖显示模型的数据（例如，不同种族的玩家看到同一个NPC的模型不同）。 |
| [creature_movement](https://github.com/cmangos/issues/wiki/creature_movement_template) | holds all the information on each single GUID creature's waypoints. | 保存每个单一 GUID 生物的路径点移动信息。 |
| [creature_movement_template](https://github.com/cmangos/issues/wiki/creature_movement_template) | holds all the information on each single ENTRY creature's waypoints. | 保存每个单一 ENTRY（生物模板）的路径点移动模板信息。 |
| [creature_onkill_reputation](https://github.com/cmangos/issues/wiki/creature_onkill_reputation) | controls the reputation given by creatures when killed by other players. | 控制生物被玩家杀死时给予的声望奖励。 |
| [creature_questrelation](https://github.com/cmangos/issues/wiki/creature_questrelation) (Reloadable) | holds NPC quest giver relations on which NPCs start which quests. | 保存 NPC 任务给予者关系，即哪些 NPC 可以开始（提供）哪些任务。 |
| [creature_spawn_data](https://github.com/cmangos/issues/wiki/creature_spawn_data) | link between individual creatures GUID and creature_spawn_data_template | 连接单个生物 GUID 和 creature_spawn_data_template 的关联表。 |
| [creature_spawn_data_template](https://github.com/cmangos/issues/wiki/creature_spawn_data_template) | contains data to override spawned creatures UnitFlags, Faction, ModelId, EquipmentId, CurHealth, CurMana, SpawnFlags | 包含用于覆盖已生成生物的单位标志、阵营、模型ID、装备ID、当前生命值、当前法力值、生成标志等数据的模板。 |
| [creature_spawn_entry](https://github.com/cmangos/issues/wiki/creature_spawn_entry) | holds multiple creature_template.entry a creature.guid can be spawned as. **creature.id = 0** | 保存一个 creature.guid 可以随机生成的多个 creature_template.entry（生物模板编号）。**（此表使用时，creature 表的 id 字段应设为 0）** |
| [creature_spell_list](https://github.com/cmangos/issues/wiki/creature_spell_list) | holds basic creature combat information, supplymented by [creature_spell_list_entry](https://github.com/cmangos/issues/wiki/creature_spell_list#the-creature_spell_list_entry-table) and creature_spell_targeting (hardcoded target values for creature_spell_list | 保存生物战斗AI（SmartAI）使用的基本法术列表信息，由 creature_spell_list_entry 表和 creature_spell_targeting（硬编码目标选择）补充。 |
| [creature_template](https://github.com/cmangos/issues/wiki/creature_template) | contains the description of creatures. | 包含生物的模板数据，定义了生物的基本属性、技能、掉落等。 |
| [creature_template_addon](https://github.com/cmangos/issues/wiki/creature_template_addon) | defines different things that are applied on creature with a certain ENTRY when it is loaded. | 定义在加载具有特定 ENTRY（生物模板编号）的生物时应用于其上的不同内容（如挂载、光环、站立状态等）。 |
| [creature_template_classlevelstats](https://github.com/cmangos/issues/wiki/creature_template_classlevelstats) | Unit Base Stats | 单位（生物）基础属性（生命、法力、护甲等）按等级和分类的模板。 |
| [creature_template_spells](https://github.com/cmangos/issues/wiki/creature_template_spells) | obsolete | 已废弃。 |
| [costum_texts](https://github.com/cmangos/issues/wiki/costum_texts) | ? | ? |
| [db_version](https://github.com/cmangos/issues/wiki/db_version) | contains the version of the DB in use. | 包含正在使用的数据库版本信息。 |
| [dbscript_random_templates](https://github.com/cmangos/issues/wiki/dbscript_random_templates) | holds randomize texts and relay scripts | 保存随机化的文本和中继脚本的模板。 |
| [dbscripts_on_creature_death](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated when a creature dies. | 保存生物死亡时激活的数据脚本。 |
| [dbscripts_on_creature_movement](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated while a npc is moving. | 保存 NPC 在路径点上移动时激活的数据脚本。 |
| [dbscripts_on_event](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated whenever an event is activated by spell, gameobject or taxi waypoints. | 保存通过法术、游戏对象或飞行路径点激活事件时激活的数据脚本。 |
| [dbscripts_on_go_template_use](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds possible scripts activated by gameobjects. | 保存可能由游戏对象（使用）激活的数据脚本。 |
| [dbscripts_on_go_use](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds possible scripts activated by GAMEOBJECT_TYPE_DOOR and GAMEOBJECT_TYPE_BUTTON. | 保存可能由 GAMEOBJECT_TYPE_DOOR（门）和 GAMEOBJECT_TYPE_BUTTON（按钮）类型游戏对象激活的数据脚本。 |
| [dbscripts_on_gossip](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated on gossip_menu_option or gossip_menu. | 保存在玩家与 NPC 对话（ gossip_menu_option 或 gossip_menu ）时激活的数据脚本。 |
| [dbscripts_on_quest_end](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated when a player finishes a quest. | 保存玩家完成任务时激活的数据脚本。 |
| [dbscripts_on_quest_start](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts activated when a player accepts a quest. | 保存玩家接受任务时激活的数据脚本。 |
| [dbscripts_on_relay](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts that are relayed from AI or other dbscripts. | 保存从 AI 系统或其他数据脚本中继过来的数据脚本。 |
| [dbscripts_on_spell](https://github.com/cmangos/issues/wiki/DBScripts) (Reloadable) | holds scripts that can be activated by spells | 保存可以通过施放法术激活的数据脚本。 |
| [disenchant_loot_template](https://github.com/cmangos/issues/wiki/disenchant_loot_template) (Reloadable) | Item disenchant loot | 物品分解掉落模板。 |
| [exploration_basexp](https://github.com/cmangos/issues/wiki/exploration_basexp) | controls the XP gained by characters when they explore new zones. | 控制玩家探索新区域时获得的经验值。 |
| [faction_store](https://github.com/cmangos/issues/wiki/faction_store) | Faction.dbc | 与 DBC 文件 Faction.dbc 相关的数据存储。 |
| [fishing_loot_template](https://github.com/cmangos/issues/wiki/fishing_loot_template) (Reloadable) | Fishing loot | 钓鱼掉落模板。 |
| [game_event](https://github.com/cmangos/issues/wiki/game_event) | contains definitions for all game events that are activated or deactivated automatically by the Game Event System in the core. | 包含所有游戏事件的定义，这些事件由核心的游戏事件系统自动激活或停用。 |
| [game_event_creature](https://github.com/cmangos/issues/wiki/game_event_creature) | contains all creature instances that have to be spawned/unspawned during defined game events. | 包含在特定游戏事件期间需要生成或取消生成的所有生物实例。 |
| [game_event_creature_data](https://github.com/cmangos/issues/wiki/game_event_creature_data) | contains all creature instances that need to change display id and/or equipment during defined game events. | 包含在特定游戏事件期间需要改变显示ID和/或装备的所有生物实例。 |
| [game_event_gameobject](https://github.com/cmangos/issues/wiki/game_event_gameobject) | contains all gameobjects instances that participate to any game event. | 包含参与任何游戏事件的所有游戏对象实例。 |
| [game_event_mail](https://github.com/cmangos/issues/wiki/game_event_mail) | ? | ? |
| [game_event_quest](https://github.com/cmangos/issues/wiki/game_event_quest) | holds quests, which are only active during certain events. | 保存仅在特定事件期间才可用的任务。 |
| [game_event_time](https://github.com/cmangos/issues/wiki/game_event_time) | ? | ? |
| [game_graveyard_zone](https://github.com/cmangos/issues/wiki/game_graveyard_zone) (Reloadable) | Contains informations about zones connected to world's graveyards. | 包含与世界中的墓地相关联的区域信息。 |
| [game_tele](https://github.com/cmangos/issues/wiki/game_tele) | contains a list of teleport locations that can be used with the .tele command in-game. | 包含一个可使用游戏内 `.tele` 命令传送的位置列表。 |
| [game_weather](https://github.com/cmangos/issues/wiki/game_weather) | holds the percentages for weather changes in various zones. | 保存各个区域天气变化的概率。 |
| [gameobject](https://github.com/cmangos/issues/wiki/gameobject) | holds the individual object data on each spawned game object in the world. | 保存世界中每个已生成的游戏对象（GAMEOBJECT）的实例数据。 |
| [gameobject_addon](https://github.com/cmangos/issues/wiki/gameobject_addon) | Nondefault animprogress, state, path_rotation | 定义游戏对象实例的非默认动画进度、状态和路径旋转。 |
| [gameobject_battleground](https://github.com/cmangos/issues/wiki/gameobject_battleground) | contains the events of gameobjects which are spawned on battlegrounds. | 包含在战场上生成的游戏对象的事件信息。 |
| [gameobject_involvedrelation](https://github.com/cmangos/issues/wiki/gameobject_involvedrelation) (Reloadable) | holds game object quest taker relations. | 保存游戏对象任务完成者关系（即与哪些游戏对象交互可以完成任务）。 |
| [gameobject_loot_template](https://github.com/cmangos/issues/wiki/gameobject_loot_template) (Reloadable) | Gameobject loot | 游戏对象掉落模板。 |
| [gameobject_questrelation](https://github.com/cmangos/issues/wiki/gameobject_questrelation) (Reloadable) | holds game object quest giver relations. | 保存游戏对象任务给予者关系（即从哪些游戏对象可以接到任务）。 |
| [gameobject_spawn_entry](https://github.com/cmangos/issues/wiki/gameobject_spawn_entry) | holds multiple gameobject_template.entry a gameobject.guid can be spawned as. **gameobject.id = 0** | 保存一个 gameobject.guid 可以随机生成的多个 gameobject_template.entry（游戏对象模板编号）。**（此表使用时，gameobject 表的 id 字段应设为 0）** |
| [gameobject_template](https://github.com/cmangos/issues/wiki/gameobject_template) | contains template off all world's objects. | 包含所有游戏对象的模板数据。 |
| [gameobject_template_addon](https://github.com/cmangos/issues/wiki/gameobject_template_addon) | Artkit Data | 游戏对象模板的美术套件数据。 |
| [gossip_menu](https://github.com/cmangos/issues/wiki/gossip_menu) (Reloadable) | contains displayed gossip when a player talks to an NPC. | 包含玩家与 NPC 对话时显示的 gossip 菜单内容。 |
| [gossip_menu_option](https://github.com/cmangos/issues/wiki/gossip_menu_option) (Reloadable) | holds infos about menu options a gossip NPC can have. | 保存一个 gossip NPC 可以拥有的菜单选项信息。 |
| [gossip_texts](https://github.com/cmangos/issues/wiki/gossip_texts) | holds gossip texts used in ScriptDevAI. | 保存 ScriptDevAI 中使用的 gossip 文本。 |
| [instance_dungeon_encounters](https://github.com/cmangos/issues/wiki/instance_dungeon_encounters) | ? | ? |
| [instance_encounters](https://github.com/cmangos/issues/wiki/instance_encounters) | ? | ? |
| [instance_template](https://github.com/cmangos/issues/wiki/instance_template) (Core) | contains all the templates for every instance. | 包含所有副本（地下城、团队副本）的模板信息。 |
| [item_convert](https://github.com/cmangos/issues/wiki/item_convert) | ? | ? |
| [item_enchantment_template](https://github.com/cmangos/issues/wiki/item_enchantment_template) | holds enchantment chance information for items that should have either a random property or a random suffix attached to them. | 保存附魔几率信息，用于那些应该带有随机属性或随机后缀的物品。 |
| [item_expire_convert](https://github.com/cmangos/issues/wiki/item_expire_convert) (Reloadable) | contains pairs of times which turn into an other item after a certain amount of time. | 包含物品对，定义了一个物品在经过特定时间后会转变为另一个物品。 |
| [item_loot_template](https://github.com/cmangos/issues/wiki/item_loot_template) (Reloadable) | Item loot | 物品（容器、任务物品等）掉落模板。 |
| [item_required_target](https://github.com/cmangos/issues/wiki/item_required_target) (Reloadable) | These spell effects require a specific target in either alive or dead state (for creatures). | 定义某些物品使用时的法术效果需要特定的目标（生物），目标可以是存活或死亡状态。 |
| [item_template](https://github.com/cmangos/issues/wiki/item_template) | holds information on every item that exists in the game. | 保存游戏中存在的所有物品的模板信息。 |
| [locales_areatrigger_teleport](https://github.com/cmangos/issues/wiki/locales_areatrigger_teleport) | ? | ? |
| [locales_creature](https://github.com/cmangos/issues/wiki/locales_creature) | is used to provide to localized clients with localized string for creatures. | 用于为本地化客户端提供生物的本地化字符串（如名称、子名称）。 |
| [locales_gameobject](https://github.com/cmangos/issues/wiki/locales_gameobject) | is used to provide to localized clients with localized string for gameobjects. | 用于为本地化客户端提供游戏对象的本地化字符串（如名称）。 |
| [locales_gossip_menu_option](https://github.com/cmangos/issues/wiki/locales_gossip_menu_option) | ? | ? |
| [locales_item](https://github.com/cmangos/issues/wiki/locales_item) | is used to provide to localized clients with localized string for items. | 用于为本地化客户端提供物品的本地化字符串（如名称、描述）。 |
| [locales_npc_text](https://github.com/cmangos/issues/wiki/locales_npc_text) | is used to provide localized clients with localized string for npc_texts. | 用于为本地化客户端提供 NPC 文本（npc_texts）的本地化字符串。 |
| [locales_page_text](https://github.com/cmangos/issues/wiki/locales_page_text) | is used to provide localized clients with localized string for page_texts. | 用于为本地化客户端提供页面文字（page_texts，如书籍内容）的本地化字符串。 |
| [locales_points_of_interest](https://github.com/cmangos/issues/wiki/locales_points_of_interest) | ? | ? |
| [locales_quest](https://github.com/cmangos/issues/wiki/locales_quest) | is used to provide to localized clients with localized string for quest templates. | 用于为本地化客户端提供任务模板的本地化字符串（如标题、详情、目标、完成文本）。 |
| [locales_questgiver_greeting](https://github.com/cmangos/issues/wiki/locales_questgiver_greeting) | is used to provide to localized clients with localized string for questgiver_greetings. | 用于为本地化客户端提供任务给予者问候语的本地化字符串。 |
| [locales_trainer_greeting](https://github.com/cmangos/issues/wiki/locales_trainer_greeting) | ? | ? |
| [mail_level_reward](https://github.com/cmangos/issues/wiki/mail_level_reward) (Reloadable) | holds information on sent mails when a character levels up. Can be specified by raceMask. | 保存角色升级时发送的邮件信息。可以通过种族掩码（raceMask）指定。 |
| [mail_loot_template](https://github.com/cmangos/issues/wiki/mail_loot_template) (Reloadable) | ? | ? |
| [mangos_string](https://github.com/cmangos/issues/wiki/mangos_string) | holds all of the strings used internally by the server. | 保存服务器内部使用的所有字符串（如系统消息、错误提示）。 |
| [milling_loot_template](https://github.com/cmangos/issues/wiki/milling_loot_template) | Milling loot | 研磨（草药加工）掉落模板。 |
| [npc_gossip](https://github.com/cmangos/issues/wiki/npc_gossip) | THIS TABLE IS OUTDATED. DO NOT USE | **此表已过时。请勿使用。** |
| [npc_spellclick_spells](https://github.com/cmangos/issues/wiki/npc_spellclick_spells) (Reloadable) | holds information about spells to be casted upon receiving CMSG_SPELLCLICK. | 保存关于在收到法术点击（CMSG_SPELLCLICK）消息时要施放的法术信息（常用于坐骑、载具）。 |
| [npc_text](https://github.com/cmangos/issues/wiki/npc_text) | contains the texts that are used for gossip. | 包含用于 NPC 对话（gossip）的文本。 |
| [npc_text_broadcast_text](https://github.com/cmangos/issues/wiki/npc_text_broadcast_text) | Should replace npc_text as new npc_text at some point | 应在未来某个时刻取代 npc_text 表的新 NPC 文本表（基于 broadcast_text）。 |
| [npc_trainer](https://github.com/cmangos/issues/wiki/npc_trainer_template) | holds the spell data for all trainers by ENTRY. | 按 NPC 的 ENTRY 保存所有职业训练师、武器大师等所能教授的法术/技能数据。 |
| [npc_trainer_template](https://github.com/cmangos/issues/wiki/npc_trainer_template) | holds the spell data for all trainers by TrainerTemplateId. | 按训练师模板ID（TrainerTemplateId）保存训练师所能教授的法术/技能数据。 |
| [npc_vendor](https://github.com/cmangos/issues/wiki/npc_vendor_template) | holds the vendor data for all NPCs that sell items by ENTRY. | 按 NPC 的 ENTRY 保存所有商人（供应商）所出售的物品数据。 |
| [npc_vendor_template](https://github.com/cmangos/issues/wiki/npc_vendor_template) | holds the vendor data for all NPCs that sell items by VendorTemplateId. | 按商人模板ID（VendorTemplateId）保存商人所出售的物品数据。 |
| [page_text](https://github.com/cmangos/issues/wiki/page_text) | holds the text for letter items. | 保存书信类物品的文字内容。 |
| [pet_familystats](https://github.com/cmangos/issues/wiki/pet_familystats) | ? | ? |
| [pet_levelstats](https://github.com/cmangos/issues/wiki/pet_levelstats) | holds information on individual pet base stats based on level. | 保存猎人宠物或术士魅魔等基于等级的个体基础属性信息。 |
| [pet_name_generation](https://github.com/cmangos/issues/wiki/pet_name_generation) | holds pieces of names (first and last half) that are use for pet name generation. | 保存用于生成宠物名称的姓名片段（前半部分和后半部分）。 |
| [petcreateinfo_spell](https://github.com/cmangos/issues/wiki/petcreateinfo_spell) | controls what spells a tameable beast will have once tamed. | 控制一个可驯服的野兽在被驯服后将拥有哪些技能。 |
| [pickpocketing_loot_template](https://github.com/cmangos/issues/wiki/pickpocketing_loot_template) (Reloadable) | Pickpocketing loot | 偷窃掉落模板。 |
| [player_classlevelstats](https://github.com/cmangos/issues/wiki/player_classlevelstats) | holds information on the base health and mana of characters when they level up. Each class has different level stats. | 保存玩家角色升级时的基础生命值和法力值。每个职业都有不同的等级属性。 |
| [player_levelstats](https://github.com/cmangos/issues/wiki/player_levelstats) | holds information on the base health and mana of characters when they level up. Each class has different level stats. | 保存玩家角色升级时的基础生命值和法力值。每个职业都有不同的等级属性。（与 player_classlevelstats 类似，具体使用哪个需看核心版本） |
| [player_xp_for_level](https://github.com/cmangos/issues/wiki/player_xp_for_level) | includes information on how much experience needed for next level. Comes from sniffs. | 包含升到下一级所需经验值的信息。数据来源于网络嗅探（Sniffs）。 |
| [playercreateinfo](https://github.com/cmangos/issues/wiki/playercreateinfo) | holds the start positions of each class-race combinations for all newly created characters. | 保存所有新建的种族-职业组合角色的起始位置（地图、区域、坐标、朝向）。 |
| [playercreateinfo_action](https://github.com/cmangos/issues/wiki/playercreateinfo_action) | holds information on what default actions a brand new character should start out with. | 保存一个新创建的角色初始时应具备的默认动作条技能/物品。 |
| [playercreateinfo_item](https://github.com/cmangos/issues/wiki/playercreateinfo_item) | holds information on what items each race-class combination of a new character starts out with. | 保存新创建的每个种族-职业组合角色初始时拥有的物品。 |
| [playercreateinfo_skills](https://github.com/cmangos/issues/wiki/playercreateinfo_skills) | holds information on what skills newly created characters should start out with. | 保存新创建的角色初始时应具备的技能（如语言、武器技能）。 |
| [playercreateinfo_spell](https://github.com/cmangos/issues/wiki/playercreateinfo_spell) | holds information on what spells newly created characters should start out with. | 保存新创建的角色初始时应具备的法术/技能。 |
| [points_of_interest](https://github.com/cmangos/issues/wiki/points_of_interest) (Reloadable) | comes from sniffs. | 包含地图上的兴趣点（POI）信息，如旅馆、商人、训练师的位置。数据来源于网络嗅探（Sniffs）。 |
| [pool_creature](https://github.com/cmangos/issues/wiki/pool_creature) | contains all pooled creatures by GUID that are part of a pool_template. | 包含所有按 GUID 加入刷新池（pool_template）的生物实例。 |
| [pool_creature_template](https://github.com/cmangos/issues/wiki/pool_creature_template) | contains all pooled creatures by ENTRY that are part of a pool_template. | 包含所有按 ENTRY（生物模板编号）加入刷新池（pool_template）的生物。 |
| [pool_gameobject](https://github.com/cmangos/issues/wiki/pool_gameobject) | contains all pooled gameobjects by GUID that are part of a pool_template. | 包含所有按 GUID 加入刷新池（pool_template）的游戏对象实例。 |
| [pool_gameobject_template](https://github.com/cmangos/issues/wiki/pool_gameobject_template) | contains all pooled gameobjects by ENTRY that are part of a pool_template. | 包含所有按 ENTRY（游戏对象模板编号）加入刷新池（pool_template）的游戏对象。 |
| [pool_pool](https://github.com/cmangos/issues/wiki/pool_pool) | contains pool of pools. You can create a pool with a chance of a range of pools in that pool being activated. | 包含池中池。可以创建一个母池，其中有一定几率激活其包含的一系列子池。 |
| [pool_template](https://github.com/cmangos/issues/wiki/pool_template) | contains all pool instances that participate to any game event. | 包含所有刷新池模板的定义。 |
| [prospecting_loot_template](https://github.com/cmangos/issues/wiki/prospecting_loot_template) (Reloadable) | Prospecting loot | 选矿（矿石加工）掉落模板。 |
| [quest_poi](https://github.com/cmangos/issues/wiki/quest_poi) (Reloadable) | comes from sniffs. | 包含任务目标点（Points of Interest）信息。数据来源于网络嗅探（Sniffs）。 |
| [quest_poi_points](https://github.com/cmangos/issues/wiki/quest_poi_points) (Reloadable) | comes from sniffs. Visually speaking, this table is used to identify the X and Y coordinates on the map (not the minimap -- the main map) where a quest's question mark should appear. | 包含任务目标点（POI）的具体坐标点。数据来源于网络嗅探（Sniffs）。直观地说，此表用于确定任务问号应出现在世界地图（非小地图）上的 X 和 Y 坐标。 |
| [quest_template](https://github.com/cmangos/issues/wiki/quest_template) (Reloadable) | contains all basic definitions of quests available. | 包含所有可用任务的基本定义。 |
| [questgiver_greeting](https://github.com/cmangos/issues/wiki/questgiver_greeting) (Reloadable) | contains texts sent by certain quest creatures/objects. | 包含某些任务给予者（生物或对象）发送的问候文本。 |
| [reference_loot_template](https://github.com/cmangos/issues/wiki/reference_loot_template) (Reloadable) | reference loot (loot groups) | 参考掉落模板（掉落组），可被其他掉落模板引用。 |
| [reference_loot_template_names](https://github.com/cmangos/issues/wiki/reference_loot_template) (Reloadable) | Holds names of commonly used [reference_loot_template](https://github.com/cmangos/issues/wiki/reference_loot_template) | 保存常用参考掉落模板的名称，便于管理。 |
| [reputation_reward_rate](https://github.com/cmangos/issues/wiki/reputation_reward_rate) (Reloadable) | holds reputation multipliers for specific factions. | 保存特定阵营的声望获取倍率。 |
| [reputation_spillover_template](https://github.com/cmangos/issues/wiki/reputation_spillover_template) | holds information about the [Reputation Bleed Over](http://wowwiki.wikia.com/wiki/Exalted) -Effect | 保存关于声望溢出（当一个阵营声望达到崇拜后，其相关阵营获得部分声望）效果的信息。 |
| [reserved_name](https://github.com/cmangos/issues/wiki/reserved_name) (Reloadable) | serves as a simple list of names that players (gmlevel == 0) cannot use when naming their characters. | 作为一个简单的保留名称列表，普通玩家（gmlevel == 0）在创建角色时不能使用这些名字。 |
| [script_texts](https://github.com/cmangos/issues/wiki/script_texts) (Core) | holds all the texts used by core scripted creatures/entities (ScriptDev) | 保存由核心脚本（如 ScriptDev2）控制的生物/实体所使用的所有文本（如喊话、对话）。 |
| [script_waypoint](https://github.com/cmangos/issues/wiki/script_waypoint) (Core) | ? | ? |
| [scripted_areatrigger](https://github.com/cmangos/issues/wiki/scripted_areatrigger) (Core) | This table links areatriggers to C++ scripts. | 此表将区域触发器与 C++ 脚本相关联。 |
| [scripted_event_id](https://github.com/cmangos/issues/wiki/scripted_event_id) (Core) | This table links event id's to C++ scripts. | 此表将事件ID与 C++ 脚本相关联。 |
| [skill_discovery_template](https://github.com/cmangos/issues/wiki/skill_discovery_template) (Reloadable) | controls the so called "discovery" system of learning spells. | 控制所谓的法术“发现”学习系统（例如通过制作物品有几率领悟新配方）。 |
| [skill_extra_item_template](https://github.com/cmangos/issues/wiki/skill_extra_item_template) | holds information about when using certain profession spells, you have the chance of creating more than one copy of the item. | 保存关于在使用某些专业技能时，有几率额外制造出多份成品的信息。 |
| [skill_fishing_base_level](https://github.com/cmangos/issues/wiki/skill_fishing_base_level) | controls the minimum skill level required in fishing to fish in a certain area. | 控制在特定区域钓鱼所需的最低钓鱼技能等级。 |
| [skinning_loot_template](https://github.com/cmangos/issues/wiki/skinning_loot_template) | Skinning loot | 剥皮掉落模板。 |
| [spam_records](https://github.com/cmangos/issues/wiki/spam_records) | Anticheat | 反作弊 - 垃圾信息记录。 |
| [spawn_group](https://github.com/cmangos/issues/wiki/spawn_group) | Defines how groups of entities spawn spawn_group_entry, spawn_group_formation, spawn_group_linked_group, spawn_group_spawn | 定义实体组（生物、游戏对象）的生成方式，关联表包括 spawn_group_entry, spawn_group_formation, spawn_group_linked_group, spawn_group_spawn。 |
| [spell_affect](https://github.com/cmangos/issues/wiki/spell_affect) (Reloadable) | holds information on what spells are affected by what spell mods. | 保存关于哪些法术受哪些法术效果修饰（如天赋、装备效果）影响的信息。 |
| [spell_area](https://github.com/cmangos/issues/wiki/spell_area) (Reloadable) | holds information on what spells are applied to npcs/players in some areas. | 保存关于在特定区域对 NPC/玩家自动施加或移除哪些法术（光环）的信息。 |
| [spell_chain](https://github.com/cmangos/issues/wiki/spell_chain) (Reloadable) | defines spell chains. A spell chain is a series of spells which all share the same name and all do the same thing. | 定义法术链。一个法术链是一系列共享相同名称和作用，但效果逐级增强的法术（例如不同等级的治疗术）。 |
| [spell_check](https://github.com/cmangos/issues/wiki/spell_check) | ? | ? |
| [spell_cone](https://github.com/cmangos/issues/wiki/spell_cone) | holds Degrees for Cone spells | 保存锥形范围法术的作用角度。 |
| [spell_elixir](https://github.com/cmangos/issues/wiki/spell_elixir) (Reloadable) | holds elixir information to be used to properly stack the elixirs. | 保存药剂信息，用于正确处理药剂的叠加规则（战斗/守护药剂）。 |
| [spell_group](https://github.com/cmangos/issues/wiki/spell_group) | ? | ? |
| [spell_group_spell](https://github.com/cmangos/issues/wiki/spell_group_spell) | ? | ? |
| [spell_facing](https://github.com/cmangos/issues/wiki/spell_facing) | ? | ? |
| [spell_learn_spell](https://github.com/cmangos/issues/wiki/spell_learn_spell) (Reloadable) | holds information on spells that should be learned at the same time a player learns another spell. | 保存关于当玩家学习某个法术时，应同时自动学会的其他法术的信息（例如学习骑术自动获得对应坐骑技能）。 |
| [spell_loot_template](https://github.com/cmangos/issues/wiki/spell_loot_template) (Reloadable) | Spell loot | 法术掉落模板（例如制造、采集技能产出的物品）。 |
| [spell_pet_auras](https://github.com/cmangos/issues/wiki/spell_pet_auras) | ? | ? |
| [spell_proc_event](https://github.com/cmangos/issues/wiki/spell_proc_event) (Reloadable) | holds information on how certain spells activate, which proc other spells. | 保存关于某些法术（通常是光环或被动效果）如何被激活并触发其他法术的信息。 |
| [spell_proc_item_enchant](https://github.com/cmangos/issues/wiki/spell_proc_item_enchant) (Reloadable) | holds information (ppmRate) for item (weapon) enchants | 保存物品（武器）附魔的触发几率信息（通常使用 PPM - 每分钟触发次数）。 |
| [spell_script_target](https://github.com/cmangos/issues/wiki/spell_script_target) (Reloadable) | holds information on spell effects which require a specific target in either alive or dead state (for creatures). | 保存关于需要特定目标（生物，存活或死亡状态）的法术效果的信息。 |
| [spell_scripts](https://github.com/cmangos/issues/wiki/spell_scripts) (Core) | holds ScriptName of spells scripted in Core | 保存在核心中实现了 C++ 脚本的法术所对应的脚本名称（ScriptName）。 |
| [spell_target_position](https://github.com/cmangos/issues/wiki/spell_target_position) (Reloadable) | holds coordinate information on where the player should be teleported to when a spell with effect SPELL_EFFECT_TELEPORT_UNITS. | 保存当施放具有传送单位效果（SPELL_EFFECT_TELEPORT_UNITS）的法术时，玩家应被传送到的目标位置坐标信息。 |
| [spell_template](https://github.com/cmangos/issues/wiki/spell_template) (Core) | contains the description of spells. | 包含法术的模板数据。 |
| [spell_threat](https://github.com/cmangos/issues/wiki/spell_threat) (Reloadable) | holds threat values on all spells that should either give or take away threat. | 保存所有会产生或减少威胁值的法术的威胁值信息。 |
| [string_id](https://github.com/cmangos/issues/wiki/string_id) | holds ids and strings connection between string_id variables. StringId is assigned to a world object, and then enables querying. Effectively supercedes guid, entry, or other kind of targeting, and enables custom targeting from spells or even per dbscript. | 保存 string_id 变量之间的 ID 和字符串连接关系。StringId 被分配给一个世界对象，然后可以实现查询。它有效地取代了 GUID、ENTRY 或其他类型的目标选择方式，并允许从法术甚至每个数据库脚本进行自定义目标选择。 |
| [taxi_shortcuts](https://github.com/cmangos/issues/wiki/taxi_shortcuts) (Reloadable) | holds information about shortcuts for each individual taxi flight. | 保存关于各个飞行路线捷径的信息（允许玩家直接飞往中途点）。 |
| [trainer_greeting](https://github.com/cmangos/issues/wiki/trainer_greeting) | ? | ? |
| [transports](https://github.com/cmangos/issues/wiki/transports) | contains all type 15 transports (Boats and Zeppelins). | 包含所有类型为 15 的交通工具（船和飞艇）的路径和时刻表信息。 |
| [unit_condition](https://github.com/cmangos/issues/wiki/unit_condition) | contains data used for condition checks on units | 包含用于对单位（生物、玩家）进行条件检查的数据。 |
| [vehicle_accessory](https://github.com/cmangos/issues/wiki/vehicle_accessory) | ? | ? |
| [warden_scans](https://github.com/cmangos/issues/wiki/warden_scans) | Anticheat | 反作弊 - Warden 扫描模块数据。 |
| [waypoint_path](https://github.com/cmangos/issues/wiki/spawn_group) | paths linked to [spawn_groups](https://github.com/cmangos/issues/wiki/spawn_group) | 与生成组（spawn_groups）相关联的路径点路径数据。 |
| [waypoint_path_name](https://github.com/cmangos/issues/wiki/spawn_group) | path names linked to [spawn_groups](https://github.com/cmangos/issues/wiki/spawn_group) | 与生成组（spawn_groups）相关联的路径点路径名称。 |
| [world_safe_locs](https://github.com/cmangos/issues/wiki/world_safe_locs) | ? | ? |
| [world_template](https://github.com/cmangos/issues/wiki/world_template) (Core) | holds the ScriptNames of the world maps 0, 1, 530, 571 | 保存世界地图（0, 1, 530, 571 等）的关联脚本名称（ScriptName）。 |
| [worldstate_expression](https://github.com/cmangos/issues/wiki/worldstate_expression) | holds data for evaluating worldstate conditions. On more info about worldstate variables go to Worldstates | 保存用于评估世界状态（WorldState）条件的数据。 |
| [worldstate_name](https://github.com/cmangos/issues/wiki/worldstate_name) | holds data on worldstate variables used for CONDITION_WORLDSTATE | 保存用于 CONDITION_WORLDSTATE 条件的世界状态变量的数据。 |