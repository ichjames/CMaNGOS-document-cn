# CMaNGOS 数据库与DBC文件中文化说明文档

这是针对 [CMaNGOS](https://github.com/cmangos) 项目中 MySQL 数据库表结构和 DBC 文件的中文说明文档集合。该文档基于官方 [CMaNGOS Wiki](https://github.com/cmangos/issues/wiki) 内容进行翻译整理，旨在帮助中文用户更好地理解和使用 CMaNGOS 项目。

## 📚 文档内容

### 数据库表结构说明

本项目包含了 CMaNGOS 核心数据库 `mangos` 中主要数据表的详细说明：

- 表功能概述与分类
- 字段详细解释
- 使用示例和注意事项
- 表之间的关联关系

其中包括但不限于以下重要表结构说明：
- [creature_template](https://github.com/cmangos/issues/wiki/creature_template) - 生物模板表
- [creature](https://github.com/cmangos/issues/wiki/creature) - 生物实例表
- [gameobject_template](https://github.com/cmangos/issues/wiki/gameobject_template) - 游戏对象模板表
- [gameobject](https://github.com/cmangos/issues/wiki/gameobject) - 游戏对象实例表
- [item_template](https://github.com/cmangos/issues/wiki/item_template) - 物品模板表
- [quest_template](https://github.com/cmangos/issues/wiki/quest_template) - 任务模板表
- [creature_loot_template](https://github.com/cmangos/issues/wiki/creature_loot_template) - 生物掉落模板表
- 以及100+其他核心表的详细说明

### DBC 文件说明

文档还涵盖了魔兽世界客户端 DBC 数据文件的结构说明：

- DBC 文件格式解析
- 各种 DBC 表的字段含义
- 与数据库表的关联关系
- 在服务器中的应用方式

## 📖 文档来源

所有文档内容均来源于 CMaNGOS 官方 Wiki：
[https://github.com/cmangos/issues/wiki](https://github.com/cmangos/issues/wiki)

## 🎯 适用版本

本说明文档适用于以下 CMaNGOS 版本：
- Classic (1.12.x)
- TBC (2.4.3)
- WotLK (3.3.5a)

## 🚀 使用方法

您可以直接浏览本项目中的 Markdown 文件来查看对应表结构和 DBC 文件的详细说明。

对于开发者和服务器管理员，这些文档可以帮助您：
- 理解数据库表结构设计
- 正确配置游戏数据
- 进行自定义修改和扩展
- 调试和解决数据相关问题

## 🤝 贡献

欢迎对文档进行补充和修正。如果您发现任何错误或有改进意见，请提交 Issue 或 Pull Request。

## 📄 许可证

本文档基于 CMaNGOS Wiki 内容整理，遵循相同的许可协议。

CMaNGOS 是一个开源项目，遵循 GNU General Public License v2.0 许可证。