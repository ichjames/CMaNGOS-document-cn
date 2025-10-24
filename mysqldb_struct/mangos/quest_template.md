Quest_template

 

**`quest_template` 表**

包含所有可用任务的基本定义。

**结构**

| **字段**                                                                       | **类型**            | **Null** | **Key** | **默认值** | **额外**      |
| ------------------------------------------------------------------------------ | ------------------- | -------- | ------- | ---------- | ------------- |
| [entry](https://github.com/cmangos/issues/wiki/Quest_template#entry)           | int(10) unsigned    | 否       | 主键    | 0          |               |
| [Method](https://github.com/cmangos/issues/wiki/Quest_template#method)         | tinyint(3)          | 否       |         | 2          |               |
| [ZoneOrSort](https://github.com/cmangos/issues/wiki/Quest_template#zoneorsort) | smallint(6)         | 否       |         | 0          |               |
| [MinLevel](https://github.com/cmangos/issues/wiki/Quest_template#minlevel)     | tinyint(3) unsigned | 否       |         | 0          |               |
| [QuestLevel](https://github.com/cmangos/issues/wiki/Quest_template#questlevel) | tinyint(3) unsigned | 否       |         | 0          |               |
| [Type](https://github.com/cmangos/issues/wiki/Quest_template#type)             | smallint(5) unsigned| 否       |         | 0          |               |
| [RequiredClasses](https://github.com/cmangos/issues/wiki/Quest_template#requiredclasses) | smallint(5) | 否       |         | 0          |               |
| [RequiredRaces](https://github.com/cmangos/issues/wiki/Quest_template#requiredraces) | smallint(5) | 否       |         | 0          |               |
| [RequiredSkill](https://github.com/cmangos/issues/wiki/Quest_template#requiredskill) | smallint(5) | 否       |         | 0          |               |
| [RequiredSkillValue](https://github.com/cmangos/issues/wiki/Quest_template#requiredskillvalue) | smallint(5) unsigned | 否 |         | 0          |               |
| [RequiredCondition](https://github.com/cmangos/issues/wiki/Quest_template#RequiredCondition) | smallint(5) unsigned | 否 |         | 0          |               |
| [RepObjectiveFaction](https://github.com/cmangos/issues/wiki/Quest_template#repobjectivefaction) | smallint(5) unsigned | 否 |         | 0          |               |
| [RepObjectiveValue](https://github.com/cmangos/issues/wiki/Quest_template#repobjectivevalue) | mediumint(9) | 否 |         | 0          |               |
| [RequiredMinRepFaction](https://github.com/cmangos/issues/wiki/Quest_template#requiredminrepfaction) | mediumint(5) unsigned | 否 |         | 0          |               |
| [RequiredMinRepValue](https://github.com/cmangos/issues/wiki/Quest_template#requiredminrepvalue) | mediumint(9) | 否 |         | 0          |               |
| [RequiredMaxRepFaction](https://github.com/cmangos/issues/wiki/Quest_template#requiredmaxrepfaction) | mediumint(5) unsigned | 否 |         | 0          |               |
| [RequiredMaxRepValue](https://github.com/cmangos/issues/wiki/Quest_template#requiredmaxrepvalue) | mediumint(9) | 否 |         | 0          |               |
| [SuggestedPlayers](https://github.com/cmangos/issues/wiki/Quest_template#suggestedplayers) | mediumint(3) unsigned | 否 |         | 0          |               |
| [LimitTime](https://github.com/cmangos/issues/wiki/Quest_template#limittime)   | int(10)             | 否       |         | 0          |               |
| [QuestFlags](https://github.com/cmangos/issues/wiki/Quest_template#questflags) | smallint(5) unsigned| 否       |         | 0          |               |
| [SpecialFlags](https://github.com/cmangos/issues/wiki/Quest_template#specialflags) | tinyint(3) unsigned | 否 |         | 0          |               |
| [CharTitleId](https://github.com/cmangos/issues/wiki/Quest_template#chartitleid) | tinyint(3) unsigned | 否 |         | 0          |               |
| [PlayersSlain](https://github.com/cmangos/issues/wiki/Quest_template#playersslain) | tinyint(3) unsigned | 否 |         | 0          | 巫妖王之怒    |
| [BonusTalents](https://github.com/cmangos/issues/wiki/Quest_template#bonustalents) | tinyint(3) unsigned | 否 |         | 0          | 巫妖王之怒    |
| [PrevQuestId](https://github.com/cmangos/issues/wiki/Quest_template#prevquestid) | mediumint(9)        | 否       |         | 0          |               |
| [NextQuestId](https://github.com/cmangos/issues/wiki/Quest_template#nextquestid) | mediumint(9)        | 否       |         | 0          |               |
| [ExclusiveGroup](https://github.com/cmangos/issues/wiki/Quest_template#exclusivegroup) | mediumint(9) | 否       |         | 0          |               |
| [BreadcrumbForQuestId](https://github.com/cmangos/issues/wiki/Quest_template#BreadcrumbForQuestId) | mediumint(9) unsigned | 否 |         | 0          |               |
| [NextQuestInChain](https://github.com/cmangos/issues/wiki/Quest_template#nextquestinchain) | mediumint(8) | 否       |         | 0          |               |
| [RewXPId](https://github.com/cmangos/issues/wiki/Quest_template#rewxpid)       | tinyint(3) unsigned | 否       |         | 0          | 巫妖王之怒    |
| [SrcItemId](https://github.com/cmangos/issues/wiki/Quest_template#srcitemid)   | mediumint(8) unsigned | 否     |         | 0          |               |
| [SrcItemCount](https://github.com/cmangos/issues/wiki/Quest_template#srcitemcount) | tinyint(3)   | 否       |         | 0          |               |
| [SrcSpell](https://github.com/cmangos/issues/wiki/Quest_template#srcspell)     | mediumint(8)        | 否       |         | 0          |               |
| [Title](https://github.com/cmangos/issues/wiki/Quest_template#title)           | text                | 是       |         |            |               |
| [Details](https://github.com/cmangos/issues/wiki/Quest_template#details)       | text                | 是       |         |            |               |
| [Objectives](https://github.com/cmangos/issues/wiki/Quest_template#objectives) | text                | 是       |         |            |               |
| [OfferRewardText](https://github.com/cmangos/issues/wiki/Quest_template#offerrewardtext) | text      | 是       |         |            |               |
| [RequestItemsText](https://github.com/cmangos/issues/wiki/Quest_template#requestitemstext) | text    | 是       |         |            |               |
| [EndText](https://github.com/cmangos/issues/wiki/Quest_template#endtext)       | text                | 是       |         |            |               |
| [ObjectiveText1-4](https://github.com/cmangos/issues/wiki/Quest_template#objectivetext) | text      | 是       |         |            |               |
| [ReqItemId1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqitemid) | mediumint(8) unsigned | 否     |         | 0          |               |
| [ReqItemCount1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqitemcount) | smallint(5) unsigned | 否   |         | 0          |               |
| [ReqSourceId1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqsourceid) | mediumint(8) | 否       |         | 0          |               |
| [ReqSourceCount1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqsourcecount) | smallint(5) | 否       |         | 0          |               |
| [ReqCreatureOrGOId1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqcreatureorgoid) | mediumint(9) | 否 |         | 0          |               |
| [ReqCreatureOrGOCount1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqcreatureorgocount) | int(10) unsigned / smallint(5) unsigned | 否 |         | 0          |               |
| [ReqSpellCast1-4](https://github.com/cmangos/issues/wiki/Quest_template#reqspellcast) | mediumint(8) unsigned | 否 |         | 0          |               |
| [RewChoiceItemId1-6](https://github.com/cmangos/issues/wiki/Quest_template#rewchoiceitemid) | mediumint(8) unsigned | 否 |         | 0          |               |
| [RewChoiceItemCount1-6](https://github.com/cmangos/issues/wiki/Quest_template#rewchoiceitemcount) | smallint(5) unsigned | 否 |         | 0          |               |
| [RewItemId1-4](https://github.com/cmangos/issues/wiki/Quest_template#rewitemid) | mediumint(8) unsigned | 否     |         | 0          |               |
| [RewItemCount1-4](https://github.com/cmangos/issues/wiki/Quest_template#rewitemcount) | smallint(5) unsigned | 否   |         | 0          |               |
| [RewRepFaction1-5](https://github.com/cmangos/issues/wiki/Quest_template#rewrepfaction) | smallint(5) | 否       |         | 0          |               |
| [RewRepValue1-5 / RewRepValueId1-5](https://github.com/cmangos/issues/wiki/Quest_template#rewrepvalue) | mediumint(9) | 否 |         | 0          |               |
| [RewHonorableKills](https://github.com/cmangos/issues/wiki/Quest_template#rewhonorablekills) | int(11)      | 否       |         | 0          |               |
| [RewOrReqMoney](https://github.com/cmangos/issues/wiki/Quest_template#reworreqmoney) | int(11)      | 否       |         | 0          |               |
| [RewMoneyMaxLevel](https://github.com/cmangos/issues/wiki/Quest_template#rewmoneymaxlevel) | int(10) unsigned | 否 |         | 0          |               |
| [RewSpell](https://github.com/cmangos/issues/wiki/Quest_template#rewspell)     | mediumint(8) unsigned | 否     |         | 0          |               |
| [RewSpellCast](https://github.com/cmangos/issues/wiki/Quest_template#rewspellcast) | mediumint(8) unsigned | 否   |         | 0          |               |
| [RewMailTemplateId](https://github.com/cmangos/issues/wiki/Quest_template#rewmailtemplateid) | mediumint(8) unsigned | 否 |         | 0          |               |
| [RewMailDelaySecs](https://github.com/cmangos/issues/wiki/Quest_template#rewmaildelaysecs) | int(11) unsigned | 否 |         | 0          |               |
| [PointMapId](https://github.com/cmangos/issues/wiki/Quest_template#pointmapid) | smallint(5) unsigned | 否       |         | 0          |               |
| [PointX](https://github.com/cmangos/issues/wiki/Quest_template#pointx)         | float                | 否       |         | 0          |               |
| [PointY](https://github.com/cmangos/issues/wiki/Quest_template#pointy)         | float                | 否       |         | 0          |               |
| [PointOpt](https://github.com/cmangos/issues/wiki/Quest_template#pointopt)     | mediumint(8)         | 否       |         |            |               |
| [DetailsEmote1-4](https://github.com/cmangos/issues/wiki/Quest_template#detailsemote) | smallint(5) unsigned | 否 |         | 0          |               |
| [DetailsEmoteDelay1-4](https://github.com/cmangos/issues/wiki/Quest_template#DetailsEmoteDelay) | smallint(5) unsigned | 否 |         | 0          |               |
| [IncompleteEmote](https://github.com/cmangos/issues/wiki/Quest_template#incompleteemote) | smallint(5) unsigned | 否 |         | 0          |               |
| [CompleteEmote](https://github.com/cmangos/issues/wiki/Quest_template#completeemote) | smallint(5) unsigned | 否 |         | 0          |               |
| [OfferRewardEmote1-4](https://github.com/cmangos/issues/wiki/Quest_template#offerrewardemote) | smallint(5) unsigned | 否 |         | 0          |               |
| [OfferRewardEmoteDelay1-4](https://github.com/cmangos/issues/wiki/Quest_template#OfferRewardEmoteDelay) | smallint(5) unsigned | 否 |         | 0          |               |
| [StartScript](https://github.com/cmangos/issues/wiki/Quest_template#startscript) | mediumint(8) unsigned | 否     |         | 0          |               |
| [CompleteScript](https://github.com/cmangos/issues/wiki/Quest_template#completescript) | mediumint(8) unsigned | 否   |         | 0          |               |

**字段描述**

**entry**
任务ID。任务ID是表的主键。每个任务ID必须是唯一的！

**Method**
接受的值：0、1或2。如果**值=0**，则任务自动完成（跳过目标/详细内容）。

**ZoneOrSort**
此字段定义任务在任务日志中属于哪个类别。

如果**值>0**，则值是区域ID，取自[AreaTable.dbc](https://github.com/cmangos/issues/wiki/AreaTable.dbc)。

如果**值<0**，则(**-值**)是任务排序ID：（通常是专业或职业任务。另见[RequiredSkillValue](https://github.com/cmangos/issues/wiki/quest_template#RequiredSkillValue)）值来自QuestSort.dbc。[QuestSort.dbc](https://github.com/cmangos/issues/wiki/QuestSort.dbc)

**RequiredSkill**
此字段定义角色可用任务所需的任何特定技能要求。

如果**值>0**，则值是技能ID（参见SkillLine.dbc）

**MinLevel**
接受任务所需的最低等级。

**QuestLevel**
任务等级。只有当玩家等级小于或等于任务等级+5时，玩家才能获得全额经验值。

如果任务等级=-1，任务使用当前玩家等级作为其等级。

**Type**
这些值是取自QuestInfo.dbc的ID

| ID   | 名称             |
| ---- | ---------------- |
| 1    | 组队/"精英"      |
| 21   | 生命             |
| 41   | PvP              |
| 62   | 团队             |
| 81   | 地下城           |
| 82   | 世界事件         |
| 83   | 传说             |
| 84   | 护送             |
| 85   | 英雄             |

**RequiredClasses**
接受任务所需的职业。0表示对所有职业可用。字段值是一个十进制值，必须转换为8位二进制才能理解。在二进制形式中，每个不同的位代表来自[CharClasses.dbc](https://github.com/cmangos/issues/wiki/CharClasses.dbc)的不同职业

| **值** | **ID** | **名称**       |
| ------ | ------ | -------------- |
| 1      | 1      | 战士           |
| 2      | 2      | 圣骑士         |
| 4      | 3      | 猎人           |
| 8      | 4      | 潜行者         |
| 16     | 5      | 牧师           |
| 32     | 6      | 死亡骑士       |
| 64     | 7      | 萨满祭司       |
| 128    | 8      | 法师           |
| 256    | 9      | 术士           |
| 1024   | 11     | 德鲁伊         |

**RequiredRaces**
接受任务所需的种族。0表示对所有种族可用。字段值是一个十进制值，必须转换为8位二进制才能理解。在二进制形式中，每个不同的位代表不同的种族。分配如下：

这些值是来自[CharRaces.dbc](https://github.com/cmangos/issues/wiki/CharRaces.dbc)的2^ID

| **值** | **名称**               |
| ------ | ---------------------- |
| 0      | 所有种族               |
| 1      | 人类                   |
| 2      | 兽人                   |
| 4      | 矮人                   |
| 8      | 暗夜精灵               |
| 16     | 亡灵                   |
| 32     | 牛头人                 |
| 64     | 侏儒                   |
| 77     | 联盟任务（经典旧世）   |
| 128    | 巨魔                   |
| 178    | 部落任务（经典旧世）   |
| 256    | 地精                   |
| 512    | 血精灵                 |
| 690    | 部落任务（直至大灾变） |
| 1024   | 德莱尼                 |
| 1101   | 联盟任务（直至大灾变） |
| 2097152| 狼人                   |

**RequiredSkillValue**
如果[ZoneOrSort](https://github.com/cmangos/issues/wiki/quest_template#ZoneOrSort)字段<0并且具有某些技能相关值，则对技能的玩家技能值要求。

**RequiredCondition**

**RepObjectiveFaction**
需要达到特定声望值的阵营目标ID。参见[Faction.dbc](https://github.com/cmangos/issues/wiki/Faction.dbc)

**RepObjectiveValue**
玩家必须与[RepObjectiveFaction](https://github.com/cmangos/issues/wiki/quest_template#RepObjectiveFaction)中的阵营达到的声望值，作为任务目标的一部分。

**RequiredMinRepFaction**
声望要求的阵营ID。参见[Faction.dbc](https://github.com/cmangos/issues/wiki/Faction.dbc)

**RequiredMinRepValue**
玩家必须拥有此声望或更高声望才能接受任务。

| **值**  | **声望等级** |
| ------- | ------------ |
| 42000   | 崇拜         |
| 21000   | 崇敬         |
| 9000    | 尊敬         |
| 3000    | 友好         |
| 0       | 中立         |
| -3000   | 冷淡         |
| -6000   | 敌对         |
| -42000  | 仇恨         |

**RequiredMaxRepFaction**
控制玩家可以拥有并仍能获得任务的最大声望值的阵营ID。参见[Faction.dbc](https://github.com/cmangos/issues/wiki/Faction.dbc)

**RequiredMaxRepValue**
玩家可以与阵营拥有并仍能获得任务的最大声望值。如果玩家拥有比此字段中的值更多的声望，则将无法再接受该任务。

**SuggestedPlayers**
关于应该有多少玩家联合完成此任务的信息。

**LimitTime**
玩家完成此任务的时间限制（以秒为单位）。

**QuestFlags**
此标志字段更具体地定义了任务的类型。除了日常标志和可共享标志外，此字段仅用于分组目的，不用于任何其他任务要求。任务要求是根据任务模板其他字段中的非零值计算的。此外，虽然其中一些标志是已知的，但其他标志的用途尚不清楚，下面的评论只是对它们的猜测。

| **位** | **十六进制** | **名称**                     | **注释**                               |
| ------ | ------------ | ---------------------------- | -------------------------------------- |
| 0      | 0×00000000   | 任务标志_无                  | 无标志，因此没有为此任务分配组         |
| 1      | 0×00000001   | 任务标志_保持存活            | 如果玩家死亡，任务失败                 |
| 2      | 0×00000002   | 任务标志_队伍接受            | 护送任务或任何其他事件驱动的任务。如果玩家在队伍中，所有可以接受此任务的玩家将收到确认框以接受它 |
| 4      | 0×00000004   | 任务标志_探索                | 涉及激活区域触发器                     |
| 8      | 0×00000008   | 任务标志_可共享              | 允许任务与其他玩家共享                 |
| 16     | 0×00000010   | 任务标志_无2                 | 此时未知且未使用                       |
| 32     | 0×00000020   | 任务标志_史诗                |                                        |
| 64     | 0×00000040   | 任务标志_团队                |                                        |
| 128    | 0×00000080   | 任务标志_燃烧的远征          | 随燃烧的远征或之后添加                 |
| 256    | 0×00000100   | 任务标志_无经验金钱          |                                        |
| 512    | 0×00000200   | 任务标志_隐藏奖励            | 物品和金钱奖励在初始任务详细信息页面和任务日志中隐藏，但将在准备奖励时出现 |
| 1024   | 0×00000400   | 任务标志_自动奖励            | 这些任务在任务完成时自动奖励           |
| 2048   | 0×00000800   | 任务标志_燃烧的远征种族      | 血精灵/德莱尼起始区域任务              |
| 4096   | 0×00001000   | 任务标志_日常                | 日常可重复任务（核心应用特定行为的唯一标志） |
| 8192   | 0×00002000   | 任务标志_PvP                 |                                        |
| 16384  | 0×00004000   | 任务标志_不可用              |                                        |
| 32768  | 0×00008000   | 任务标志_每周                |                                        |
| 65536  | 0×00010000   | 任务标志_自动完成            |                                        |
| 131072 | 0×00020000   | 任务标志_在追踪器中显示      |                                        |
| 262144 | 0×00040000   | 任务标志_目标文本            |                                        |
| 524288 | 0×00080000   | 任务标志_自动接受            | 起始区域——仅限巫妖王之怒               |

与所有基于标志的字段一样，可以为不同类型的任务添加**QuestFlags**。

**SpecialFlags**
此字段是一个位掩码，仅控制两个额外要求，只有4个可能的值。

- 0：无额外要求
- 1：使任务可重复。
- 2：使任务只能通过某些外部事件完成（例如[areatrigger_involvedrelation](https://github.com/cmangos/issues/wiki/areatrigger_involvedrelation)中的条目、法术效果任务完成或[spell_scripts](https://github.com/cmangos/issues/wiki/spell_scripts)中命令7的条目等示例）
- 3：既可重复又只能通过外部事件完成
- 4：任务在月初为玩家重置（必须与特殊标志1（可重复）结合使用）

**CharTitleId**
完成任务后角色将获得的头衔。参见CharTitles.dbc

**PlayersSlain**

**BonusTalents**

**PrevQuestId**
**如果值>0：**包含必须先完成的前置任务ID，然后才能开始此任务。
**如果值<0：**包含必须先激活的父任务ID，然后才能开始此任务。
参见[示例部分](https://github.com/cmangos/issues/wiki/quest_template#Examples)的示例。

**NextQuestId**
**如果值>0：**包含下一个任务ID，如果该任务的PrevQuestId不够。
**如果值<0：**包含子任务ID，如果该任务的PrevQuestId不够。如果任务有许多替代下一个任务（从单个非职业特定任务引导的职业特定任务），下一个任务中的PrevQuestId字段可用于设置此依赖关系。
参见[示例部分](https://github.com/cmangos/issues/wiki/quest_template#Examples)的示例。

**ExclusiveGroup**
**如果ExclusiveGroup>0**
允许定义一组任务，其中只能选择一个并完成。例如，如果只能选择任务1200、1201和1202中的一个，则将1200插入所有3个任务的ExclusiveGroup中。
**如果ExclusiveGroup<0**
允许定义一组任务，其中所有任务都必须完成并奖励才能开始下一个任务。例如，如果任务1000依赖于任务1200、1201和1202中的一个，并且所有这些任务具有相同的负互斥组，则所有这些任务必须完成并奖励，然后才能开始任务1000。
参见[示例部分](https://github.com/cmangos/issues/wiki/quest_template#Examples)的示例。

**BreadcrumbForQuestId**
引导到其他任务的面包屑任务。

**NextQuestInChain**
来自**生物**或**游戏对象**的任务条目，结束一个任务并开始一个新任务。结果是，如果你结束任务，新任务会立即从任务给予者处出现。
参见[示例部分](https://github.com/cmangos/issues/wiki/quest_template#Examples)的示例。

**RewXPId**
用于[QuestXP.dbc](https://github.com/cmangos/issues/wiki/QuestXP.dbc)的奖励经验索引。
该DBC文件为每个[QuestLevel](https://github.com/cmangos/issues/wiki/quest_template#QuestLevel)列出了9种不同的经验值（从0到8）。此字段在其中选择正确的数量。截至3.3.5a，RewXPId索引0表示所有任务等级都没有经验。

**SrcItemId**
任务开始时任务给予者给予的物品ID。放弃任务时物品将被删除。

**SrcItemCount**
给予的物品数量。

**SrcSpell**
任务开始时对玩家施放的法术。可以是增益效果或学习法术。

**Title**
任务的标题。

**Details**
任务文本。你可以使用某些占位符，这些占位符将在游戏中填充：--换行，--名称，--种族，--职业，:女性;（男性和女性可以替换为你想要的任何同义词，但顺序必须保持不变。例如：男孩:女孩/男人:女人/先生:女士/家伙:姑娘）

**Objectives**
任务的目标。如果为空，则任务是一个自动完成的任务，可以立即完成而无需先接受。

**OfferRewardText**
完成任务时NPC发送给玩家的第一个文本。你可以使用某些占位符，这些占位符将在游戏中填充：--换行，--名称，--种族，--职业，:女性;（男性和女性可以替换为你想要的任何同义词，但顺序必须保持不变。例如：男孩:女孩/男人:女人/先生:女士/家伙:姑娘）

**RequestItemsText**
当玩家尝试与拥有活动但未完成任务的NPC交谈时发送给玩家的文本。（Wowhead中"进度"标题下的文本。）你可以使用某些占位符，这些占位符将在游戏中填充：--换行，--名称，--种族，--职业，:女性;（男性和女性可以替换为你想要的任何同义词，但顺序必须保持不变。例如：男孩:女孩/男人:女人/先生:女士/家伙:姑娘）

**EndText**
仅当[SpecialFlags](https://github.com/cmangos/issues/wiki/quest_template#SpecialFlags)2激活时使用。这是发送给玩家的目标文本，描述了完成任务所需的外部事件。

**ObjectiveText**
用于定义非标准目标文本，这些文本显示在任务日志中。例如，"治疗倒下的战士"，数字通过计数值添加。

**ReqItemId**
完成任务所需物品的item_template ID。

**ReqItemCount**
所需物品的数量

**ReqSourceID**
任务间接需要的物品ID。例如，任务要求物品X，但获得物品X的唯一方法是激活物品Y；然而，物品Y也是任务物品。因此，你在此字段中设置物品Y的ID。此要求不会出现在任务文本中，它只是为了让核心知道何时掉落不在ReqItemID字段中但仍由任务需要的任务物品。

**ReqSourceCount**
可以拾取（并由核心掉落）的ReqSourceID中物品副本的最大数量。\
将此值设置为0意味着物品堆叠大小将是核心掉落的最大数量。

**ReqCreatureOrGOId**
**值>0：**玩家需要杀死/施放以完成任务的所需creature_template ID。
**值<0：**玩家需要施放以完成任务的所需gameobject_template ID。
如果**ReqSpellCast**!=0，目标是施放在目标上，否则是杀死。
注意：如果ReqSpellCast!=0且法术具有发送事件或任务完成效果，则此字段可能留空。

**ReqCreatureOrGOCount**
必须杀死或施放在生物或游戏对象上的次数。

**ReqSpellCast**
需要施放以满足任务目标的法术ID。法术通常需要一个目标，即[ReqCreatureOrGOId](https://github.com/cmangos/issues/wiki/quest_template#ReqCreatureOrGOId)
对于具有"法术效果与ImpliciteTargetA-B==38"的法术，检查表[Spell_script_target](https://github.com/cmangos/issues/wiki/Spell_script_target)
注意：如果法术具有法术效果发送事件或任务完成，它可以在这里输入，而不需要目标和计数。

**RewChoiceItemId, RewChoiceItemCount**
可用于奖励选择的物品ID。
可用奖励物品中的充能次数。

**RewItemId, RewItemCount**
奖励物品数量
给予奖励的物品ID（无选择）。

**RewRepFaction**
任务给予声望点的阵营ID（来自[Faction.dbc](https://github.com/cmangos/issues/wiki/Faction.dbc)）。

**RewRepValue,**
完成任务时阵营获得或失去的声望点数。这是特殊的声望奖励。对任务奖励生物阵营的正常声望奖励会自动计算和添加。
在巫妖王之怒中，RewRepValueId指向QuestFactionReward.dbc

| 值    | 声望        |
| ----- | ----------- |
| 0     | 0           |
| +-1   | 10 / -10    |
| +-2   | 25 / -25    |
| +-3   | 75 / -75    |
| +-4   | 150 / -150  |
| +-5   | 250 / -250  |
| +-6   | 350 / -350  |
| +-7   | 500 / -500  |
| +-8   | 1000 / -1000|
| +-9   | 5 / -5      |

**RewHonorableKills**
完成此任务奖励的荣誉击杀荣誉数量。
示例：任务8388的示例值为15：在70级时，一个荣誉击杀价值20.9荣誉。将其乘以15，你得到313.5，乘法后该值向上取整。因此，70级时此任务奖励的荣誉为314。

**RewOrReqMoney**
完成任务赚取的金钱（如果值>0）。任务金钱要求（如果值<0）。

**RewMoneyMaxLevel**
80级角色完成此任务时将获得的金钱。此字段还控制给予的经验值，因为经验值是通过以下公式从此字段中的值计算的。如果任务可重复，经验值将只给予一次。角色将获得的总经验值还受角色等级与任务等级之间的等级差异影响。
从此字段中的值计算经验值的公式：
**任务等级>=65：**经验值=RewMoneyMaxLevel/6.0
**任务等级==64：**经验值=RewMoneyMaxLevel/4.8
**任务等级==63：**经验值=RewMoneyMaxLevel/3.6
**任务等级==62：**经验值=RewMoneyMaxLevel/2.4
**任务等级==61：**经验值=RewMoneyMaxLevel/1.2
**任务等级<=60：**经验值=RewMoneyMaxLevel/0.6

**RewSpell**
任务日志中显示在完成任务时施放的法术。注意，如果[RewSpellCast](https://github.com/cmangos/issues/wiki/quest_template#RewSpellCast)非零，则此法术将**不会**施放。将改为施放另一个字段中的法术，在这种情况下，此处的法术仅用作任务日志中的视觉效果。
注意：此字段直接来自WDB，不应更改。

**RewSpellCast**
完成任务时始终对玩家施放的法术。这可以是学习法术，玩家因此学习了一些法术，或者是增益法术，例如。如果此字段非零，则此法术将**始终**施放，而[RewSpell](https://github.com/cmangos/issues/wiki/quest_template#RewSpell)中的法术将不会。
注意：此字段直接来自WDB，不应更改。

**RewMailTemplateId**
如果任务奖励来自可能物品列表中的物品，则此处的ID对应于[quest_mail_loot_template](https://github.com/cmangos/issues/wiki/quest_mail_loot_template)中的适当战利品模板。根据该战利品模板中的规则，"掉落"的物品将在任务完成时通过邮件发送。

**RewMailDelaySecs**
在将邮件发送给提交任务的角色之前等待的秒数，该任务奖励来自[RewMailTemplateId](https://github.com/cmangos/issues/wiki/quest_template#RewMailTemplateId)中定义的战利品模板的物品。

**PointMapId**
任务兴趣点（POI——兴趣点）的地图ID。当任务活动时，POI将显示在地图上。

**PointX**
任务POI的X坐标。

**PointY**
任务POI的Y坐标。

**PointOpt**

**DetailsEmote**
在你查看任务详细信息并点击"接受"按钮之前，相关NPC播放的表情。\
这可以在嗅探包中的SMSG_QUEST_GIVER_QUEST_DETAILS数据包中找到。

**DetailsEmoteDelay**
从此DetailsEmote之前的上一个DetailsEmote开始的延迟（以毫秒为单位）\
这可以在嗅探包中的SMSG_QUEST_GIVER_QUEST_DETAILS数据包中找到。

**IncompleteEmote**
当你查看任务详细信息且一个或多个任务目标尚未完成时，相关NPC播放的表情。

**CompleteEmote**
在所有任务对象完成时，相关NPC播放的表情。\
这可以在嗅探包中的SMSG_QUEST_GIVER_REQUEST_ITEMS数据包中找到。

**OfferRewardEmote**
角色获得任务奖励时NPC播放的表情。\
这可以在嗅探包中的SMSG_QUEST_GIVER_OFFER_REWARD_MESSAGE数据包中找到。

**OfferRewardEmoteDelay**
从此OfferRewardEmote之前的上一个OfferRewardEmote开始的延迟（以毫秒为单位）\
这可以在嗅探包中的SMSG_QUEST_GIVER_OFFER_REWARD_MESSAGE数据包中找到。

**StartScript**
开始脚本的ID。参见[DBScripts.id](https://github.com/cmangos/issues/wiki/DBScripts#id)

**CompleteScript**
结束脚本的ID。参见[DBScripts.id](https://github.com/cmangos/issues/wiki/DBScripts#id)

**示例**

**处理任务的"交战规则"**

1. 始终在使用NextQuestId之前使用PrevQuestId。NextQuestId被认为是可选的，仅在PrevQuestId不够时使用

**基本任务**

*单个独立任务，无先决条件*

    *questA*

PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0        entry = questA

*当此任务需要另一个任务被奖励时*

    *questA*

PrevQuestId = questX   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0        entry = questA

**任务链**

*玩家按特定顺序完成任务的严格链。*

    *questA*
        |
    *questB*
        |
    *questC*
        |
    *questD*

PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questB    entry = questA
PrevQuestId = questA   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questC    entry = questB
PrevQuestId = questB   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questD    entry = questC
PrevQuestId = questC   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0         entry = questD

**具有多个起始任务的任务链。**

*玩家应该只被允许完成三个可能中的一个*

    *questA*    *questB*    *questC*
        \          |          /
         ------ *questD* -----
                   |
                *questE*

PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questA
PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questB
PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questC
PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = questE    entry = questD
PrevQuestId = questD   NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = 0         entry = questE

**具有多个起始任务的任务链。**

*玩家必须完成所有三个初始任务，然后D才可用*

    *questA*    *questB*    *questC*
        \          |          /
         ------ *questD* -----
                   |
                *questE*

PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questA
PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questB
PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questC
PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = questE    entry = questD
PrevQuestId = questD   NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = 0         entry = questE

**具有拆分和子任务的任务**

*完成A解锁B和C，可以同时完成。两者都需要在D可用之前完成。X需要获得C的物品，并且此任务应仅在C活动时可用*

                *questA*
                  /    \ 
          *questB*      *questC* <-> *questX*
                  \    /
                 *questD*

PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questA
PrevQuestId = questA   NextQuestId = questD   ExclusiveGroup = -questB   NextQuestInChain = 0        entry = questB
PrevQuestId = questA   NextQuestId = questD   ExclusiveGroup = -questB   NextQuestInChain = 0        entry = questC
PrevQuestId = -questC  NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questX
PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questD

**多个任务链，导向一个最终任务**

*玩家可以完成（不需要）X，但必须在最终任务可用之前完成所有三个任务链*

                *questX*
                   |
    *questA*    *questC*    *questE*
       |           |            |
    *questB*    *questD*    *questF*
       \           |           /
         ------ *questG* -----

PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questC    entry = questX

PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questB    entry = questA
PrevQuestId = questA   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questB
PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questD    entry = questC
PrevQuestId = questC   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questD
PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questF    entry = questE
PrevQuestId = questE   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questF

PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questG

**复杂**

*玩家必须先完成A，然后B以解锁从C到E的链。还将解锁组中的三个其他任务，这些任务可以同时完成。三个分组任务必须全部在I可用之前完成。完成E和I是获得最终任务所必需的。*

                *questA*
                   |
                *questB*
              /          \
          *questC*     *questF*    
             |         *questG*
          *questD*     *questH*
             |            |
          *questE*     *questI*
              \          /
                *questJ*

PrevQuestId=0 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=任务B entry=任务A

PrevQuestId=任务A NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务B

PrevQuestId=任务B NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=任务D entry=任务C

PrevQuestId=任务C NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=任务E entry=任务D

PrevQuestId=任务D NextQuestId=任务J ExclusiveGroup=-任务E NextQuestInChain=0 entry=任务E

PrevQuestId=任务B NextQuestId=任务I ExclusiveGroup=-任务F NextQuestInChain=0 entry=任务F

PrevQuestId=任务B NextQuestId=任务I ExclusiveGroup=-任务F NextQuestInChain=0 entry=任务G

PrevQuestId=任务B NextQuestId=任务I ExclusiveGroup=-任务F NextQuestInChain=0 entry=任务H

PrevQuestId=0 NextQuestId=任务J ExclusiveGroup=-任务E NextQuestInChain=0 entry=任务I

PrevQuestId=0 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务J

**不可能——许多任务可能解锁许多**

*玩家可以在两个替代链之间选择（链A或B，但不是两个链）。A2或B2应该在完成时解锁C、D和E。当所有三个完成时，F应该被解锁。如果玩家在完成F后获得A3或B3，取决于选择链A还是B。*

                *questA1*          *questB1*
                    |                  |
                *questA2*          *questB2*
                    \                 /
                      --- *questC* ---
                          *questD*
                          *questE*
                             |
                          *questF*
                         /        \
                *questA3*          *questB3*

PrevQuestId=0 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=任务A2 entry=任务A1

PrevQuestId=任务A1 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务A2

PrevQuestId=0 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=任务B2 entry=任务B1

PrevQuestId=任务B1 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务B2

PrevQuestId=0 NextQuestId=任务F ExclusiveGroup=-任务C NextQuestInChain=0 entry=任务C

PrevQuestId=0 NextQuestId=任务F ExclusiveGroup=-任务C NextQuestInChain=0 entry=任务D

PrevQuestId=0 NextQuestId=任务F ExclusiveGroup=-任务C NextQuestInChain=0 entry=任务E

PrevQuestId=0 NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务F

PrevQuestId=任务F NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务A3

PrevQuestId=任务F NextQuestId=0 ExclusiveGroup=0 NextQuestInChain=0 entry=任务B3

*注意：如果玩家可以在链A或B之间选择，可能由阵营状态（奥尔多或占星者）决定，使用ReqMinRepFaction=1。玩家不应该能够同时与两者保持中立+1。这可能是获得奥尔多或占星者任务的共同阈值（这不确定）。如果是这种情况，只有在完成A2或B2后解锁C、D和E是不可能的。*