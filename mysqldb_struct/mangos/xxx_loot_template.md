**`*_loot_template` 表**

**概述**

从字面意思来看，“loot”这个词的含义很适合描述尸体掉落，也可能适合一些游戏对象（比如宝箱），但对于钓鱼“掉落”则不太合适。不过没关系。我们将在这里使用术语“掉落”表示“为玩家在一个事件中生成的一组物品”，而“掉落定义”表示“用于生成掉落物品的一组规则”。暂时先忘掉词汇学吧。

这种表格式用于11个不同的表，为不同的事物生成不同的掉落物品。这11个表分别是：
creature_loot_template, disenchant_loot_template, fishing_loot_template,
gameobject_loot_template, item_loot_template,
pickpocketing_loot_template, prospecting_loot_template,
skinning_loot_template, quest_mail_loot_template,
reference_loot_template, milling_loot_template。这里的通用描述对所有11个表都有效，因为掉落系统对这11个表都是一样的。

掉落模板仅定义掉落中的物品。关于尸体、偷窃和行李（ luggage ）中的金钱掉落的评论，请参见 [creature_template](https://github.com/cmangos/issues/wiki/creature_template) 和 [item_template](https://github.com/cmangos/issues/wiki/item_template)。

**结构**

| **字段**                                                                                       | **类型**                 | **Null** | **Key** | **默认值** | **额外** |
| :---------------------------------------------------------------------------------------------- | :----------------------- | :------- | :------ | :--------- | :------- |
| [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)                               | mediumint unsigned       | NO       | PRI     | 0          |          |
| [item](https://github.com/cmangos/issues/wiki/Loot_template#item)                                 | mediumint unsigned       | NO       | PRI     | 0          |          |
| [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/Loot_template#chanceorquestchance)   | float                    | NO       |         | 100        |          |
| [groupid](https://github.com/cmangos/issues/wiki/Loot_template#groupid)                           | tinyint                  | NO       |         | 0          |          |
| [mincountOrRef](https://github.com/cmangos/issues/wiki/Loot_template#mincountorref)               | mediumint                | NO       |         | 1          |          |
| [maxcount](https://github.com/cmangos/issues/wiki/Loot_template#maxcount)                         | tinyint unsigned         | NO       |         | 1          |          |
| [condition_id](https://github.com/cmangos/issues/wiki/Loot_template#condition_id)                 | mediumint(8) unsigned    | NO       |         | 0          |          |

**关联关系**

这11个表与其他数据库表有不同的关联关系。

| **掉落表**                | **字段**                                                            | **关联关系**      | **关联表**                                                                 | **字段**                                                                         | **注释**                                                                                                                                                                                                          |
| :------------------------- | :------------------------------------------------------------------- | :---------------- | :------------------------------------------------------------------------- | :------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fishing_loot_template      | 无关联                                                               | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry) 关联于钓鱼区域或地区的ID |                                                                              |                                                                                  |                                                                                                                                                                                                                   |
| spell_loot_template        | 无关联                                                               | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry) 关联于法术的ID |                                                                              |                                                                                  |                                                                                                                                                                                                                   |
| creature_loot_template     | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | [creature_template](https://github.com/cmangos/issues/wiki/Creature_template) | [lootid](https://github.com/cmangos/issues/wiki/Creature_template#lootid)        |                                                                                                                                                                                                                   |
| gameobject_loot_template   | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | [gameobject_template](https://github.com/cmangos/issues/wiki/Gameobject_template) | [data1](https://github.com/cmangos/issues/wiki/Gameobject_template#data0-23)     | 只有 GAMEOBJECT_TYPE_CHEST (3) 或 GAMEOBJECT_TYPE_FISHINGHOLE (25) 使用 data1 作为掉落ID，对于其他类型，data1 用于其他用途                                                                                        |
| item_loot_template         | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 一          | [item_template](https://github.com/cmangos/issues/wiki/Item_template)         | [entry](https://github.com/cmangos/issues/wiki/Item_template#entry)              |                                                                                                                                                                                                                   |
| disenchant_loot_template   | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | [item_template](https://github.com/cmangos/issues/wiki/Item_template)         | [disenchantid](https://github.com/cmangos/issues/wiki/Item_template#disenchantid) |                                                                                                                                                                                                                   |
| prospecting_loot_template  | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 一          | [item_template](https://github.com/cmangos/issues/wiki/Item_template)         | [entry](https://github.com/cmangos/issues/wiki/Item_template#entry)              |                                                                                                                                                                                                                   |
| milling_loot_template      | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 一          | [item_template](https://github.com/cmangos/issues/wiki/Item_template)         | [entry](https://github.com/cmangos/issues/wiki/Item_template#entry)              |                                                                                                                                                                                                                   |
| pickpocketing_loot_template | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | [creature_template](https://github.com/cmangos/issues/wiki/Creature_template) | [pickpocketloot](https://github.com/cmangos/issues/wiki/Creature_template#pickpocketloot) |                                                                                                                                                                                                                   |
| skinning_loot_template     | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | [creature_template](https://github.com/cmangos/issues/wiki/Creature_template) | [skinloot](https://github.com/cmangos/issues/wiki/Creature_template#skinloot)    | 也可以存储从生物身上采集的可挖掘/可采集草药物品                                                                                                                                                                     |
| mail_loot_template         | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  |                   | [quest_template](https://github.com/cmangos/issues/wiki/Quest_template)       | [RewMailTemplateId](https://github.com/cmangos/issues/wiki/Quest_template#rewmailtemplateid) |                                                                                                                                                                                                                   |
| reference_loot_template    | [entry](https://github.com/cmangos/issues/wiki/Loot_template#entry)  | 多 <- 多          | \* \_loot_template                                                           | [-mincountOrRef](https://github.com/cmangos/issues/wiki/Loot_template#mincountorref) | 当 mincountOrRef 为负值时                                                                                                                                                                                         |

**字段描述**

**entry**

掉落定义（掉落模板）的ID。具有相同ID的行定义了一个单一的掉落。
它通常与掉落来源（物品、生物等）的ID相同，但是当[关联](https://github.com/cmangos/issues/wiki/loot_template#Relations)不是基于关联表的 **entry** 字段建立时，ID可能会不同。例如，当多个掉落来源应该提供相同的掉落时，可以使用单一的掉落定义。在这种情况下，掉落来源在链接字段中具有相同的值。

也可以设置**人工掉落模板**，这些模板完全不直接使用，因为它们的ID没有被相关来源引用。这样的“支持模板”可以从“正常”掉落模板中被[引用](https://github.com/cmangos/issues/wiki/loot_template#Template_reference)。

当使用通用或人工掉落模板时，会出现一个问题：该模板应使用什么ID？根据不同的掉落表，可以约定不同的规则以简化表的维护。此外，这样的规则会非常方便，但目前似乎很少有明确定义的规则。

关于 **entry** 字段值的约定在[这里](https://github.com/cmangos/issues/wiki/loot_template#Agreements)描述。

**item**

可以包含在掉落中的物品的[模板ID](https://github.com/cmangos/issues/wiki/item_template#entry)。

注意：对于[引用条目](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef)，此字段没有意义，并且核心不以任何方式使用它。然而，由于主键是 entry + item 的组合，对于每个引用条目，此字段仍然需要是一个唯一的数字，以免产生索引冲突。

**ChanceOrQuestChance**

该字段的含义根据其符号以及 [mincountOrRef](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef) 的符号而有所不同：

**普通条目**

**ChanceOrQuestChance** > 0, [mincountOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#mincountorref) > 0

**ChanceOrQuestChance** 的绝对值（实际上就是其值，因为在这种情况下它是正数）表示物品掉落的百分比几率。允许任何浮点数，但实际上任何大于100的值都会产生与100相同的结果。

**任务掉落**

**ChanceOrQuestChance** < 0, [mincountOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#mincountorref) > 0

与[普通条目](https://github.com/cmangos/issues/wiki/loot_template#Plain_entry)一样，**ChanceOrQuestChance** 的绝对值表示物品掉落的百分比几率。但此外，负的 **ChanceOrQuestChance** 会通知核心，该物品只应对拥有相应任务的角色显示。这意味着即使物品掉落了，玩家也必须在掉落中看到它，玩家必须至少有一个[任务](https://github.com/cmangos/issues/wiki/quest_template)，该任务的 [ReqItemIdN](https://github.com/cmangos/issues/wiki/quest_template#ReqItemId) 字段或 [ReqSourceIdN](https://github.com/cmangos/issues/wiki/quest_template#ReqSourceId) 字段中包含该[物品ID](https://github.com/cmangos/issues/wiki/loot_template#item)。玩家还必须拥有少于 [ReqItemCountN](https://github.com/cmangos/issues/wiki/quest_template#ReqItemCount) 或 [ReqSourceCountN](https://github.com/cmangos/issues/wiki/quest_template#ReqSourceCount) 的物品副本。

**几率引用**

[mincountOrRef](https://github.com/cmangos/issues/wiki/loot_template#mincountorref) < 0

对于负的 [mincountOrRef](https://github.com/cmangos/issues/wiki/loot_template#mincountorref)（*引用条目*），**ChanceOrQuestChance** 表示引用被使用的百分比几率。因此，它与[普通条目](https://github.com/cmangos/issues/wiki/loot_template#Plain)的含义非常相似，只是要注意，如果几率未命中，整个引用将被跳过。

负值和零值对于这种情况没有意义，不能使用。

**通用备注**

**ChanceOrQuestChance** 的零值仅对[分组条目](https://github.com/cmangos/issues/wiki/loot_template#groupid)允许。

掉落定义中（非零的）**ChanceOrQuestChance** 值在掉落生成过程中，对于引用和非引用条目，会乘以 RATE_DROP_ITEMS（mangos 配置设置），但对于分组条目则不会。

**groupid**

组是一组掉落定义，其处理方式是在任何给定的掉落事件中，生成的掉落只能从该组中定义的物品中获得1件（或0件）[物品](https://github.com/cmangos/issues/wiki/loot_template#item)。组由具有相同 [entry](https://github.com/cmangos/issues/wiki/loot_template#entry) 和 **groupid** 字段值 **并且** **MinCountOrRef > 0** 的掉落定义形成。

一个组可以由**明确几率**（具有非零 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance)）和**均等几率**（[ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance) = 0）的条目组成。组中的每个*均等几率*条目被认为具有这样的几率：

- 所有均等几率条目具有相同的几率
- **组几率**（所有条目几率之和）为100%

当然，组可以由以下组成：
- 仅明确几率条目，或
- 仅均等几率条目，或
- 两种类型的条目。

理解什么是组的最简单方法是理解核心如何处理分组条目：

在加载时：
- 组被形成——所有具有相同 **groupid** 和 **entry** 字段值的分组条目被收集到两个集合中——一个用于明确几率条目，一个用于均等几率条目。请注意，集合中条目的顺序不能由数据库定义——你应该假设条目处于未知顺序。但实际上，每次核心处理一个组时，条目都处于某种顺序，该顺序在处理过程中是恒定的。

在掉落生成期间：
- 核心为明确几率条目（如果有的话）进行掷骰：
  - 在0到100（浮点值）范围内掷出一个随机数 **R**。
  - 检查组中的每个（明确几率）条目的掉落几率：
    - 如果 **R** 小于该条目的 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance) 的绝对值，则该条目“获胜”：该[物品](https://github.com/cmangos/issues/wiki/loot_template#item)被包含在掉落中。组处理停止，组中剩余的条目被跳过。
    - 否则该条目“失败”：该[物品](https://github.com/cmangos/issues/wiki/loot_template#item)失去了进入掉落的机会。**R** 减去该条目的 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance) 的绝对值，然后检查下一个明确几率条目。
- 如果没有明确几率条目获得机会，则处理均等几率部分（如果有的话）：
  - 从均等几率条目集合中随机选择一个条目，并将相应的[物品](https://github.com/cmangos/issues/wiki/loot_template#item)包含在掉落中。
- 如果尚未选择任何物品（如果组中有一些均等几率条目，则这种情况永远不会发生）——则没有来自该组的物品被包含在掉落中。

让我们使用术语**组几率**作为组中所有条目的 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance)（绝对值）的总和。请注意，即使只有一个均等几率条目，也会使组几率达到100%（前提是明确几率的和不超过100%）。

如果你理解了这个过程，你就能理解结果：
- 在任何给定时间，一个组中最多只能掉落一件物品。
- 如果**组几率**至少为100，那么肯定会掉落一件物品。
- 如果*组几率*不超过100，那么组条目中定义的每件物品的掉落几率*正好*是其在 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance) 中设置的几率。
- 如果*组几率*大于100，那么无论掷出的 **R** 值是多少，某些条目将会失去一部分机会（甚至根本不会被检查——所有均等几率条目都会如此）。因此，对于某些物品，掉落几率将小于其 [ChanceOrQuestChance](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance)。这*非常*糟糕，这就是为什么严格禁止*组几率* > 100。
- 处理*均等几率*部分比处理*明确几率*部分花费的时间少得多。因此，在可能的情况下，建议使用均等几率组。

现在，组的基本应用很清楚了：
- *组几率*为100%的组每次都会生成**正好一件**[物品](https://github.com/cmangos/issues/wiki/loot_template#item)。这经常是需要的，例如，定义首领（Boss）掉落套装备（tier item）的掉落模板就需要这种行为。
- *组几率* < 100 的组每次生成**一件或零件**[物品](https://github.com/cmangos/issues/wiki/loot_template#item)，同时保持每件物品的[几率](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrRef)不变。这种行为对于限制掉落中物品的最大数量很有用。
- 可以为多个掉落来源共有的一组物品定义一个组。这对于减小数据库大小而没有任何数据损失非常有用。更多细节请参见[引用](https://github.com/cmangos/issues/wiki/loot_template#Group_reference)。

无法将[引用](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef)作为组的一部分。

注意：一个组可能包含非任务掉落、任务掉落或两者的定义，但不建议在单个组中混合非任务和任务掉落。

注意：核心有一个限制——只有16个非任务物品（不计入为任务添加的金钱和物品）可以进入掉落。这并非核心开发人员的任性——客户端有一些限制。由于大多数掉落的可能物品数量远多于16个（有时是数百个），因此如果没有组，就有（很小的）几率在给定的掉落中掷出超过16件物品，但玩家将只能看到（并拾取）其中的前16件。使用组，你可以确保超过16件物品*永远不会*掉落。如果数据库声称是高质量的软件，它必须确保任何掉落模板定义中不超过16个普通条目和组。这只是一个说明——UDB 开发者尚未发布这样的声明。

注意：核心对组的数量没有限制（除了数据库字段大小的255限制），但根据前面的说明，没有必要使用大于16的值。

**mincountOrRef**

此字段定义：
- 当为正数时：在单次掉落中可以掉落的该物品的最小副本数量
- 当为负数时：指向另一个模板的*引用*

零值没有意义，不应使用。

正数的含义相当清楚，不需要额外的注释。*引用*可以指向整个模板或模板的单个组，如下所述。

**模板引用**

[mincountOrRef](https://github.com/cmangos/issues/wiki/loot_template#mincountorref) < 0, [group](https://github.com/cmangos/issues/wiki/loot_template#groupid) = 0

模板引用要求核心处理另一个掉落模板（其 [entry](https://github.com/cmangos/issues/wiki/loot_template#entry) 等于“-mincountOrRef”），并将该模板掉落的所有物品包含到当前掉落中。简单的想法。

[maxcount](https://github.com/cmangos/issues/wiki/loot_template#maxcount) 字段的值被用作引用的重复因子——引用将被处理不止一次，而是正好 **maxcount** 次。因此，如果引用的模板可以产生3到10件物品（取决于运气），并且 **maxcount** 的值为'5'，那么在处理该引用后，将有15到50件物品被添加到掉落中。一个可怕的例子，不是吗？实际上，没有已知的关于整个模板引用重复的好例子，但有时对于[组引用](https://github.com/cmangos/issues/wiki/loot_template#Group_reference)来说，它非常有用。

小心。自我引用（掉落模板包含对自身的引用）和循环引用（掉落模板A包含对整个模板B的引用，掉落模板B包含对整个模板A的引用）与[内部引用](https://github.com/cmangos/issues/wiki/loot_template#Group_reference)*完全不同*。如果你像下面这样进行自我引用：

`INSERT INTO \`creature_loot_template\` (\`entry\`,\`item\`,\`mincountOrRef\`) VALUES ('21215','0','-21215');`

那么核心在第一次尝试处理掉落21215时就会因堆栈溢出而崩溃。这就是为什么**严格禁止自我引用和循环引用**。

**过滤引用**

[mincountOrRef](https://github.com/cmangos/issues/wiki/loot_template#mincountorref) < 0, [group](https://github.com/cmangos/issues/wiki/loot_template#groupid) > 0

组引用要求核心仅处理另一个掉落模板（其 [entry](https://github.com/cmangos/issues/wiki/loot_template#entry) 等于“-mincountOrRef”）的一个[组](https://github.com/cmangos/issues/wiki/loot_template#groupid)部分——该组的id等于引用条目的 \`groupid\` 字段值。因此，此引用可能仅向掉落中添加0或1件物品（前提是 [maxcount](https://github.com/cmangos/issues/wiki/loot_template#maxcount) 等于1）。

[maxcount](https://github.com/cmangos/issues/wiki/loot_template#maxcount) 字段值的含义与[模板引用](https://github.com/cmangos/issues/wiki/loot_template#Template_reference)中描述的相同。

请注意，无法将[引用](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef)作为组的一部分，因为这样的*分组引用*将具有与这里描述的*对组的引用*相同的格式。

有两种类型的组引用：
- *外部引用*：当组引用行的 **entry** 与引用组的 **entry** 不同时
- *内部引用*：当组引用行的 **entry** 与引用组的 **entry** 相同时

组引用的基本用法是避免在多个掉落来源具有共同的掉落部分时重复定义组。在这种情况下，可以：
- 一次又一次地定义具有相同内容（物品/掉落几率）的组。这是最简单的方法，但非常消耗RAM。
- 将该组定义为其中一个掉落来源的掉落定义的一部分，并在其他掉落来源的掉落定义中包含组引用，而不是重复组定义。
- 将该组定义为人工掉落定义（其 **entry** 不对应于任何来源）的一部分，并在每个相关掉落来源的掉落定义中包含组引用。

第一种方法已弃用，第二种和第三种都使用*外部引用*。UDB 推荐使用第三种方法。

由于引用有被处理的[几率](https://github.com/cmangos/issues/wiki/loot_template#ChanceOrQuestChance)，可以有效地将它们用于*区域*或*世界*掉落定义。这些掉落对于不同的掉落来源（低/高技能游戏对象、非精英/精英生物等）通常具有不同的几率，同时具有相同的掉落内容。定义此类掉落的推荐方式如下：
- 在人工掉落模板中设置一个100%[组几率](https://github.com/cmangos/issues/wiki/loot_template#groupid)的组（在可能的情况下使用[均等几率条目](https://github.com/cmangos/issues/wiki/loot_template#groupid)）
- 将该组的引用包含到每个相关掉落来源的掉落定义中，并为该引用设置掉落几率。

一些首领掉落不止一件套装备（两件或三件）。掉落统计看起来像是同一个组被掷了2次或3次，每次选择一件物品（可能是同一件）。为单件物品定义一个[组](https://github.com/cmangos/issues/wiki/loot_template#Grouped_entry)很简单，但是如何定义第二件和第三件的掉落呢？我们可以：
- 重复组定义2（或3）次，并更改组id
- 定义组一次，并包含1（或2）个*内部引用*
- 将组定义一次作为人工掉落定义的一部分，并包含2（或3）个*外部*组引用
- 将组定义一次作为人工掉落定义的一部分，并包含一个*外部*组引用，其[重复因子](https://github.com/cmangos/issues/wiki/loot_template#maxcount)为2（或3）

游戏内的结果将是相同的。但是再次说明——第一种方法效率非常低，因此已弃用。UDB 推荐使用第四种方法。

**maxcount**

对于非引用条目——在单次掉落中可以掉落的该物品的最大副本数量。

对于[引用](https://github.com/cmangos/issues/wiki/loot_template#Template_reference)，**maxcount** 字段的值被用作引用的重复因子——引用将被处理不止一次，而是正好 **maxcount** 次。这是为了服务于一个单一目的：使套装备（tier token）掉落的定义稍微简单一些（一个层级的代币被定义为一个100%几率的人工模板组，而首领的掉落模板包含一个100%几率的对该组的引用，重复因子为2或3，视情况而定）。将非1的重复因子用于其他事情（引用*组几率*小于100%的组或几率小于100%的[几率引用](https://github.com/cmangos/issues/wiki/loot_template#Chanced_references)）必须首先与 UDB 开发者商定（并在此描述）。

注意：核心对任何掉落定义条目只掷一次几率——因此，如果一个引用失去了它的几率，它将在当前掉落中被完全跳过，无论 **maxcount** 值是多少。

**condition_id**

表示必须满足的[条件](https://github.com/cmangos/issues/wiki/Conditions#condition_entry)的值，物品才能掉落。
有关详细描述，请参见[条件表](https://github.com/cmangos/issues/wiki/Conditions)。

注意：对于[引用条目](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef)，只能使用某些条件。

**约定**

这些约定对于不同的掉落表是不同的。约定主要定义了掉落模板ID（[entry](https://github.com/cmangos/issues/wiki/loot_template#entry)）和组的规则。

**钓鱼收获**

对于 fishing_loot_template，ID 是来自 [AreaTable.dbc](https://github.com/cmangos/issues/wiki/AreaTable.dbc) 的区域或地区ID（注意：区域ID未包含在链接中）

关于 fishing_loot_template 的额外说明：如果为一个区域（Zone）只定义了一个地区（Area）ID，那么整个区域ID将被跳过，因此该区域中的所有地区都需要在表中有条目。只有当某个区域不存在任何地区条目时，核心才会直接使用区域ID。区域 = 湿地、艾尔文森林等；地区 = 北郡、湖畔镇等。

当多个区域使用相同的掉落定义时：
- 具有最小ID（minID）的区域的掉落模板应定义而不使用引用
- 具有相同掉落的其他区域应将其掉落定义设置为对 minID 掉落定义的单一[引用](https://github.com/cmangos/issues/wiki/loot_template#mincountOrRef)

注意：有待 UDB 开发者确认

由于成功的钓鱼应该正好产生1条鱼（任务鱼除外），所以每个掉落模板的非任务部分应该是：
- 或者一个具有100%掉落几率的单一[普通条目](https://github.com/cmangos/issues/wiki/loot_template#Plain_entry)
- 或者一个[*组几率*](https://github.com/cmangos/issues/wiki/loot_template#groupid)等于100%的单一组
- 或者一个引用根据前两种变体制定的模板。推荐使用[组引用](https://github.com/cmangos/issues/wiki/loot_template#Group_reference)。

当钓到一条任务鱼时，它会成为鱼钩上的*第二条*鱼。许多人笑得在地上打滚，但这是暴雪原版的，并且幸运的是很容易实现。只需添加必要的[任务掉落](https://github.com/cmangos/issues/wiki/loot_template#Quest_drop)定义。

**尸体掉落**

对于 creature_loot_template，基本方法是使用 [creature_template.lootid](https://github.com/cmangos/issues/wiki/creature_template#lootid) 等于 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry)。但这会导致掉落表开销巨大，因为：
- 许多生物使用相同的掉落定义（好吧，由于随机掷骰的性质，网站上的统计数据是*相似的*）
- 甚至更多的生物使用相同的掉落定义部分

这就是为什么推荐使用[分组](https://github.com/cmangos/issues/wiki/loot_template#groupid)、[组引用](https://github.com/cmangos/issues/wiki/loot_template#Group_reference)和[模板引用](https://github.com/cmangos/issues/wiki/loot_template#Template_reference)。

**分解结果**

分解掉落模板编号的约定是 **[item.level](https://github.com/cmangos/issues/wiki/item_template#level&#42;100) + [item.quality](https://github.com/cmangos/issues/wiki/item_template#quality)**，其中 **item** 是分解目标。

由于分解应该正好产生1种碎片/精华/尘等，所以每个掉落模板应该是：
- 或者一个具有100%掉落几率的单一[普通条目](https://github.com/cmangos/issues/wiki/loot_template#Plain_entry)
- 或者一个[*组几率*](https://github.com/cmangos/issues/wiki/loot_template#groupid)等于100%的单一组

这里不需要引用，因为引用是通过关联字段完成的。完全没有任务掉落。

**游戏对象采集**

***待补充***

**行李内容**

***待补充***

**扒窃所得**

扒窃掉落模板编号的约定未知。

***待补充***

**勘探结果**

勘探掉落模板编号的约定未知。

***待补充***

**剥皮收获**

剥皮掉落模板编号的约定未知。这真的很遗憾，因为许多生物应该使用相同的模板。在大多数情况下，同科同等级的怪物的剥皮统计数据*非常*相似。

由于剥皮应该正好产生1种皮/皮革等，所以每个掉落模板应该是：
- 或者一个具有100%掉落几率的单一[普通条目](https://github.com/cmangos/issues/wiki/loot_template#Plain_entry)
- 或者一个[*组几率*](https://github.com/cmangos/issues/wiki/loot_template#groupid)等于100%的单一组

这里不需要引用，因为引用是通过关联字段完成的。

当为一个任务剥皮时，它会成为该生物的*第二张*皮。是的，很有趣。这是暴雪原版的，并且幸运的是很容易实现。只需添加必要的[任务掉落](https://github.com/cmangos/issues/wiki/loot_template#Quest_drop)定义。

**示例**

这里的示例主要取自当前的 UDB (339) 或 UDB 论坛。示例通常有多个作者，很难正确归功于所有人，因此：非常感谢所有 UDB 开发者和贡献者。

但请注意，一些（甚至所有）示例可能包含不正确的数据，仅用于演示不同的掉落数据组织方式。
