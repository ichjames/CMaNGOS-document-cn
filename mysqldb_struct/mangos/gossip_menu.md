Gossip_menu

**`gossip_menu` 表**

此表用于在玩家与NPC对话时显示闲谈话语。

**结构**

| **字段**        | **类型**               | **属性**   | **键** | **Null** | **默认值** |
| --------------- | ---------------------- | ---------- | ------ | -------- | ---------- |
| entry           | smallint(6) unsigned   |            | 主键   | 否       | 0          |
| text_id         | mediumint(8) unsigned  |            | 主键   | 否       | 0          |
| script_id       | mediumint(8) unsigned  |            |        | 否       | 0          |
| condition_id    | mediumint(8) unsigned  |            |        | 否       | 0          |

**字段描述**

**entry**
闲谈菜单ID，来自 gossip_menu_id 和 gameobject_template.GAMEOBJECT_TYPE_QUESTGIVER.data3

**text_id**
引用 npc_text.id。

**script_id**
如果设置，将启动具有此ID的数据库脚本，对应于选定的文本
注意：在菜单显示时调用（不是在点击时）
dbscripts_on_gossip

**condition_id**
条件ID
如果闲谈菜单有多个条件为真的文本，则将显示具有最高condition_id的文本。