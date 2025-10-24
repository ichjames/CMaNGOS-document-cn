npc_vendor_template

 

**`npc_vendor(_template)` 表**

存储所有通过 [`creature_template`.`entry`](https://github.com/cmangos/issues/wiki/Creature_template#entry) 或 [creature_template.VendorTemplateId](https://github.com/cmangos/issues/wiki/creature_template#VendorTemplateId) 出售物品的NPC商人的数据。

每个物品的金币价格在其物品模板中，参见 [BuyPrice](https://github.com/cmangos/issues/wiki/item_template#BuyPrice)。

**结构**

| **字段**                                                                       | **类型**            | **Null** | **Key** | **默认值** | **额外** |
| ------------------------------------------------------------------------------ | ------------------- | -------- | ------- | ---------- | -------- |
| [entry/VendorTemplateId](https://github.com/cmangos/issues/wiki/npc_vendor_template#guid/entry) | int(10) unsigned    | 否       | 主键    | 0          |          |
| [item](https://github.com/cmangos/issues/wiki/npc_vendor_template#item)        | int(10) unsigned    | 否       | 主键    | 0          |          |
| [maxcount](https://github.com/cmangos/issues/wiki/npc_vendor_template#maxcount)| int(10) unsigned    | 否       |         | 0          |          |
| [incrtime](https://github.com/cmangos/issues/wiki/npc_vendor_template#incrtime)| int(10) unsigned    | 否       |         | 0          |          |
| [slot](https://github.com/cmangos/issues/wiki/npc_vendor_template#slot)        | tinyint(3) unsigned | 否       |         | 0          |          |
| [ExtendedCost](https://github.com/cmangos/issues/wiki/npc_vendor_template#extendedcost) | mediumint(8) unsigned | 否       |         | 0          |          |
| [condition_id](https://github.com/cmangos/issues/wiki/npc_vendor_template#condition_id) | mediumint(8) unsigned | 否       |         | 0          |          |
| [comments](https://github.com/cmangos/issues/wiki/npc_vendor_template#comments)| text                | 否       |         | NULL       |          |

**字段描述**

**entry/VendorTemplateId**

对于 npc_vendor 表，这是生物的 [`creature_template`.`entry`](https://github.com/cmangos/issues/wiki/Creature_template#entry)

对于 npc_vendor_template 表，这是 [creature_template.VendorTemplateId](https://github.com/cmangos/issues/wiki/creature_template#VendorTemplateId)，表示由此条目售卖的供应商列表。

**item**

物品ID。参见 [item_template.entry](https://github.com/cmangos/issues/wiki/item_template#entry)

**maxcount**

商人可供出售的该物品副本的最大数量。如果为0，则表示无限数量的副本。

**incrtime**

与 [maxcount](https://github.com/cmangos/issues/wiki/npc_vendor_template#maxcount) 结合使用，此字段表示商人列表刷新的频率（以秒为单位），以及限量物品副本的补货频率。对于限量物品副本，每次刷新时，数量会增加 [item_template.BuyCount](https://github.com/cmangos/issues/wiki/item_template#BuyCount)

**slot**

决定售出物品在商人菜单中的位置

| **槽位** | **槽位** |
| -------- | -------- |
| 1        | 2        |
| 3        | 4        |
| 5        | 6        |
| 7        | 8        |
| 9        | 10       |

**ExtendedCost**

此处的值对应 ItemExtendedCost.dbc 中的ID，该ID控制物品的非货币价格，可以是荣誉点数、竞技场点数、不同类型的徽章或上述任何组合。

**condition_id**

购买物品的条件，对应conditions表的id（？）

**comments**

描述 —— 目前为"物品名称"