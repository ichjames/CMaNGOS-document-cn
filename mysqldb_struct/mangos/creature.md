creature

 

Grz3s 于 2月19日编辑了此页面 · [10次修订](https://github.com/cmangos/issues/wiki/creature/_history)

返回 [世界数据库](https://github.com/cmangos/issues/wiki/mangosdb_struct) 表列表。

**`creature` 表**

包含个体生物生成数据。生物生成是生物对象在世界中的一个实例。

**结构**

| **字段**                                                                       | **类型**            | **Null** | **Key** | **默认值** | **额外**        |
| ------------------------------------------------------------------------------ | ------------------- | -------- | ------- | ---------- | --------------- |
| [guid](https://github.com/cmangos/issues/wiki/creature#guid)                   | int(10) unsigned    | 否       | 主键    | 无         | 自动递增        |
| [id](https://github.com/cmangos/issues/wiki/creature#id)                       | mediumint(8) unsigned | 否       | 索引    | 0          |                 |
| [map](https://github.com/cmangos/issues/wiki/creature#map)                     | smallint(5) unsigned | 否       | 索引    | 0          |                 |
| [spawnMask](https://github.com/cmangos/issues/wiki/creature#spawnmask)         | tinyint(3) unsigned | 否       |         | 1          |                 |
| [phaseMask](https://github.com/cmangos/issues/wiki/creature#phasemask)         | smallint(5) unsigned | 否       |         | 1          | (巫妖王之怒+)   |
| [position_x](https://github.com/cmangos/issues/wiki/creature#position_x)       | float               | 否       |         | 0          |                 |
| [position_y](https://github.com/cmangos/issues/wiki/creature#position_y)       | float               | 否       |         | 0          |                 |
| [position_z](https://github.com/cmangos/issues/wiki/creature#position_z)       | float               | 否       |         | 0          |                 |
| [orientation](https://github.com/cmangos/issues/wiki/creature#orientation)     | float               | 否       |         | 0          |                 |
| [spawntimesecsmin](https://github.com/cmangos/issues/wiki/creature#spawntimesecsmin) | int(10) unsigned    | 否       |         | 120        |                 |
| [spawntimesecsmax](https://github.com/cmangos/issues/wiki/creature#spawntimesecsmax) | int(10) unsigned    | 否       |         | 120        |                 |
| [spawndist](https://github.com/cmangos/issues/wiki/creature#spawndist)         | float               | 否       |         | 5          |                 |
| [MovementType](https://github.com/cmangos/issues/wiki/creature#movementtype)   | tinyint(3) unsigned | 否       |         | 0          |                 |

**字段描述**

**guid**

分配给每个生物的唯一标识符，用于区分不同生物。两个生物**不能**拥有相同的**GUID**。

巫妖王之怒数据库为**仅限**诺森德的生物保留了GUID范围 500000 -- 599999。

**id**

实例化此生物时使用的模板ID。参见 [creature_template.entry](https://github.com/cmangos/issues/wiki/creature_template#entry)

**map**

生物位置的地图ID。参见 [Map.dbc](https://github.com/cmangos/issues/wiki/Map.dbc)

**spawnMask**

控制生物在哪些难度下会被生成。

| **值** | **注释**                                                                 |
| ------ | ------------------------------------------------------------------------ |
| 0      | 不生成                                                                   |
| 1      | 仅在10人普通版本的地图中生成（包括没有英雄模式的地图）                   |
| 2      | 仅在25人普通版本的地图中生成（或3.2版本之前的英雄模式）                  |
| 4      | 仅在10人英雄版本的地图中生成                                             |
| 8      | 仅在25人英雄版本的地图中生成                                             |
| 15     | 在所有版本的地图中生成                                                   |

**phaseMask**

定义生物所属的相位。1是默认相位，其余来自法术光环261，（Aura #261）(4) = 相位掩码 = 4。

**position_x**

生物的X坐标位置。

**position_y**

生物的Y坐标位置。

**position_z**

生物的Z坐标位置。

**orientation**

生物的朝向。（北 = 0.0；南 = pi (3.14159)）

**spawntimesecsmin**

生物的最小重生时间，单位为秒。

**spawntimesecsmax**

生物的最大重生时间，单位为秒。

如果 spawntimesecsmin 和 spawntimesecsmax 均为 0，则生物不会重生。仅通过脚本重生。

**spawndist**

生物从其生成点生成的最大距离。如果生物的 [MovementType](https://github.com/cmangos/issues/wiki/creature#MovementType) = 1，此值也控制生物从其生成点可以行走的最大距离。

| **值** | **注释**                             |
| ------ | ------------------------------------ |
| -1     | 仅改变朝向 —— 当前未实现             |
| 5      | 默认的随机移动值                     |

**MovementType**

参见 [creature_template.MovementType](https://github.com/cmangos/issues/wiki/creature_template#MovementType) 了解可能的值。

creature_movement 和 creature_movement_template 需要将 MovementType 设置为 2,3,4 以对应某个 guid。

spawn_group / waypoint_path 生成的所有生物应使用 0 作为 MovementType。

| **值** | **名称**               | **注释**                                                                                     |
| ------ | ---------------------- | -------------------------------------------------------------------------------------------- |
| 0      | 空闲移动类型           | 无移动 —— 空闲移动生成器                                                                     |
| 1      | 随机移动类型           | 使用 spawndist 进行随机移动 —— 随机移动生成器                                                |
| 2      | 路径点移动类型         | 123.123 —— 路径点移动生成器                                                                  |
| 3      | 路径移动类型           | 123.123 —— 样条移动，所有路径点在生物更新数据包中发送（例如飞行路径）—— 路径移动生成器        |
| 4      | 线性路径点移动类型     | 123.21.23.21.23.21 —— 路径点移动生成器                                                       |