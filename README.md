因为懒兵英语不好，所以只有中文README。

LazyBing has pool english. chinese README only.



## 起因

在给基友开设离线 MC服务器时，发现即便添加了原版的白名单却仍然无法进入服务器。

研究后发现：**原版白名单**即便在离线模式下，仍然以 **{正版UUID}** 记录白名单玩家；

但是你登录时使用的是 **{离线UUID}** 显然，他和 `whitelist.json`中记录的UUID不符，导致无法进入。

随后就有了此插件，设计为离线服管理白名单用。





## 快速开始

### 	安装

​		本插件为单文件，将本体 `OfflineWhitelistManager.py` 放入插件目录 `/plugin/` 可完成安装，

​		随后需要使用MCDR命令`!!MCDR r plg`以载入插件。



### 	配置

​		本插件使用懒狗狂喜的 **硬编码** 存储配置信息，修改区域位于插件前面几行（如图）

​		如 **服务端文件夹** 或 **存档文件夹** 修改过名称，需要修改配置信息。

​		`server_dirname: 服务端文件夹名称`		`world_dirname: 存档文件夹名称`

![hard_config](https://github.com/Lazy-Bing-Server/MCDR-offline-whitelist-manager/blob/main/pic/hard_config.png)



​		余下配置信息 **请不要** 修改，此处仅做介绍。

​		`offline_uuid_method: 获取离线UUID方法(int, 默认：3，推荐：3)`

​		方法1：通过API获取离线UUID。

​		方法2：通过carpet bot + 比较 playerdata的方式获取离线UUID，需要服务器安装有Carpet Mod。		

​		**## 方法2对于同一昵称仅能添加一次白名单（意味着删白名等同于永久BAN）。不推荐 ##**

​		方法3：通过按照mojang规则本地计算离线UUID。

​		`bot_wait_time: 方法2时等待Carpet bot的时间(int, 默认: 3)`



### 	命令

​		`!!wlist help`

​			显示插件帮助信息。



​		`!!wlist add [player name]` 

​			添加玩家至服务器白名单，**# 该命令需要MCDR权限ADMIN及以上 #**。

​			![wlist_add](https://github.com/Lazy-Bing-Server/MCDR-offline-whitelist-manager/blob/main/pic/wlist_add.png)



​		`!!wlist remove [player name]`

​			从服务器白名单中移出玩家，**# 该命令需要MCDR权限ADMIN及以上 #**。

​			![wlist_remove](https://github.com/Lazy-Bing-Server/MCDR-offline-whitelist-manager/blob/main/pic/wlist_remove.png)



​		`!!wlist list`

​			显示服务器白名单列表，**# 该命令需要MCDR权限ADMIN及以上 #**。

​			![wlist_list](https://github.com/Lazy-Bing-Server/MCDR-offline-whitelist-manager/blob/main/pic/wlist_list.png)



### 	备份

​		每次操作白名单（Add/Remove)时都会生成一次备份，备份位于 `/server/whitelist_backup/`

​		备份中会使用 **A / R** 记录本次备份时的操作类型 添加 / 删除 。（意味这备份是X操作前保存的）

​		![backup_whitelist](https://github.com/Lazy-Bing-Server/MCDR-offline-whitelist-manager/blob/main/pic/backup_whitelist.png)





## 鸣谢

​	Ra1ny_Yuki: 在编写插件中作为人肉编译器及时用碳基生物自然语言骂我。

​	Fallen_Breath: 从他那偷来了生成离线UUID的API。

​	账号己注销: 提供了本地计算离线UUID的代码

​	Tonashiki: 为我产生了编写该插件的需求。





## 彩蛋

​	本插件系强迫症友好型插件，插件大小为 8192 **Bytes**.
