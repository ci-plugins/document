# devops\_ci\_process

**数据库名：** devops\_ci\_process

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_process的数据库文档

|                                                        表名                                                       |      说明      |
| :-------------------------------------------------------------------------------------------------------------: | :----------: |
|                         [T\_AUDIT\_RESOURCE](devops\_ci\_process.md#T\_AUDIT\_RESOURCE)                         |              |
|           [T\_PIPELINE\_ATOM\_REPLACE\_BASE](devops\_ci\_process.md#T\_PIPELINE\_ATOM\_REPLACE\_BASE)           | 流水线插件替换基本信息表 |
|        [T\_PIPELINE\_ATOM\_REPLACE\_HISTORY](devops\_ci\_process.md#T\_PIPELINE\_ATOM\_REPLACE\_HISTORY)        | 流水线插件替换历史信息表 |
|           [T\_PIPELINE\_ATOM\_REPLACE\_ITEM](devops\_ci\_process.md#T\_PIPELINE\_ATOM\_REPLACE\_ITEM)           |  流水线插件替换项信息表 |
|                [T\_PIPELINE\_BUILD\_COMMITS](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_COMMITS)                |              |
|              [T\_PIPELINE\_BUILD\_CONTAINER](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_CONTAINER)              |  流水线构建容器环境表  |
|                 [T\_PIPELINE\_BUILD\_DETAIL](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_DETAIL)                 |   流水线构建详情表   |
|                [T\_PIPELINE\_BUILD\_HISTORY](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_HISTORY)                |   流水线构建历史表   |
|       [T\_PIPELINE\_BUILD\_HIS\_DATA\_CLEAR](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_HIS\_DATA\_CLEAR)       | 流水线构建数据清理统计表 |
|      [T\_PIPELINE\_BUILD\_RECORD\_CONTAINER](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_RECORD\_CONTAINER)      |  流水线构建容器环境表  |
|          [T\_PIPELINE\_BUILD\_RECORD\_MODEL](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_RECORD\_MODEL)          |   流水线构建详情表   |
|          [T\_PIPELINE\_BUILD\_RECORD\_STAGE](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_RECORD\_STAGE)          |   流水线构建阶段表   |
|           [T\_PIPELINE\_BUILD\_RECORD\_TASK](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_RECORD\_TASK)           |   流水线构建任务表   |
|                  [T\_PIPELINE\_BUILD\_STAGE](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_STAGE)                  |   流水线构建阶段表   |
|                [T\_PIPELINE\_BUILD\_SUMMARY](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_SUMMARY)                |   流水线构建摘要表   |
|                   [T\_PIPELINE\_BUILD\_TASK](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_TASK)                   |   流水线构建任务表   |
| [T\_PIPELINE\_BUILD\_TEMPLATE\_ACROSS\_INFO](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_TEMPLATE\_ACROSS\_INFO) |  流水线模板跨项目访问表 |
|                    [T\_PIPELINE\_BUILD\_VAR](devops\_ci\_process.md#T\_PIPELINE\_BUILD\_VAR)                    |    流水线变量表    |
|                   [T\_PIPELINE\_DATA\_CLEAR](devops\_ci\_process.md#T\_PIPELINE\_DATA\_CLEAR)                   |  流水线数据清理统计表  |
|                         [T\_PIPELINE\_FAVOR](devops\_ci\_process.md#T\_PIPELINE\_FAVOR)                         |    流水线收藏表    |
|                         [T\_PIPELINE\_GROUP](devops\_ci\_process.md#T\_PIPELINE\_GROUP)                         |    流水线分组表    |
|                          [T\_PIPELINE\_INFO](devops\_ci\_process.md#T\_PIPELINE\_INFO)                          |    流水线信息表    |
|             [T\_PIPELINE\_JOB\_MUTEX\_GROUP](devops\_ci\_process.md#T\_PIPELINE\_JOB\_MUTEX\_GROUP)             |              |
|                         [T\_PIPELINE\_LABEL](devops\_ci\_process.md#T\_PIPELINE\_LABEL)                         |    流水线标签表    |
|               [T\_PIPELINE\_LABEL\_PIPELINE](devops\_ci\_process.md#T\_PIPELINE\_LABEL\_PIPELINE)               |   流水线-标签映射表  |
|                   [T\_PIPELINE\_MODEL\_TASK](devops\_ci\_process.md#T\_PIPELINE\_MODEL\_TASK)                   | 流水线模型task任务表 |
|                  [T\_PIPELINE\_PAUSE\_VALUE](devops\_ci\_process.md#T\_PIPELINE\_PAUSE\_VALUE)                  |   流水线暂停变量表   |
|                   [T\_PIPELINE\_RECENT\_USE](devops\_ci\_process.md#T\_PIPELINE\_RECENT\_USE)                   |   最近使用的流水线   |
|                  [T\_PIPELINE\_REMOTE\_AUTH](devops\_ci\_process.md#T\_PIPELINE\_REMOTE\_AUTH)                  | 流水线远程触发auth表 |
|                      [T\_PIPELINE\_RESOURCE](devops\_ci\_process.md#T\_PIPELINE\_RESOURCE)                      |    流水线资源表    |
|             [T\_PIPELINE\_RESOURCE\_VERSION](devops\_ci\_process.md#T\_PIPELINE\_RESOURCE\_VERSION)             |   流水线资源版本表   |
|                          [T\_PIPELINE\_RULE](devops\_ci\_process.md#T\_PIPELINE\_RULE)                          |   流水线规则信息表   |
|                       [T\_PIPELINE\_SETTING](devops\_ci\_process.md#T\_PIPELINE\_SETTING)                       |   流水线基础配置表   |
|              [T\_PIPELINE\_SETTING\_VERSION](devops\_ci\_process.md#T\_PIPELINE\_SETTING\_VERSION)              |  流水线基础配置版本表  |
|                    [T\_PIPELINE\_STAGE\_TAG](devops\_ci\_process.md#T\_PIPELINE\_STAGE\_TAG)                    |              |
|                         [T\_PIPELINE\_TIMER](devops\_ci\_process.md#T\_PIPELINE\_TIMER)                         |              |
|               [T\_PIPELINE\_TRIGGER\_DETAIL](devops\_ci\_process.md#T\_PIPELINE\_TRIGGER\_DETAIL)               |  流水线触发事件明细表  |
|                [T\_PIPELINE\_TRIGGER\_EVENT](devops\_ci\_process.md#T\_PIPELINE\_TRIGGER\_EVENT)                |   流水线触发事件表   |
|               [T\_PIPELINE\_TRIGGER\_REVIEW](devops\_ci\_process.md#T\_PIPELINE\_TRIGGER\_REVIEW)               |   流水线触发审核信息  |
|                          [T\_PIPELINE\_VIEW](devops\_ci\_process.md#T\_PIPELINE\_VIEW)                          |     流水线视图    |
|                   [T\_PIPELINE\_VIEW\_GROUP](devops\_ci\_process.md#T\_PIPELINE\_VIEW\_GROUP)                   |    流水线组关系表   |
|                     [T\_PIPELINE\_VIEW\_TOP](devops\_ci\_process.md#T\_PIPELINE\_VIEW\_TOP)                     |    流水线组置顶表   |
|        [T\_PIPELINE\_VIEW\_USER\_LAST\_VIEW](devops\_ci\_process.md#T\_PIPELINE\_VIEW\_USER\_LAST\_VIEW)        |              |
|          [T\_PIPELINE\_VIEW\_USER\_SETTINGS](devops\_ci\_process.md#T\_PIPELINE\_VIEW\_USER\_SETTINGS)          |              |
|                       [T\_PIPELINE\_WEBHOOK](devops\_ci\_process.md#T\_PIPELINE\_WEBHOOK)                       |              |
|     [T\_PIPELINE\_WEBHOOK\_BUILD\_PARAMETER](devops\_ci\_process.md#T\_PIPELINE\_WEBHOOK\_BUILD\_PARAMETER)     |  webhook构建参数 |
|                [T\_PIPELINE\_WEBHOOK\_QUEUE](devops\_ci\_process.md#T\_PIPELINE\_WEBHOOK\_QUEUE)                |              |
|             [T\_PIPELINE\_WEBHOOK\_REVISION](devops\_ci\_process.md#T\_PIPELINE\_WEBHOOK\_REVISION)             |              |
|             [T\_PROJECT\_PIPELINE\_CALLBACK](devops\_ci\_process.md#T\_PROJECT\_PIPELINE\_CALLBACK)             |              |
|    [T\_PROJECT\_PIPELINE\_CALLBACK\_HISTORY](devops\_ci\_process.md#T\_PROJECT\_PIPELINE\_CALLBACK\_HISTORY)    |              |
|                                  [T\_REPORT](devops\_ci\_process.md#T\_REPORT)                                  |    流水线产物表    |
|                                [T\_TEMPLATE](devops\_ci\_process.md#T\_TEMPLATE)                                |   流水线模板信息表   |
|                [T\_TEMPLATE\_INSTANCE\_BASE](devops\_ci\_process.md#T\_TEMPLATE\_INSTANCE\_BASE)                |  模板实列化基本信息表  |
|                [T\_TEMPLATE\_INSTANCE\_ITEM](devops\_ci\_process.md#T\_TEMPLATE\_INSTANCE\_ITEM)                |   模板实列化项信息表  |
|                      [T\_TEMPLATE\_PIPELINE](devops\_ci\_process.md#T\_TEMPLATE\_PIPELINE)                      |  流水线模板-实例映射表 |

**表名：** T\_AUDIT\_RESOURCE

**说明：**

**数据列：**

|  序号 |        名称       |    数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |  说明  |
| :-: | :-------------: | :-------: | :--: | :-: | :--: | :-: | :----------------: | :--: |
|  1  |        ID       |   bigint  |  20  |  0  |   N  |  Y  |                    | 主键ID |
|  2  |  RESOURCE\_TYPE |  varchar  |  32  |  0  |   N  |  N  |                    | 资源类型 |
|  3  |   RESOURCE\_ID  |  varchar  |  128 |  0  |   N  |  N  |                    | 资源ID |
|  4  |  RESOURCE\_NAME |  varchar  |  128 |  0  |   N  |  N  |                    | 资源名称 |
|  5  |     USER\_ID    |  varchar  |  64  |  0  |   N  |  N  |                    | 用户ID |
|  6  |      ACTION     |  varchar  |  64  |  0  |   N  |  N  |                    |  操作  |
|  7  | ACTION\_CONTENT |  varchar  | 1024 |  0  |   N  |  N  |                    | 操作内容 |
|  8  |  CREATED\_TIME  | timestamp |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 创建时间 |
|  9  |      STATUS     |  varchar  |  32  |  0  |   Y  |  N  |                    |  状态  |
|  10 |   PROJECT\_ID   |  varchar  |  128 |  0  |   N  |  N  |                    | 项目ID |

**表名：** T\_PIPELINE\_ATOM\_REPLACE\_BASE

**说明：** 流水线插件替换基本信息表

**数据列：**

|  序号 |         名称         |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |          默认值          |    说明   |
| :-: | :----------------: | :------: | :---: | :-: | :--: | :-: | :-------------------: | :-----: |
|  1  |         ID         |  varchar |   32  |  0  |   N  |  Y  |                       |   主键ID  |
|  2  |     PROJECT\_ID    |  varchar |   64  |  0  |   Y  |  N  |                       |   项目ID  |
|  3  | PIPELINE\_ID\_INFO |   text   | 65535 |  0  |   Y  |  N  |                       | 流水线ID信息 |
|  4  |  FROM\_ATOM\_CODE  |  varchar |   64  |  0  |   N  |  N  |                       | 被替换插件代码 |
|  5  |   TO\_ATOM\_CODE   |  varchar |   64  |  0  |   N  |  N  |                       | 被替换插件代码 |
|  6  |       STATUS       |  varchar |   32  |  0  |   N  |  N  |          INIT         |    状态   |
|  7  |       CREATOR      |  varchar |   50  |  0  |   N  |  N  |         system        |   创建者   |
|  8  |      MODIFIER      |  varchar |   50  |  0  |   N  |  N  |         system        |   修改者   |
|  9  |    UPDATE\_TIME    | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   修改时间  |
|  10 |    CREATE\_TIME    | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   创建时间  |

**表名：** T\_PIPELINE\_ATOM\_REPLACE\_HISTORY

**说明：** 流水线插件替换历史信息表

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |     说明     |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :--------: |
|  1  |        ID       |  varchar |  32 |  0  |   N  |  Y  |                       |    主键ID    |
|  2  |   PROJECT\_ID   |  varchar |  64 |  0  |   Y  |  N  |                       |    项目ID    |
|  3  |     BUS\_ID     |  varchar |  34 |  0  |   N  |  N  |                       |    业务ID    |
|  4  |    BUS\_TYPE    |  varchar |  32 |  0  |   N  |  N  |        PIPELINE       |    业务类型    |
|  5  | SOURCE\_VERSION |    int   |  10 |  0  |   N  |  N  |                       |    源版本号    |
|  6  | TARGET\_VERSION |    int   |  10 |  0  |   Y  |  N  |                       |    目标版本号   |
|  7  |      STATUS     |  varchar |  32 |  0  |   N  |  N  |                       |     状态     |
|  8  |       LOG       |  varchar | 128 |  0  |   Y  |  N  |                       |     日志     |
|  9  |     BASE\_ID    |  varchar |  32 |  0  |   N  |  N  |                       | 插件替换基本信息ID |
|  10 |     ITEM\_ID    |  varchar |  32 |  0  |   N  |  N  |                       |  插件替换项信息ID |
|  11 |     CREATOR     |  varchar |  50 |  0  |   N  |  N  |         system        |     创建者    |
|  12 |     MODIFIER    |  varchar |  50 |  0  |   N  |  N  |         system        |     修改者    |
|  13 |   UPDATE\_TIME  | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    修改时间    |
|  14 |   CREATE\_TIME  | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    创建时间    |

**表名：** T\_PIPELINE\_ATOM\_REPLACE\_ITEM

**说明：** 流水线插件替换项信息表

**数据列：**

|  序号 |          名称          |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |          默认值          |     说明     |
| :-: | :------------------: | :------: | :---: | :-: | :--: | :-: | :-------------------: | :--------: |
|  1  |          ID          |  varchar |   32  |  0  |   N  |  Y  |                       |    主键ID    |
|  2  |   FROM\_ATOM\_CODE   |  varchar |   64  |  0  |   N  |  N  |                       |   被替换插件代码  |
|  3  |  FROM\_ATOM\_VERSION |  varchar |   20  |  0  |   N  |  N  |                       |  被替换插件版本号  |
|  4  |    TO\_ATOM\_CODE    |  varchar |   64  |  0  |   N  |  N  |                       |   替换插件代码   |
|  5  |   TO\_ATOM\_VERSION  |  varchar |   20  |  0  |   N  |  N  |                       |   替换插件版本号  |
|  6  |        STATUS        |  varchar |   32  |  0  |   N  |  N  |          INIT         |     状态     |
|  7  | PARAM\_REPLACE\_INFO |   text   | 65535 |  0  |   Y  |  N  |                       |  插件参数替换信息  |
|  8  |       BASE\_ID       |  varchar |   32  |  0  |   N  |  N  |                       | 插件替换基本信息ID |
|  9  |        CREATOR       |  varchar |   50  |  0  |   N  |  N  |         system        |     创建者    |
|  10 |       MODIFIER       |  varchar |   50  |  0  |   N  |  N  |         system        |     修改者    |
|  11 |     UPDATE\_TIME     | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    修改时间    |
|  12 |     CREATE\_TIME     | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    创建时间    |

**表名：** T\_PIPELINE\_BUILD\_COMMITS

**说明：**

**数据列：**

|  序号 |         名称         |   数据类型   |     长度     | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :----------------: | :------: | :--------: | :-: | :--: | :-: | :-: | :----: |
|  1  |         ID         |  bigint  |     20     |  0  |   N  |  Y  |     |        |
|  2  |     PROJECT\_ID    |  varchar |     32     |  0  |   N  |  N  |     |        |
|  3  |    PIPELINE\_ID    |  varchar |     34     |  0  |   N  |  N  |     |        |
|  4  |      BUILD\_ID     |  varchar |     34     |  0  |   N  |  N  |     |        |
|  5  |     COMMIT\_ID     |  varchar |     64     |  0  |   N  |  N  |     |        |
|  6  |       MESSAGE      | longtext | 2147483647 |  0  |   N  |  N  |     |        |
|  7  |    AUTHOR\_NAME    |  varchar |     64     |  0  |   N  |  N  |     |        |
|  8  | MERGE\_REQUEST\_ID |  varchar |     256    |  0  |   Y  |  N  |     |        |
|  9  |  REPOSITORY\_TYPE  |  varchar |     20     |  0  |   N  |  N  |     |        |
|  10 |    COMMIT\_TIME    | datetime |     19     |  0  |   N  |  N  |     |        |
|  11 |    CREATE\_TIME    | datetime |     19     |  0  |   N  |  N  |     |        |
|  12 |         URL        |  varchar |     255    |  0  |   N  |  N  |     |  仓库url |
|  13 |     EVENT\_TYPE    |  varchar |     32     |  0  |   N  |  N  |     | 触发事件类型 |
|  14 |       CHANNEL      |  varchar |     32     |  0  |   Y  |  N  |     |        |
|  15 |       ACTION       |  varchar |     64     |  0  |   Y  |  N  |     |        |

**表名：** T\_PIPELINE\_BUILD\_CONTAINER

**说明：** 流水线构建容器环境表

**数据列：**

|  序号 |          名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |     说明    |
| :-: | :-----------------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :-------: |
|  1  |     PROJECT\_ID     |   varchar  |    64    |  0  |   N  |  N  |                    |    项目ID   |
|  2  |     PIPELINE\_ID    |   varchar  |    64    |  0  |   N  |  N  |                    |   流水线ID   |
|  3  |      BUILD\_ID      |   varchar  |    64    |  0  |   N  |  Y  |                    |    构建ID   |
|  4  |      STAGE\_ID      |   varchar  |    64    |  0  |   N  |  Y  |                    | 当前stageId |
|  5  |    CONTAINER\_ID    |   varchar  |    64    |  0  |   N  |  Y  |                    |   构建容器ID  |
|  6  |   CONTAINER\_TYPE   |   varchar  |    45    |  0  |   Y  |  N  |                    |    容器类型   |
|  7  |         SEQ         |     int    |    10    |  0  |   N  |  N  |                    |           |
|  8  |        STATUS       |     int    |    10    |  0  |   Y  |  N  |                    |     状态    |
|  9  |     START\_TIME     |  timestamp |    19    |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |    开始时间   |
|  10 |      END\_TIME      |  timestamp |    19    |  0  |   Y  |  N  |                    |    结束时间   |
|  11 |         COST        |     int    |    10    |  0  |   Y  |  N  |          0         |     花费    |
|  12 |    EXECUTE\_COUNT   |     int    |    10    |  0  |   Y  |  N  |          1         |    执行次数   |
|  13 |      CONDITIONS     | mediumtext | 16777215 |  0  |   Y  |  N  |                    |     状况    |
|  14 | CONTAINER\_HASH\_ID |   varchar  |    64    |  0  |   Y  |  N  |                    |  容器全局唯一ID |
|  15 | MATRIX\_GROUP\_FLAG |     bit    |     1    |  0  |   Y  |  N  |                    |  是否为构建矩阵  |
|  16 |  MATRIX\_GROUP\_ID  |   varchar  |    64    |  0  |   Y  |  N  |                    |  所属的矩阵组ID |

**表名：** T\_PIPELINE\_BUILD\_DETAIL

**说明：** 流水线构建详情表

**数据列：**

|  序号 |      名称      |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :--------: | :------: | :-: | :--: | :-: | :-: | :---: |
|  1  |  PROJECT\_ID |   varchar  |    64    |  0  |   N  |  N  |     |       |
|  2  |   BUILD\_ID  |   varchar  |    34    |  0  |   N  |  Y  |     |  构建ID |
|  3  |  BUILD\_NUM  |     int    |    10    |  0  |   Y  |  N  |     |  构建次数 |
|  4  |     MODEL    | mediumtext | 16777215 |  0  |   Y  |  N  |     | 流水线模型 |
|  5  |  START\_USER |   varchar  |    32    |  0  |   Y  |  N  |     |  启动者  |
|  6  |    TRIGGER   |   varchar  |    32    |  0  |   Y  |  N  |     |  触发器  |
|  7  |  START\_TIME |  datetime  |    19    |  0  |   Y  |  N  |     |  开始时间 |
|  8  |   END\_TIME  |  datetime  |    19    |  0  |   Y  |  N  |     |  结束时间 |
|  9  |    STATUS    |   varchar  |    32    |  0  |   Y  |  N  |     |   状态  |
|  10 | CANCEL\_USER |   varchar  |    32    |  0  |   Y  |  N  |     |  取消者  |

**表名：** T\_PIPELINE\_BUILD\_HISTORY

**说明：** 流水线构建历史表

**数据列：**

|  序号 |         名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |      说明      |
| :-: | :----------------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :----------: |
|  1  |      BUILD\_ID     |   varchar  |    34    |  0  |   N  |  Y  |                    |     构建ID     |
|  2  |  PARENT\_BUILD\_ID |   varchar  |    34    |  0  |   Y  |  N  |                    |    父级构建ID    |
|  3  |  PARENT\_TASK\_ID  |   varchar  |    34    |  0  |   Y  |  N  |                    |    父级任务ID    |
|  4  |     BUILD\_NUM     |     int    |    10    |  0  |   Y  |  N  |          0         |     构建次数     |
|  5  |     PROJECT\_ID    |   varchar  |    64    |  0  |   N  |  N  |                    |     项目ID     |
|  6  |    PIPELINE\_ID    |   varchar  |    34    |  0  |   N  |  N  |                    |     流水线ID    |
|  7  |       VERSION      |     int    |    10    |  0  |   Y  |  N  |                    |      版本号     |
|  8  |     START\_USER    |   varchar  |    64    |  0  |   Y  |  N  |                    |      启动者     |
|  9  |       TRIGGER      |   varchar  |    32    |  0  |   N  |  N  |                    |      触发器     |
|  10 |     START\_TIME    |  timestamp |    19    |  0  |   Y  |  N  |                    |     开始时间     |
|  11 |      END\_TIME     |  timestamp |    19    |  0  |   Y  |  N  |                    |     结束时间     |
|  12 |       STATUS       |     int    |    10    |  0  |   Y  |  N  |                    |      状态      |
|  13 |    STAGE\_STATUS   |    text    |   65535  |  0  |   Y  |  N  |                    |   流水线各阶段状态   |
|  14 |     TASK\_COUNT    |     int    |    10    |  0  |   Y  |  N  |                    |    流水线任务数量   |
|  15 |   FIRST\_TASK\_ID  |   varchar  |    34    |  0  |   Y  |  N  |                    |    首次任务id    |
|  16 |       CHANNEL      |   varchar  |    32    |  0  |   Y  |  N  |                    |     项目渠道     |
|  17 |    TRIGGER\_USER   |   varchar  |    64    |  0  |   Y  |  N  |                    |      触发者     |
|  18 |      MATERIAL      | mediumtext | 16777215 |  0  |   Y  |  N  |                    |      原材料     |
|  19 |     QUEUE\_TIME    |  timestamp |    19    |  0  |   Y  |  N  |                    |    排队开始时间    |
|  20 |   ARTIFACT\_INFO   | mediumtext | 16777215 |  0  |   Y  |  N  |                    |    构件列表信息    |
|  21 |       REMARK       |   varchar  |   4096   |  0  |   Y  |  N  |                    |      评论      |
|  22 |    EXECUTE\_TIME   |   bigint   |    20    |  0  |   Y  |  N  |                    |     执行时间     |
|  23 |  BUILD\_PARAMETERS | mediumtext | 16777215 |  0  |   Y  |  N  |                    |    构建环境参数    |
|  24 |    WEBHOOK\_TYPE   |   varchar  |    64    |  0  |   Y  |  N  |                    |   WEBHOOK类型  |
|  25 | RECOMMEND\_VERSION |   varchar  |    64    |  0  |   Y  |  N  |                    |     推荐版本号    |
|  26 |     ERROR\_TYPE    |     int    |    10    |  0  |   Y  |  N  |                    |     错误类型     |
|  27 |     ERROR\_CODE    |     int    |    10    |  0  |   Y  |  N  |                    |      错误码     |
|  28 |     ERROR\_MSG     |    text    |   65535  |  0  |   Y  |  N  |                    |     错误描述     |
|  29 |    WEBHOOK\_INFO   |    text    |   65535  |  0  |   Y  |  N  |                    |   WEBHOOK信息  |
|  30 |      IS\_RETRY     |     bit    |     1    |  0  |   Y  |  N  |        b'0'        |     是否重试     |
|  31 |   EXECUTE\_COUNT   |     int    |    10    |  0  |   Y  |  N  |                    |     执行次数     |
|  32 |     ERROR\_INFO    |    text    |   65535  |  0  |   Y  |  N  |                    |     错误信息     |
|  33 |     BUILD\_MSG     |   varchar  |    255   |  0  |   Y  |  N  |                    |     构建信息     |
|  34 |  BUILD\_NUM\_ALIAS |   varchar  |    256   |  0  |   Y  |  N  |                    |    自定义构建号    |
|  35 | CONCURRENCY\_GROUP |   varchar  |    255   |  0  |   Y  |  N  |                    | 并发时,设定的group |
|  36 |    UPDATE\_TIME    |  datetime  |    19    |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |     更新时间     |

**表名：** T\_PIPELINE\_BUILD\_HIS\_DATA\_CLEAR

**说明：** 流水线构建数据清理统计表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :---: |
|  1  |   BUILD\_ID  |  varchar |  34 |  0  |   N  |  Y  |                       |  构建ID |
|  2  | PIPELINE\_ID |  varchar |  34 |  0  |   N  |  N  |                       | 流水线ID |
|  3  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |                       |  项目ID |
|  4  |   DEL\_TIME  | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |       |

**表名：** T\_PIPELINE\_BUILD\_RECORD\_CONTAINER

**说明：** 流水线构建容器环境表

**数据列：**

|  序号 |          名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 | 默认值 |      说明     |
| :-: | :-----------------: | :--------: | :------: | :-: | :--: | :-: | :-: | :---------: |
|  1  |      BUILD\_ID      |   varchar  |    64    |  0  |   N  |  Y  |     |     构建ID    |
|  2  |     PROJECT\_ID     |   varchar  |    64    |  0  |   N  |  N  |     |     项目ID    |
|  3  |     PIPELINE\_ID    |   varchar  |    64    |  0  |   N  |  N  |     |    流水线ID    |
|  4  |  RESOURCE\_VERSION  |     int    |    10    |  0  |   N  |  N  |     |     编排版本    |
|  5  |      STAGE\_ID      |   varchar  |    64    |  0  |   N  |  N  |     |     步骤ID    |
|  6  |    CONTAINER\_ID    |   varchar  |    64    |  0  |   N  |  Y  |     |    构建容器ID   |
|  7  |    EXECUTE\_COUNT   |     int    |    10    |  0  |   N  |  Y  |  1  |     执行次数    |
|  8  |        STATUS       |   varchar  |    32    |  0  |   Y  |  N  |     |     构建状态    |
|  9  |    CONTAINER\_VAR   | mediumtext | 16777215 |  0  |   N  |  N  |     |  当次执行的变量记录  |
|  10 |   CONTAINER\_TYPE   |   varchar  |    45    |  0  |   Y  |  N  |     |     容器类型    |
|  11 | CONTAIN\_POST\_TASK |     bit    |     1    |  0  |   Y  |  N  |     |  包含POST插件标识 |
|  12 | MATRIX\_GROUP\_FLAG |     bit    |     1    |  0  |   Y  |  N  |     |     矩阵标识    |
|  13 |  MATRIX\_GROUP\_ID  |   varchar  |    64    |  0  |   Y  |  N  |     |   所属的矩阵组ID  |
|  14 |     START\_TIME     |  datetime  |    23    |  0  |   Y  |  N  |     |     开始时间    |
|  15 |      END\_TIME      |  datetime  |    23    |  0  |   Y  |  N  |     |     结束时间    |
|  16 |      TIMESTAMPS     |    text    |   65535  |  0  |   Y  |  N  |     | 运行中产生的时间戳集合 |

**表名：** T\_PIPELINE\_BUILD\_RECORD\_MODEL

**说明：** 流水线构建详情表

**数据列：**

|  序号 |         名称        |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |          默认值          |      说明     |
| :-: | :---------------: | :--------: | :------: | :-: | :--: | :-: | :-------------------: | :---------: |
|  1  |     BUILD\_ID     |   varchar  |    34    |  0  |   N  |  Y  |                       |     构建ID    |
|  2  |    PROJECT\_ID    |   varchar  |    64    |  0  |   N  |  N  |                       |     项目ID    |
|  3  |    PIPELINE\_ID   |   varchar  |    34    |  0  |   N  |  N  |                       |    流水线ID    |
|  4  | RESOURCE\_VERSION |     int    |    10    |  0  |   N  |  N  |                       |     编排版本    |
|  5  |     BUILD\_NUM    |     int    |    10    |  0  |   N  |  N  |                       |     构建次数    |
|  6  |   EXECUTE\_COUNT  |     int    |    10    |  0  |   N  |  Y  |                       |     执行次数    |
|  7  |    START\_USER    |   varchar  |    32    |  0  |   N  |  N  |                       |     启动者     |
|  8  |     MODEL\_VAR    | mediumtext | 16777215 |  0  |   N  |  N  |                       |  当次执行的变量记录  |
|  9  |    START\_TYPE    |   varchar  |    32    |  0  |   N  |  N  |                       |     触发方式    |
|  10 |    QUEUE\_TIME    |  datetime  |    23    |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |     触发时间    |
|  11 |    START\_TIME    |  datetime  |    23    |  0  |   Y  |  N  |                       |     启动时间    |
|  12 |     END\_TIME     |  datetime  |    23    |  0  |   Y  |  N  |                       |     结束时间    |
|  13 |       STATUS      |   varchar  |    32    |  0  |   Y  |  N  |                       |     构建状态    |
|  14 |    ERROR\_INFO    |    text    |   65535  |  0  |   Y  |  N  |                       |     错误信息    |
|  15 |    CANCEL\_USER   |   varchar  |    32    |  0  |   Y  |  N  |                       |     取消者     |
|  16 |     TIMESTAMPS    |    text    |   65535  |  0  |   Y  |  N  |                       | 运行中产生的时间戳集合 |

**表名：** T\_PIPELINE\_BUILD\_RECORD\_STAGE

**说明：** 流水线构建阶段表

**数据列：**

|  序号 |         名称        |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |      说明     |
| :-: | :---------------: | :------: | :---: | :-: | :--: | :-: | :-: | :---------: |
|  1  |     BUILD\_ID     |  varchar |   64  |  0  |   N  |  Y  |     |     构建ID    |
|  2  |    PROJECT\_ID    |  varchar |   64  |  0  |   N  |  N  |     |     项目ID    |
|  3  |    PIPELINE\_ID   |  varchar |   64  |  0  |   N  |  N  |     |    流水线ID    |
|  4  | RESOURCE\_VERSION |    int   |   10  |  0  |   Y  |  N  |     |    编排版本号    |
|  5  |     STAGE\_ID     |  varchar |   64  |  0  |   N  |  Y  |     |     步骤ID    |
|  6  |        SEQ        |    int   |   10  |  0  |   N  |  N  |     |     步骤序列    |
|  7  |     STAGE\_VAR    |   text   | 65535 |  0  |   N  |  N  |     |  当次执行的变量记录  |
|  8  |       STATUS      |  varchar |   32  |  0  |   Y  |  N  |     |     构建状态    |
|  9  |   EXECUTE\_COUNT  |    int   |   10  |  0  |   N  |  Y  |  1  |     执行次数    |
|  10 |    START\_TIME    | datetime |   23  |  0  |   Y  |  N  |     |     开始时间    |
|  11 |     END\_TIME     | datetime |   23  |  0  |   Y  |  N  |     |     结束时间    |
|  12 |     TIMESTAMPS    |   text   | 65535 |  0  |   Y  |  N  |     | 运行中产生的时间戳集合 |

**表名：** T\_PIPELINE\_BUILD\_RECORD\_TASK

**说明：** 流水线构建任务表

**数据列：**

|  序号 |          名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 | 默认值 |       说明      |
| :-: | :-----------------: | :--------: | :------: | :-: | :--: | :-: | :-: | :-----------: |
|  1  |      BUILD\_ID      |   varchar  |    34    |  0  |   N  |  Y  |     |      构建ID     |
|  2  |     PROJECT\_ID     |   varchar  |    64    |  0  |   N  |  N  |     |      项目ID     |
|  3  |     PIPELINE\_ID    |   varchar  |    34    |  0  |   N  |  N  |     |     流水线ID     |
|  4  |  RESOURCE\_VERSION  |     int    |    10    |  0  |   N  |  N  |     |     编排版本号     |
|  5  |      STAGE\_ID      |   varchar  |    34    |  0  |   N  |  N  |     |      步骤ID     |
|  6  |    CONTAINER\_ID    |   varchar  |    34    |  0  |   N  |  N  |     |     构建容器ID    |
|  7  |       TASK\_ID      |   varchar  |    34    |  0  |   N  |  Y  |     |      任务ID     |
|  8  |      TASK\_SEQ      |     int    |    10    |  0  |   N  |  N  |  1  |      任务序列     |
|  9  |    EXECUTE\_COUNT   |     int    |    10    |  0  |   N  |  Y  |  1  |      执行次数     |
|  10 |        STATUS       |   varchar  |    32    |  0  |   Y  |  N  |     |      构建状态     |
|  11 |      TASK\_VAR      | mediumtext | 16777215 |  0  |   N  |  N  |     |   当次执行的变量记录   |
|  12 |      POST\_INFO     |    text    |   65535  |  0  |   Y  |  N  |     | 市场插件的POST关联信息 |
|  13 |     CLASS\_TYPE     |   varchar  |    64    |  0  |   N  |  N  |     |      项目ID     |
|  14 |      ATOM\_CODE     |   varchar  |    128   |  0  |   N  |  N  |     |    插件的唯一标识    |
|  15 | ORIGIN\_CLASS\_TYPE |   varchar  |    64    |  0  |   Y  |  N  |     |    所在矩阵组ID    |
|  16 |     START\_TIME     |  datetime  |    23    |  0  |   Y  |  N  |     |      开始时间     |
|  17 |      END\_TIME      |  datetime  |    23    |  0  |   Y  |  N  |     |      结束时间     |
|  18 |      TIMESTAMPS     |    text    |   65535  |  0  |   Y  |  N  |     |  运行中产生的时间戳集合  |

**表名：** T\_PIPELINE\_BUILD\_STAGE

**说明：** 流水线构建阶段表

**数据列：**

|  序号 |       名称       |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |     说明    |
| :-: | :------------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :-------: |
|  1  |   PROJECT\_ID  |   varchar  |    64    |  0  |   N  |  N  |                    |    项目ID   |
|  2  |  PIPELINE\_ID  |   varchar  |    64    |  0  |   N  |  N  |                    |   流水线ID   |
|  3  |    BUILD\_ID   |   varchar  |    64    |  0  |   N  |  Y  |                    |    构建ID   |
|  4  |    STAGE\_ID   |   varchar  |    64    |  0  |   N  |  Y  |                    | 当前stageId |
|  5  |       SEQ      |     int    |    10    |  0  |   N  |  N  |                    |           |
|  6  |     STATUS     |     int    |    10    |  0  |   Y  |  N  |                    |     状态    |
|  7  |   START\_TIME  |  timestamp |    19    |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |    开始时间   |
|  8  |    END\_TIME   |  timestamp |    19    |  0  |   Y  |  N  |                    |    结束时间   |
|  9  |      COST      |     int    |    10    |  0  |   Y  |  N  |          0         |     花费    |
|  10 | EXECUTE\_COUNT |     int    |    10    |  0  |   Y  |  N  |          1         |    执行次数   |
|  11 |   CONDITIONS   | mediumtext | 16777215 |  0  |   Y  |  N  |                    |     状况    |
|  12 |    CHECK\_IN   | mediumtext | 16777215 |  0  |   Y  |  N  |                    |   准入检查配置  |
|  13 |   CHECK\_OUT   | mediumtext | 16777215 |  0  |   Y  |  N  |                    |   准出检查配置  |

**表名：** T\_PIPELINE\_BUILD\_SUMMARY

**说明：** 流水线构建摘要表

**数据列：**

|  序号 |          名称         |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :-----------------: | :-------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |     PIPELINE\_ID    |  varchar  |  34 |  0  |   N  |  Y  |     |  流水线ID |
|  2  |     PROJECT\_ID     |  varchar  |  64 |  0  |   N  |  N  |     |  项目ID  |
|  3  |      BUILD\_NUM     |    int    |  10 |  0  |   Y  |  N  |  0  |  构建次数  |
|  4  |      BUILD\_NO      |    int    |  10 |  0  |   Y  |  N  |  0  |   构建号  |
|  5  |    FINISH\_COUNT    |    int    |  10 |  0  |   Y  |  N  |  0  |  完成次数  |
|  6  |    RUNNING\_COUNT   |    int    |  10 |  0  |   Y  |  N  |  0  |  运行次数  |
|  7  |     QUEUE\_COUNT    |    int    |  10 |  0  |   Y  |  N  |  0  |  排队次数  |
|  8  |  LATEST\_BUILD\_ID  |  varchar  |  34 |  0  |   Y  |  N  |     | 最近构建ID |
|  9  |   LATEST\_TASK\_ID  |  varchar  |  34 |  0  |   Y  |  N  |     | 最近任务ID |
|  10 | LATEST\_START\_USER |  varchar  |  64 |  0  |   Y  |  N  |     |  最近启动者 |
|  11 | LATEST\_START\_TIME | timestamp |  19 |  0  |   Y  |  N  |     | 最近启动时间 |
|  12 |  LATEST\_END\_TIME  | timestamp |  19 |  0  |   Y  |  N  |     | 最近结束时间 |
|  13 | LATEST\_TASK\_COUNT |    int    |  10 |  0  |   Y  |  N  |     | 最近任务计数 |
|  14 |  LATEST\_TASK\_NAME |  varchar  | 128 |  0  |   Y  |  N  |     | 最近任务名称 |
|  15 |    LATEST\_STATUS   |    int    |  10 |  0  |   Y  |  N  |     |  最近状态  |
|  16 |  BUILD\_NUM\_ALIAS  |  varchar  | 256 |  0  |   Y  |  N  |     | 自定义构建号 |

**表名：** T\_PIPELINE\_BUILD\_TASK

**说明：** 流水线构建任务表

**数据列：**

|  序号 |           名称          |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 | 默认值 |      说明     |
| :-: | :-------------------: | :--------: | :------: | :-: | :--: | :-: | :-: | :---------: |
|  1  |      PIPELINE\_ID     |   varchar  |    34    |  0  |   N  |  N  |     |    流水线ID    |
|  2  |      PROJECT\_ID      |   varchar  |    64    |  0  |   N  |  N  |     |     项目ID    |
|  3  |       BUILD\_ID       |   varchar  |    34    |  0  |   N  |  Y  |     |     构建ID    |
|  4  |       STAGE\_ID       |   varchar  |    34    |  0  |   N  |  N  |     |  当前stageId  |
|  5  |     CONTAINER\_ID     |   varchar  |    34    |  0  |   N  |  N  |     |    构建容器ID   |
|  6  |       TASK\_NAME      |   varchar  |    128   |  0  |   Y  |  N  |     |     任务名称    |
|  7  |        TASK\_ID       |   varchar  |    34    |  0  |   N  |  Y  |     |     任务ID    |
|  8  |      TASK\_PARAMS     | mediumtext | 16777215 |  0  |   Y  |  N  |     |    任务参数集合   |
|  9  |       TASK\_TYPE      |   varchar  |    64    |  0  |   N  |  N  |     |     任务类型    |
|  10 |       TASK\_ATOM      |   varchar  |    128   |  0  |   Y  |  N  |     |   任务atom代码  |
|  11 |       ATOM\_CODE      |   varchar  |    128   |  0  |   Y  |  N  |     |   插件的唯一标识   |
|  12 |      START\_TIME      |  timestamp |    19    |  0  |   Y  |  N  |     |     开始时间    |
|  13 |       END\_TIME       |  timestamp |    19    |  0  |   Y  |  N  |     |     结束时间    |
|  14 |        STARTER        |   varchar  |    64    |  0  |   N  |  N  |     |     执行人     |
|  15 |        APPROVER       |   varchar  |    64    |  0  |   Y  |  N  |     |     批准人     |
|  16 |         STATUS        |     int    |    10    |  0  |   Y  |  N  |     |      状态     |
|  17 |     EXECUTE\_COUNT    |     int    |    10    |  0  |   Y  |  N  |  0  |     执行次数    |
|  18 |       TASK\_SEQ       |     int    |    10    |  0  |   Y  |  N  |  1  |     任务序列    |
|  19 |    SUB\_PROJECT\_ID   |   varchar  |    64    |  0  |   Y  |  N  |     |    子项目id    |
|  20 |     SUB\_BUILD\_ID    |   varchar  |    34    |  0  |   Y  |  N  |     |    子构建id    |
|  21 |    CONTAINER\_TYPE    |   varchar  |    45    |  0  |   Y  |  N  |     |     容器类型    |
|  22 |  ADDITIONAL\_OPTIONS  | mediumtext | 16777215 |  0  |   Y  |  N  |     |     其他选项    |
|  23 |      TOTAL\_TIME      |   bigint   |    20    |  0  |   Y  |  N  |     |     总共时间    |
|  24 |      ERROR\_TYPE      |     int    |    10    |  0  |   Y  |  N  |     |     错误类型    |
|  25 |      ERROR\_CODE      |     int    |    10    |  0  |   Y  |  N  |     |     错误码     |
|  26 |       ERROR\_MSG      |    text    |   65535  |  0  |   Y  |  N  |     |     错误描述    |
|  27 |     PLATFORM\_CODE    |   varchar  |    64    |  0  |   Y  |  N  |     |    对接平台代码   |
|  28 | PLATFORM\_ERROR\_CODE |     int    |    10    |  0  |   Y  |  N  |     |   对接平台错误码   |
|  29 |  CONTAINER\_HASH\_ID  |   varchar  |    64    |  0  |   Y  |  N  |     |  构建Job唯一标识  |
|  30 |        STEP\_ID       |   varchar  |    64    |  0  |   Y  |  N  |     | 标识上下文的自定义ID |

**表名：** T\_PIPELINE\_BUILD\_TEMPLATE\_ACROSS\_INFO

**说明：** 流水线模板跨项目访问表

**数据列：**

|  序号 |            名称           |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |          说明          |
| :-: | :---------------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :------------------: |
|  1  |            ID           |   bigint  |   20  |  0  |   N  |  Y  |                    |         主键ID         |
|  2  |       TEMPLATE\_ID      |    char   |   34  |  0  |   N  |  N  |                    |       模板唯一UUID       |
|  3  |       PROJECT\_ID       |  varchar  |   64  |  0  |   N  |  N  |                    |         项目ID         |
|  4  |       PIPELINE\_ID      |  varchar  |   34  |  0  |   N  |  N  |                    | 流水线ID（P-32位UUID)=34位 |
|  5  |        BUILD\_ID        |  varchar  |   34  |  0  |   Y  |  N  |                    |         构建ID         |
|  6  |      TEMPLATE\_TYPE     |  varchar  |   64  |  0  |   N  |  N  |                    |         模板类型         |
|  7  | TEMPLATE\_INSTANCE\_IDS |    text   | 65535 |  0  |   N  |  N  |                    |       模板对应的实例ID      |
|  8  |   TARGET\_PROJECT\_ID   |  varchar  |   64  |  0  |   N  |  N  |                    |        使用的项目ID       |
|  9  |       CREATE\_TIME      | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |         创建时间         |
|  10 |         CREATOR         |  varchar  |   64  |  0  |   N  |  N  |                    |          创建人         |

**表名：** T\_PIPELINE\_BUILD\_VAR

**说明：** 流水线变量表

**数据列：**

|  序号 |      名称      |   数据类型  |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :-----: | :--: | :-: | :--: | :-: | :-: | :---: |
|  1  |   BUILD\_ID  | varchar |  34  |  0  |   N  |  Y  |     |  构建ID |
|  2  |      KEY     | varchar |  255 |  0  |   N  |  Y  |     |   键   |
|  3  |     VALUE    | varchar | 4000 |  0  |   Y  |  N  |     |   值   |
|  4  |  PROJECT\_ID | varchar |  64  |  0  |   Y  |  N  |     |  项目ID |
|  5  | PIPELINE\_ID | varchar |  64  |  0  |   Y  |  N  |     | 流水线ID |
|  6  |   VAR\_TYPE  | varchar |  64  |  0  |   Y  |  N  |     |  变量类型 |
|  7  |  READ\_ONLY  |   bit   |   1  |  0  |   Y  |  N  |     |  是否只读 |

**表名：** T\_PIPELINE\_DATA\_CLEAR

**说明：** 流水线数据清理统计表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :---: |
|  1  | PIPELINE\_ID |  varchar |  34 |  0  |   N  |  Y  |                       | 流水线ID |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |                       |  项目ID |
|  3  |   DEL\_TIME  | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |       |

**表名：** T\_PIPELINE\_FAVOR

**说明：** 流水线收藏表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |     |  项目ID |
|  3  | PIPELINE\_ID |  varchar |  64 |  0  |   N  |  N  |     | 流水线ID |
|  4  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间 |
|  5  | CREATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  创建者  |

**表名：** T\_PIPELINE\_GROUP

**说明：** 流水线分组表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :--: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     | 主键ID |
|  2  |  PROJECT\_ID |  varchar |  32 |  0  |   N  |  N  |     | 项目ID |
|  3  |     NAME     |  varchar |  64 |  0  |   N  |  N  |     |  名称  |
|  4  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     | 创建时间 |
|  5  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  |     | 更新时间 |
|  6  | CREATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  创建者 |
|  7  | UPDATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  修改人 |

**表名：** T\_PIPELINE\_INFO

**说明：** 流水线信息表

**数据列：**

|  序号 |           名称           |    数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :--------------------: | :-------: | :--: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |      PIPELINE\_ID      |  varchar  |  34  |  0  |   N  |  Y  |                    |  流水线ID  |
|  2  |       PROJECT\_ID      |  varchar  |  64  |  0  |   N  |  N  |                    |   项目ID  |
|  3  |     PIPELINE\_NAME     |  varchar  |  255 |  0  |   N  |  N  |                    |  流水线名称  |
|  4  |     PIPELINE\_DESC     |  varchar  |  255 |  0  |   Y  |  N  |                    |  流水线描述  |
|  5  |         VERSION        |    int    |  10  |  0  |   Y  |  N  |          1         |   版本号   |
|  6  |      CREATE\_TIME      | timestamp |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   创建时间  |
|  7  |         CREATOR        |  varchar  |  64  |  0  |   N  |  N  |                    |   创建者   |
|  8  |      UPDATE\_TIME      | timestamp |  19  |  0  |   Y  |  N  |                    |   更新时间  |
|  9  |   LAST\_MODIFY\_USER   |  varchar  |  64  |  0  |   N  |  N  |                    |  最近修改者  |
|  10 |         CHANNEL        |  varchar  |  32  |  0  |   Y  |  N  |                    |   项目渠道  |
|  11 |     MANUAL\_STARTUP    |    int    |  10  |  0  |   Y  |  N  |          1         |  是否手工启动 |
|  12 |      ELEMENT\_SKIP     |    int    |  10  |  0  |   Y  |  N  |          0         |  是否跳过插件 |
|  13 |       TASK\_COUNT      |    int    |  10  |  0  |   Y  |  N  |          0         | 流水线任务数量 |
|  14 |         DELETE         |    bit    |   1  |  0  |   Y  |  N  |        b'0'        |   是否删除  |
|  15 |           ID           |   bigint  |  20  |  0  |   N  |  N  |                    |   主键ID  |
|  16 | PIPELINE\_NAME\_PINYIN |  varchar  | 1300 |  0  |   Y  |  N  |                    | 流水线名称拼音 |
|  17 |   LATEST\_START\_TIME  |  datetime |  23  |  0  |   Y  |  N  |                    |  最近启动时间 |

**表名：** T\_PIPELINE\_JOB\_MUTEX\_GROUP

**说明：**

**数据列：**

|  序号 |            名称           |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |    说明    |
| :-: | :---------------------: | :-----: | :-: | :-: | :--: | :-: | :-: | :------: |
|  1  |       PROJECT\_ID       | varchar |  64 |  0  |   N  |  Y  |     |   项目ID   |
|  2  | JOB\_MUTEX\_GROUP\_NAME | varchar | 127 |  0  |   N  |  Y  |     | Job互斥组名字 |

**表名：** T\_PIPELINE\_LABEL

**说明：** 流水线标签表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |     |  项目ID |
|  3  |   GROUP\_ID  |  bigint  |  20 |  0  |   N  |  N  |     | 用户组ID |
|  4  |     NAME     |  varchar |  64 |  0  |   N  |  N  |     |   名称  |
|  5  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间 |
|  6  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  更新时间 |
|  7  | CREATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  创建者  |
|  8  | UPDATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  修改人  |

**表名：** T\_PIPELINE\_LABEL\_PIPELINE

**说明：** 流水线-标签映射表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |     |  项目ID |
|  3  | PIPELINE\_ID |  varchar |  34 |  0  |   N  |  N  |     | 流水线ID |
|  4  |   LABEL\_ID  |  bigint  |  20 |  0  |   N  |  N  |     |  标签ID |
|  5  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间 |
|  6  | CREATE\_USER |  varchar |  64 |  0  |   N  |  N  |     |  创建者  |

**表名：** T\_PIPELINE\_MODEL\_TASK

**说明：** 流水线模型task任务表

**数据列：**

|  序号 |          名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 | 默认值 |     说明    |
| :-: | :-----------------: | :--------: | :------: | :-: | :--: | :-: | :-: | :-------: |
|  1  |     PIPELINE\_ID    |   varchar  |    64    |  0  |   N  |  Y  |     |   流水线ID   |
|  2  |     PROJECT\_ID     |   varchar  |    64    |  0  |   N  |  Y  |     |    项目ID   |
|  3  |      STAGE\_ID      |   varchar  |    64    |  0  |   N  |  Y  |     | 当前stageId |
|  4  |    CONTAINER\_ID    |   varchar  |    64    |  0  |   N  |  Y  |     |   构建容器ID  |
|  5  |       TASK\_ID      |   varchar  |    64    |  0  |   N  |  Y  |     |    任务ID   |
|  6  |      TASK\_NAME     |   varchar  |    128   |  0  |   Y  |  N  |     |    任务名称   |
|  7  |     CLASS\_TYPE     |   varchar  |    64    |  0  |   N  |  N  |     |    插件大类   |
|  8  |      TASK\_ATOM     |   varchar  |    128   |  0  |   Y  |  N  |     |  任务atom代码 |
|  9  |      TASK\_SEQ      |     int    |    10    |  0  |   Y  |  N  |  1  |    任务序列   |
|  10 |     TASK\_PARAMS    | mediumtext | 16777215 |  0  |   Y  |  N  |     |   任务参数集合  |
|  11 |          OS         |   varchar  |    45    |  0  |   Y  |  N  |     |    操作系统   |
|  12 | ADDITIONAL\_OPTIONS | mediumtext | 16777215 |  0  |   Y  |  N  |     |    其他选项   |
|  13 |      ATOM\_CODE     |   varchar  |    32    |  0  |   N  |  N  |     |  插件的唯一标识  |
|  14 |    ATOM\_VERSION    |   varchar  |    30    |  0  |   Y  |  N  |     |   插件版本号   |
|  15 |     CREATE\_TIME    |  datetime  |    23    |  0  |   Y  |  N  |     |    创建时间   |
|  16 |     UPDATE\_TIME    |  datetime  |    23    |  0  |   Y  |  N  |     |    更新时间   |

**表名：** T\_PIPELINE\_PAUSE\_VALUE

**说明：** 流水线暂停变量表

**数据列：**

|  序号 |       名称       |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |     说明     |
| :-: | :------------: | :-------: | :---: | :-: | :--: | :-: | :-: | :--------: |
|  1  |   PROJECT\_ID  |  varchar  |   64  |  0  |   N  |  N  |     |            |
|  2  |    BUILD\_ID   |  varchar  |   34  |  0  |   N  |  N  |     |    构建ID    |
|  3  |    TASK\_ID    |  varchar  |   34  |  0  |   N  |  N  |     |    任务ID    |
|  4  | DEFAULT\_VALUE |    text   | 65535 |  0  |   Y  |  N  |     |    默认变量    |
|  5  |   NEW\_VALUE   |    text   | 65535 |  0  |   Y  |  N  |     | 暂停后用户提供的变量 |
|  6  |  CREATE\_TIME  | timestamp |   19  |  0  |   Y  |  N  |     |    添加时间    |
|  7  | EXECUTE\_COUNT |    int    |   10  |  0  |   Y  |  N  |     |    执行次数    |

**表名：** T\_PIPELINE\_RECENT\_USE

**说明：** 最近使用的流水线

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  Y  |     |  项目ID |
|  2  |   USER\_ID   |  varchar |  64 |  0  |   N  |  Y  |     |  用户ID |
|  3  | PIPELINE\_ID |  varchar |  64 |  0  |   N  |  Y  |     | 流水线ID |
|  4  |   USE\_TIME  | datetime |  19 |  0  |   N  |  N  |     |  使用时间 |

**表名：** T\_PIPELINE\_REMOTE\_AUTH

**说明：** 流水线远程触发auth表

**数据列：**

|  序号 |       名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :------------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |  PIPELINE\_ID  |  varchar |  34 |  0  |   N  |  Y  |     | 流水线ID |
|  2  | PIPELINE\_AUTH |  varchar |  32 |  0  |   N  |  N  |     | 流水线权限 |
|  3  |   PROJECT\_ID  |  varchar |  32 |  0  |   N  |  N  |     |  项目ID |
|  4  |  CREATE\_TIME  | datetime |  19 |  0  |   N  |  N  |     |  创建时间 |
|  5  |  CREATE\_USER  |  varchar |  64 |  0  |   N  |  N  |     |  创建者  |

**表名：** T\_PIPELINE\_RESOURCE

**说明：** 流水线资源表

**数据列：**

|  序号 |      名称      |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |   说明  |
| :-: | :----------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :---: |
|  1  |  PROJECT\_ID |   varchar  |    64    |  0  |   N  |  N  |                    |  项目ID |
|  2  | PIPELINE\_ID |   varchar  |    34    |  0  |   N  |  Y  |                    | 流水线ID |
|  3  |    VERSION   |     int    |    10    |  0  |   N  |  Y  |          1         |  版本号  |
|  4  |     MODEL    | mediumtext | 16777215 |  0  |   Y  |  N  |                    | 流水线模型 |
|  5  |    CREATOR   |   varchar  |    64    |  0  |   Y  |  N  |                    |  创建者  |
|  6  | CREATE\_TIME |  timestamp |    19    |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  创建时间 |

**表名：** T\_PIPELINE\_RESOURCE\_VERSION

**说明：** 流水线资源版本表

**数据列：**

|  序号 |       名称      |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |        说明       |
| :-: | :-----------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :-------------: |
|  1  |  PROJECT\_ID  |   varchar  |    64    |  0  |   N  |  N  |                    |       项目ID      |
|  2  |  PIPELINE\_ID |   varchar  |    34    |  0  |   N  |  Y  |                    |      流水线ID      |
|  3  |    VERSION    |     int    |    10    |  0  |   N  |  Y  |          1         |       版本号       |
|  4  | VERSION\_NAME |   varchar  |    64    |  0  |   N  |  N  |                    |       版本名称      |
|  5  |     MODEL     | mediumtext | 16777215 |  0  |   Y  |  N  |                    |      流水线模型      |
|  6  |  REFER\_FLAG  |     bit    |     1    |  0  |   Y  |  N  |                    | 是否还有构建记录引用该版本标识 |
|  7  |  REFER\_COUNT |     int    |    10    |  0  |   Y  |  N  |                    |     关联构建记录总数    |
|  8  |    CREATOR    |   varchar  |    64    |  0  |   Y  |  N  |                    |       创建者       |
|  9  |  CREATE\_TIME |  timestamp |    19    |  0  |   N  |  N  | CURRENT\_TIMESTAMP |       创建时间      |

**表名：** T\_PIPELINE\_RULE

**说明：** 流水线规则信息表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :--: |
|  1  |      ID      |  varchar |  32 |  0  |   N  |  Y  |                       | 主键ID |
|  2  |  RULE\_NAME  |  varchar | 256 |  0  |   N  |  N  |                       | 规则名称 |
|  3  |   BUS\_CODE  |  varchar | 128 |  0  |   N  |  N  |                       | 业务标识 |
|  4  |   PROCESSOR  |  varchar | 128 |  0  |   N  |  N  |                       |  处理器 |
|  5  |    CREATOR   |  varchar |  50 |  0  |   N  |  N  |         system        |  创建者 |
|  6  |   MODIFIER   |  varchar |  50 |  0  |   N  |  N  |         system        |  修改者 |
|  7  | UPDATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) | 修改时间 |
|  8  | CREATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) | 创建时间 |

**表名：** T\_PIPELINE\_SETTING

**说明：** 流水线基础配置表

**数据列：**

|  序号 |                   名称                   |    数据类型    |     长度     | 小数位 | 允许空值 |  主键 |  默认值 |            说明            |
| :-: | :------------------------------------: | :--------: | :--------: | :-: | :--: | :-: | :--: | :----------------------: |
|  1  |              PIPELINE\_ID              |   varchar  |     34     |  0  |   N  |  Y  |      |           流水线ID          |
|  2  |                  DESC                  |   varchar  |    1024    |  0  |   Y  |  N  |      |            描述            |
|  3  |                RUN\_TYPE               |     int    |     10     |  0  |   Y  |  N  |      |                          |
|  4  |                  NAME                  |   varchar  |     255    |  0  |   Y  |  N  |      |            名称            |
|  5  |            SUCCESS\_RECEIVER           | mediumtext |  16777215  |  0  |   Y  |  N  |      |           成功接受者          |
|  6  |             FAIL\_RECEIVER             | mediumtext |  16777215  |  0  |   Y  |  N  |      |           失败接受者          |
|  7  |             SUCCESS\_GROUP             | mediumtext |  16777215  |  0  |   Y  |  N  |      |            成功组           |
|  8  |               FAIL\_GROUP              | mediumtext |  16777215  |  0  |   Y  |  N  |      |            失败组           |
|  9  |              SUCCESS\_TYPE             |   varchar  |     32     |  0  |   Y  |  N  |      |          成功的通知方式         |
|  10 |               FAIL\_TYPE               |   varchar  |     32     |  0  |   Y  |  N  |      |          失败的通知方式         |
|  11 |               PROJECT\_ID              |   varchar  |     64     |  0  |   Y  |  N  |      |           项目ID           |
|  12 |      SUCCESS\_WECHAT\_GROUP\_FLAG      |     bit    |      1     |  0  |   N  |  N  | b'0' |       成功的企业微信群通知开关       |
|  13 |         SUCCESS\_WECHAT\_GROUP         |   varchar  |    1024    |  0  |   N  |  N  |      |       成功的企业微信群通知群ID      |
|  14 |        FAIL\_WECHAT\_GROUP\_FLAG       |     bit    |      1     |  0  |   N  |  N  | b'0' |       失败的企业微信群通知开关       |
|  15 |           FAIL\_WECHAT\_GROUP          |   varchar  |    1024    |  0  |   N  |  N  |      |       失败的企业微信群通知群ID      |
|  16 |             RUN\_LOCK\_TYPE            |     int    |     10     |  0  |   Y  |  N  |   1  |          Lock类型          |
|  17 |          SUCCESS\_DETAIL\_FLAG         |     bit    |      1     |  0  |   Y  |  N  | b'0' |      成功的通知的流水线详情连接开关     |
|  18 |           FAIL\_DETAIL\_FLAG           |     bit    |      1     |  0  |   Y  |  N  | b'0' |      失败的通知的流水线详情连接开关     |
|  19 |            SUCCESS\_CONTENT            |  longtext  | 2147483647 |  0  |   Y  |  N  |      |        成功的自定义通知内容        |
|  20 |              FAIL\_CONTENT             |  longtext  | 2147483647 |  0  |   Y  |  N  |      |        失败的自定义通知内容        |
|  21 |        WAIT\_QUEUE\_TIME\_SECOND       |     int    |     10     |  0  |   Y  |  N  | 7200 |          最大排队时长          |
|  22 |            MAX\_QUEUE\_SIZE            |     int    |     10     |  0  |   Y  |  N  |  10  |          最大排队数量          |
|  23 |              IS\_TEMPLATE              |     bit    |      1     |  0  |   Y  |  N  | b'0' |           是否模板           |
|  24 | SUCCESS\_WECHAT\_GROUP\_MARKDOWN\_FLAG |     bit    |      1     |  0  |   N  |  N  | b'0' | 成功的企业微信群通知转为Markdown格式开关 |
|  25 |   FAIL\_WECHAT\_GROUP\_MARKDOWN\_FLAG  |     bit    |      1     |  0  |   N  |  N  | b'0' | 失败的企业微信群通知转为Markdown格式开关 |
|  26 |         MAX\_PIPELINE\_RES\_NUM        |     int    |     10     |  0  |   Y  |  N  |  500 |       保存流水线编排的最大个数       |
|  27 |     MAX\_CON\_RUNNING\_QUEUE\_SIZE     |     int    |     10     |  0  |   Y  |  N  |  50  |         并发构建数量限制         |
|  28 |            BUILD\_NUM\_RULE            |   varchar  |     512    |  0  |   Y  |  N  |      |          构建号生成规则         |
|  29 |           CONCURRENCY\_GROUP           |   varchar  |     255    |  0  |   Y  |  N  |      |       并发时,设定的group       |
|  30 |    CONCURRENCY\_CANCEL\_IN\_PROGRESS   |     bit    |      1     |  0  |   Y  |  N  | b'0' |  并发时,是否相同group取消正在执行的流水线 |
|  31 |      CLEAN\_VARIABLES\_WHEN\_RETRY     |     bit    |      1     |  0  |   Y  |  N  | b'0' |         重试时清理变量表         |
|  32 |      PIPELINE\_AS\_CODE\_SETTINGS      |   varchar  |     512    |  0  |   Y  |  N  |      |        YAML流水线相关配置       |

**表名：** T\_PIPELINE\_SETTING\_VERSION

**说明：** 流水线基础配置版本表

**数据列：**

|  序号 |                   名称                   |    数据类型    |     长度     | 小数位 | 允许空值 |  主键 |  默认值 |            说明            |
| :-: | :------------------------------------: | :--------: | :--------: | :-: | :--: | :-: | :--: | :----------------------: |
|  1  |                   ID                   |   bigint   |     20     |  0  |   N  |  Y  |      |           主键ID           |
|  2  |              PIPELINE\_ID              |   varchar  |     34     |  0  |   N  |  N  |      |           流水线ID          |
|  3  |            SUCCESS\_RECEIVER           | mediumtext |  16777215  |  0  |   Y  |  N  |      |           成功接受者          |
|  4  |             FAIL\_RECEIVER             | mediumtext |  16777215  |  0  |   Y  |  N  |      |           失败接受者          |
|  5  |             SUCCESS\_GROUP             | mediumtext |  16777215  |  0  |   Y  |  N  |      |            成功组           |
|  6  |               FAIL\_GROUP              | mediumtext |  16777215  |  0  |   Y  |  N  |      |            失败组           |
|  7  |              SUCCESS\_TYPE             |   varchar  |     32     |  0  |   Y  |  N  |      |          成功的通知方式         |
|  8  |               FAIL\_TYPE               |   varchar  |     32     |  0  |   Y  |  N  |      |          失败的通知方式         |
|  9  |               PROJECT\_ID              |   varchar  |     64     |  0  |   Y  |  N  |      |           项目ID           |
|  10 |      SUCCESS\_WECHAT\_GROUP\_FLAG      |     bit    |      1     |  0  |   N  |  N  | b'0' |       成功的企业微信群通知开关       |
|  11 |         SUCCESS\_WECHAT\_GROUP         |   varchar  |    1024    |  0  |   N  |  N  |      |       成功的企业微信群通知群ID      |
|  12 |        FAIL\_WECHAT\_GROUP\_FLAG       |     bit    |      1     |  0  |   N  |  N  | b'0' |       失败的企业微信群通知开关       |
|  13 |           FAIL\_WECHAT\_GROUP          |   varchar  |    1024    |  0  |   N  |  N  |      |       失败的企业微信群通知群ID      |
|  14 |          SUCCESS\_DETAIL\_FLAG         |     bit    |      1     |  0  |   Y  |  N  | b'0' |      成功的通知的流水线详情连接开关     |
|  15 |           FAIL\_DETAIL\_FLAG           |     bit    |      1     |  0  |   Y  |  N  | b'0' |      失败的通知的流水线详情连接开关     |
|  16 |            SUCCESS\_CONTENT            |  longtext  | 2147483647 |  0  |   Y  |  N  |      |        成功的自定义通知内容        |
|  17 |              FAIL\_CONTENT             |  longtext  | 2147483647 |  0  |   Y  |  N  |      |        失败的自定义通知内容        |
|  18 |              IS\_TEMPLATE              |     bit    |      1     |  0  |   Y  |  N  | b'0' |           是否模板           |
|  19 |                 VERSION                |     int    |     10     |  0  |   N  |  N  |   1  |            版本号           |
|  20 | SUCCESS\_WECHAT\_GROUP\_MARKDOWN\_FLAG |     bit    |      1     |  0  |   N  |  N  | b'0' | 成功的企业微信群通知转为Markdown格式开关 |
|  21 |   FAIL\_WECHAT\_GROUP\_MARKDOWN\_FLAG  |     bit    |      1     |  0  |   N  |  N  | b'0' | 失败的企业微信群通知转为Markdown格式开关 |

**表名：** T\_PIPELINE\_STAGE\_TAG

**说明：**

**数据列：**

|  序号 |        名称        |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |   说明   |
| :-: | :--------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :----: |
|  1  |        ID        |  varchar |  32 |  0  |   N  |  Y  |                    |   主键   |
|  2  | STAGE\_TAG\_NAME |  varchar |  45 |  0  |   N  |  N  |                    | 阶段标签名称 |
|  3  |      WEIGHT      |    int   |  10 |  0  |   N  |  N  |          0         | 阶段标签权值 |
|  4  |      CREATOR     |  varchar |  50 |  0  |   N  |  N  |       system       |   创建人  |
|  5  |     MODIFIER     |  varchar |  50 |  0  |   N  |  N  |       system       |  最近修改人 |
|  6  |   CREATE\_TIME   | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  创建时间  |
|  7  |   UPDATE\_TIME   | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  修改时间  |

**表名：** T\_PIPELINE\_TIMER

**说明：**

**数据列：**

|  序号 |      名称      |    数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |   说明  |
| :-: | :----------: | :-------: | :--: | :-: | :--: | :-: | :----------------: | :---: |
|  1  |  PROJECT\_ID |  varchar  |  32  |  0  |   N  |  Y  |                    |  项目ID |
|  2  | PIPELINE\_ID |  varchar  |  34  |  0  |   N  |  Y  |                    | 流水线ID |
|  3  |    CRONTAB   |  varchar  | 2048 |  0  |   N  |  N  |                    |  任务ID |
|  4  |    CREATOR   |  varchar  |  64  |  0  |   N  |  N  |                    |  创建者  |
|  5  | CREATE\_TIME | timestamp |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  创建时间 |
|  6  |    CHANNEL   |  varchar  |  32  |  0  |   N  |  N  |         BS         |  项目渠道 |

**表名：** T\_PIPELINE\_TRIGGER\_DETAIL

**说明：** 流水线触发事件明细表

**数据列：**

|  序号 |       名称       |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |          说明          |
| :-: | :------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :------------------: |
|  1  |   DETAIL\_ID   |   bigint  |   20  |  0  |   N  |  Y  |                    |        事件明细ID        |
|  2  |   PROJECT\_ID  |  varchar  |   64  |  0  |   N  |  N  |                    |         项目ID         |
|  3  |    EVENT\_ID   |   bigint  |   20  |  0  |   N  |  N  |                    |         事件ID         |
|  4  |     STATUS     |  varchar  |  100  |  0  |   Y  |  N  |                    | 状态(successorfailure) |
|  5  |  PIPELINE\_ID  |  varchar  |  100  |  0  |   Y  |  N  |                    |         流水线ID        |
|  6  | PIPELINE\_NAME |  varchar  |  255  |  0  |   Y  |  N  |                    |         流水线名称        |
|  7  |     VERSION    |    int    |   10  |  0  |   Y  |  N  |                    |        流水线版本号        |
|  8  |    BUILD\_ID   |  varchar  |  100  |  0  |   Y  |  N  |                    |         构建ID         |
|  9  |   BUILD\_NUM   |  varchar  |  100  |  0  |   Y  |  N  |                    |         构建编号         |
|  10 |     REASON     |  varchar  |  100  |  0  |   Y  |  N  |                    |         失败原因         |
|  11 | REASON\_DETAIL |    text   | 65535 |  0  |   Y  |  N  |                    |         原因详情         |
|  12 |  CREATE\_TIME  | timestamp |   19  |  0  |   N  |  Y  | CURRENT\_TIMESTAMP |         创建时间         |

**表名：** T\_PIPELINE\_TRIGGER\_EVENT

**说明：** 流水线触发事件表

**数据列：**

|  序号 |          名称         |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |           说明           |
| :-: | :-----------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :--------------------: |
|  1  |     REQUEST\_ID     |  varchar  |   64  |  0  |   N  |  N  |                    |          请求ID          |
|  2  |     PROJECT\_ID     |  varchar  |   64  |  0  |   N  |  N  |                    |          项目ID          |
|  3  |      EVENT\_ID      |   bigint  |   20  |  0  |   N  |  Y  |                    |          事件ID          |
|  4  |    TRIGGER\_TYPE    |  varchar  |   64  |  0  |   N  |  N  |                    |          触发类型          |
|  5  |    EVENT\_SOURCE    |  varchar  |  255  |  0  |   N  |  N  |                    | 触发源,代码库hashId/触发人/远程ip |
|  6  |     EVENT\_TYPE     |  varchar  |   64  |  0  |   N  |  N  |                    |          事件类型          |
|  7  |    TRIGGER\_USER    |  varchar  |  100  |  0  |   N  |  N  |                    |          触发用户          |
|  8  |     EVENT\_DESC     |    text   | 65535 |  0  |   N  |  N  |                    |          事件描述          |
|  9  | REPLAY\_REQUEST\_ID |  varchar  |   64  |  0  |   Y  |  N  |                    |         重放请求ID         |
|  10 |   REQUEST\_PARAMS   |    text   | 65535 |  0  |   Y  |  N  |                    |          请求参数          |
|  11 |     CREATE\_TIME    | timestamp |   19  |  0  |   N  |  Y  | CURRENT\_TIMESTAMP |          事件时间          |

**表名：** T\_PIPELINE\_TRIGGER\_REVIEW

**说明：** 流水线触发审核信息

**数据列：**

|  序号 |         名称        |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :---------------: | :------: | :---: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |     BUILD\_ID     |  varchar |   34  |  0  |   N  |  Y  |                    |   构建ID  |
|  2  |    PROJECT\_ID    |  varchar |   64  |  0  |   N  |  N  |                    |   项目ID  |
|  3  |    PIPELINE\_ID   |  varchar |   34  |  0  |   N  |  N  |                    |  流水线ID  |
|  4  | TRIGGER\_REVIEWER |   text   | 65535 |  0  |   N  |  N  |                    | 触发审核人列表 |
|  5  | TRIGGER\_OPERATOR |  varchar |   64  |  0  |   Y  |  N  |                    | 触发审核操作人 |
|  6  |    CREATE\_TIME   | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   创建时间  |
|  7  |    UPDATE\_TIME   | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   审核时间  |

**表名：** T\_PIPELINE\_VIEW

**说明：** 流水线视图

**数据列：**

|  序号 |             名称            |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |  默认值 |             说明            |
| :-: | :-----------------------: | :--------: | :------: | :-: | :--: | :-: | :--: | :-----------------------: |
|  1  |             ID            |   bigint   |    20    |  0  |   N  |  Y  |      |            主键ID           |
|  2  |        PROJECT\_ID        |   varchar  |    32    |  0  |   N  |  N  |      |            项目ID           |
|  3  |            NAME           |   varchar  |    64    |  0  |   N  |  N  |      |             名称            |
|  4  | FILTER\_BY\_PIPEINE\_NAME |   varchar  |    128   |  0  |   Y  |  N  |      | 流水线名称过滤器,已废弃,统一到filters管理 |
|  5  |    FILTER\_BY\_CREATOR    |   varchar  |    64    |  0  |   Y  |  N  |      |  创建者过滤器,已废弃,统一到filters管理  |
|  6  |        CREATE\_TIME       |  datetime  |    19    |  0  |   N  |  N  |      |            创建时间           |
|  7  |        UPDATE\_TIME       |  datetime  |    19    |  0  |   N  |  N  |      |            更新时间           |
|  8  |        CREATE\_USER       |   varchar  |    64    |  0  |   N  |  N  |      |            创建者            |
|  9  |        IS\_PROJECT        |     bit    |     1    |  0  |   Y  |  N  | b'0' |            是否项目           |
|  10 |           LOGIC           |   varchar  |    32    |  0  |   Y  |  N  |  AND |            逻辑符            |
|  11 |          FILTERS          | mediumtext | 16777215 |  0  |   Y  |  N  |      |            过滤器            |
|  12 |         VIEW\_TYPE        |     int    |    10    |  0  |   N  |  N  |   1  |     1:动态流水线组,2:静态流水线组     |

**表名：** T\_PIPELINE\_VIEW\_GROUP

**说明：** 流水线组关系表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |     |  项目ID  |
|  3  |   VIEW\_ID   |  bigint  |  20 |  0  |   N  |  N  |     | 流水线组ID |
|  4  | PIPELINE\_ID |  varchar |  34 |  0  |   N  |  N  |     |  流水线ID |
|  5  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间  |
|  6  |    CREATOR   |  varchar |  64 |  0  |   N  |  N  |     |   创建者  |

**表名：** T\_PIPELINE\_VIEW\_TOP

**说明：** 流水线组置顶表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |      ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |  PROJECT\_ID |  varchar |  64 |  0  |   N  |  N  |     |  项目ID  |
|  3  |   VIEW\_ID   |  bigint  |  20 |  0  |   N  |  N  |     | 流水线组ID |
|  4  |    CREATOR   |  varchar |  64 |  0  |   N  |  N  |     |   创建者  |
|  5  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间  |
|  6  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  |     |  更新时间  |

**表名：** T\_PIPELINE\_VIEW\_USER\_LAST\_VIEW

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--: |
|  1  |   USER\_ID   |  varchar |  32 |  0  |   N  |  Y  |                    | 用户ID |
|  2  |  PROJECT\_ID |  varchar |  32 |  0  |   N  |  Y  |                    | 项目ID |
|  3  |   VIEW\_ID   |  varchar |  64 |  0  |   N  |  N  |                    | 视图ID |
|  4  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |                    | 创建时间 |
|  5  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 更新时间 |

**表名：** T\_PIPELINE\_VIEW\_USER\_SETTINGS

**说明：**

**数据列：**

|  序号 |      名称      |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |         默认值        |   说明  |
| :-: | :----------: | :--------: | :------: | :-: | :--: | :-: | :----------------: | :---: |
|  1  |   USER\_ID   |   varchar  |    255   |  0  |   N  |  Y  |                    |  用户ID |
|  2  |  PROJECT\_ID |   varchar  |    32    |  0  |   N  |  Y  |                    |  项目ID |
|  3  |   SETTINGS   | mediumtext | 16777215 |  0  |   N  |  N  |                    | 属性配置表 |
|  4  | CREATE\_TIME |  datetime  |    19    |  0  |   N  |  N  |                    |  创建时间 |
|  5  | UPDATE\_TIME |  datetime  |    19    |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  更新时间 |

**表名：** T\_PIPELINE\_WEBHOOK

**说明：**

**数据列：**

|  序号 |          名称          |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 |  默认值 |      说明     |
| :-: | :------------------: | :-----: | :-: | :-: | :--: | :-: | :--: | :---------: |
|  1  |   REPOSITORY\_TYPE   | varchar |  64 |  0  |   N  |  N  |      | 新版的git插件的类型 |
|  2  |      PROJECT\_ID     | varchar |  32 |  0  |   N  |  N  |      |     项目ID    |
|  3  |     PIPELINE\_ID     | varchar |  34 |  0  |   N  |  N  |      |    流水线ID    |
|  4  |    REPO\_HASH\_ID    | varchar |  45 |  0  |   Y  |  N  |      |  存储库HASHID  |
|  5  |          ID          |  bigint |  20 |  0  |   N  |  Y  |      |     主键ID    |
|  6  |      REPO\_NAME      | varchar | 128 |  0  |   Y  |  N  |      |    代码库别名    |
|  7  |      REPO\_TYPE      | varchar |  32 |  0  |   Y  |  N  |      |    代码库类型    |
|  8  |     PROJECT\_NAME    | varchar | 128 |  0  |   Y  |  N  |      |     项目名称    |
|  9  |       TASK\_ID       | varchar |  34 |  0  |   Y  |  N  |      |     任务id    |
|  10 |        DELETE        |   bit   |  1  |  0  |   Y  |  N  | b'0' |     是否删除    |
|  11 |      EVENT\_TYPE     | varchar |  64 |  0  |   Y  |  N  |      |     事件类型    |
|  12 |     EXTERNAL\_ID     | varchar | 255 |  0  |   Y  |  N  |      |   代码库平台ID   |
|  13 | REPOSITORY\_HASH\_ID | varchar |  64 |  0  |   Y  |  N  |      |  代码库hashId  |
|  14 |    EXTERNAL\_NAME    | varchar | 255 |  0  |   Y  |  N  |      |   代码库平台仓库名  |

**表名：** T\_PIPELINE\_WEBHOOK\_BUILD\_PARAMETER

**说明：** webhook构建参数

**数据列：**

|  序号 |         名称        |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |  说明 |
| :-: | :---------------: | :------: | :---: | :-: | :--: | :-: | :----------------: | :-: |
|  1  |     BUILD\_ID     |  varchar |   34  |  0  |   N  |  Y  |                    |     |
|  2  |    PROJECT\_ID    |  varchar |   64  |  0  |   N  |  N  |                    |     |
|  3  |    PIPELINE\_ID   |  varchar |   34  |  0  |   N  |  N  |                    |     |
|  4  | BUILD\_PARAMETERS |   text   | 65535 |  0  |   Y  |  N  |                    |     |
|  5  |    CREATE\_TIME   | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |     |
|  6  |    UPDATE\_TIME   | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |     |

**表名：** T\_PIPELINE\_WEBHOOK\_QUEUE

**说明：**

**数据列：**

|  序号 |          名称         |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :-----------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |          ID         |  bigint  |  20 |  0  |   N  |  Y  |                    |   主键ID  |
|  2  |     PROJECT\_ID     |  varchar |  64 |  0  |   N  |  N  |                    |   项目ID  |
|  3  |     PIPELINE\_ID    |  varchar |  64 |  0  |   N  |  N  |                    |  流水线ID  |
|  4  | SOURCE\_PROJECT\_ID |  bigint  |  20 |  0  |   N  |  N  |                    |  源项目ID  |
|  5  |  SOURCE\_REPO\_NAME |  varchar | 255 |  0  |   N  |  N  |                    |  源代码库名称 |
|  6  |    SOURCE\_BRANCH   |  varchar | 255 |  0  |   N  |  N  |                    |   源分支   |
|  7  | TARGET\_PROJECT\_ID |  bigint  |  20 |  0  |   Y  |  N  |                    |  目标项目ID |
|  8  |  TARGET\_REPO\_NAME |  varchar | 255 |  0  |   Y  |  N  |                    | 目标代码库名称 |
|  9  |    TARGET\_BRANCH   |  varchar | 255 |  0  |   Y  |  N  |                    |   目标分支  |
|  10 |      BUILD\_ID      |  varchar |  34 |  0  |   N  |  N  |                    |   构建ID  |
|  11 |     CREATE\_TIME    | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   创建时间  |

**表名：** T\_PIPELINE\_WEBHOOK\_REVISION

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明 |
| :-: | :-----------: | :------: | :-: | :-: | :--: | :-: | :-: | :-: |
|  1  |       ID      |  bigint  |  20 |  0  |   N  |  Y  |     |     |
|  2  | PROJECT\_NAME |  varchar | 255 |  0  |   Y  |  N  |     |     |
|  3  |    REVISION   |  varchar |  64 |  0  |   Y  |  N  |     |     |
|  4  |  CREATE\_TIME | datetime |  19 |  0  |   Y  |  N  |     |     |
|  5  |  UPDATE\_TIME | datetime |  19 |  0  |   Y  |  N  |     |     |

**表名：** T\_PROJECT\_PIPELINE\_CALLBACK

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |  默认值 |                        说明                       |
| :-: | :-----------: | :------: | :---: | :-: | :--: | :-: | :--: | :---------------------------------------------: |
|  1  |       ID      |  bigint  |   20  |  0  |   N  |  Y  |      |                       主键ID                      |
|  2  |  PROJECT\_ID  |  varchar |   64  |  0  |   N  |  N  |      |                       项目ID                      |
|  3  |     EVENTS    |  varchar |  255  |  0  |   Y  |  N  |      |                        事件                       |
|  4  | CALLBACK\_URL |  varchar |  255  |  0  |   N  |  N  |      |                     回调url地址                     |
|  5  |    CREATOR    |  varchar |   64  |  0  |   N  |  N  |      |                       创建者                       |
|  6  |    UPDATOR    |  varchar |   64  |  0  |   N  |  N  |      |                       更新人                       |
|  7  | CREATED\_TIME | datetime |   19  |  0  |   N  |  N  |      |                       创建时间                      |
|  8  | UPDATED\_TIME | datetime |   19  |  0  |   N  |  N  |      |                       更新时间                      |
|  9  | SECRET\_TOKEN |   text   | 65535 |  0  |   Y  |  N  |      | Sendtoyourwithhttpheader:X-DEVOPS-WEBHOOK-TOKEN |
|  10 |     ENABLE    |    bit   |   1   |  0  |   N  |  N  | b'1' |                        启用                       |

**表名：** T\_PROJECT\_PIPELINE\_CALLBACK\_HISTORY

**说明：**

**数据列：**

|  序号 |        名称       |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |    说明   |
| :-: | :-------------: | :------: | :---: | :-: | :--: | :-: | :-: | :-----: |
|  1  |        ID       |  bigint  |   20  |  0  |   N  |  Y  |     |   主键ID  |
|  2  |   PROJECT\_ID   |  varchar |   64  |  0  |   N  |  N  |     |   项目ID  |
|  3  |      EVENTS     |  varchar |  255  |  0  |   Y  |  N  |     |    事件   |
|  4  |  CALLBACK\_URL  |  varchar |  255  |  0  |   N  |  N  |     | 回调url地址 |
|  5  |      STATUS     |  varchar |   20  |  0  |   N  |  N  |     |    状态   |
|  6  |    ERROR\_MSG   |   text   | 65535 |  0  |   Y  |  N  |     |   错误描述  |
|  7  | REQUEST\_HEADER |   text   | 65535 |  0  |   Y  |  N  |     |   请求头   |
|  8  |  REQUEST\_BODY  |   text   | 65535 |  0  |   N  |  N  |     |  请求body |
|  9  |  RESPONSE\_CODE |    int   |   10  |  0  |   Y  |  N  |     |  响应code |
|  10 |  RESPONSE\_BODY |   text   | 65535 |  0  |   Y  |  N  |     |  响应body |
|  11 |   START\_TIME   | datetime |   19  |  0  |   N  |  N  |     |   开始时间  |
|  12 |    END\_TIME    | datetime |   19  |  0  |   N  |  N  |     |   结束时间  |
|  13 |  CREATED\_TIME  | datetime |   19  |  0  |   N  |  Y  |     |   创建时间  |

**表名：** T\_REPORT

**说明：** 流水线产物表

**数据列：**

|  序号 |      名称      |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |    默认值   |    说明   |
| :-: | :----------: | :--------: | :------: | :-: | :--: | :-: | :------: | :-----: |
|  1  |      ID      |   bigint   |    20    |  0  |   N  |  Y  |          |   主键ID  |
|  2  |  PROJECT\_ID |   varchar  |    32    |  0  |   N  |  N  |          |   项目ID  |
|  3  | PIPELINE\_ID |   varchar  |    34    |  0  |   N  |  N  |          |  流水线ID  |
|  4  |   BUILD\_ID  |   varchar  |    34    |  0  |   N  |  N  |          |   构建ID  |
|  5  |  ELEMENT\_ID |   varchar  |    34    |  0  |   N  |  N  |          |   原子ID  |
|  6  |     TYPE     |   varchar  |    32    |  0  |   N  |  N  | INTERNAL |    类型   |
|  7  |  INDEX\_FILE | mediumtext | 16777215 |  0  |   N  |  N  |          |   入口文件  |
|  8  |     NAME     |    text    |   65535  |  0  |   N  |  N  |          |    名称   |
|  9  | CREATE\_TIME |  datetime  |    19    |  0  |   N  |  N  |          |   创建时间  |
|  10 | UPDATE\_TIME |  datetime  |    19    |  0  |   N  |  N  |          |   更新时间  |
|  11 |  TASK\_NAME  |   varchar  |    128   |  0  |   N  |  N  |          |   任务名称  |
|  12 |  ATOM\_CODE  |   varchar  |    128   |  0  |   N  |  N  |          | 插件的唯一标识 |

**表名：** T\_TEMPLATE

**说明：** 流水线模板信息表

**数据列：**

|  序号 |         名称        |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |    默认值    |      说明     |
| :-: | :---------------: | :--------: | :------: | :-: | :--: | :-: | :-------: | :---------: |
|  1  |      VERSION      |   bigint   |    20    |  0  |   N  |  Y  |           |     主键ID    |
|  2  |         ID        |   varchar  |    32    |  0  |   N  |  N  |           |     主键ID    |
|  3  |   TEMPLATE\_NAME  |   varchar  |    64    |  0  |   N  |  N  |           |     模板名称    |
|  4  |    PROJECT\_ID    |   varchar  |    34    |  0  |   N  |  N  |           |     项目ID    |
|  5  |   VERSION\_NAME   |   varchar  |    64    |  0  |   N  |  N  |           |     版本名称    |
|  6  |      CREATOR      |   varchar  |    64    |  0  |   N  |  N  |           |     创建者     |
|  7  |   CREATED\_TIME   |  datetime  |    23    |  0  |   Y  |  N  |           |     创建时间    |
|  8  |    UPDATE\_TIME   |  datetime  |    23    |  0  |   Y  |  N  |           |     更新时间    |
|  9  |      TEMPLATE     | mediumtext | 16777215 |  0  |   Y  |  N  |           |      模板     |
|  10 |        TYPE       |   varchar  |    32    |  0  |   N  |  N  | CUSTOMIZE |      类型     |
|  11 |      CATEGORY     |   varchar  |    128   |  0  |   Y  |  N  |           |     应用范畴    |
|  12 |     LOGO\_URL     |   varchar  |    512   |  0  |   Y  |  N  |           |  LOGOURL地址  |
|  13 | SRC\_TEMPLATE\_ID |   varchar  |    32    |  0  |   Y  |  N  |           |    源模版ID    |
|  14 |    STORE\_FLAG    |     bit    |     1    |  0  |   Y  |  N  |    b'0'   | 是否已关联到store |
|  15 |       WEIGHT      |     int    |    10    |  0  |   Y  |  N  |     0     |      权值     |

**表名：** T\_TEMPLATE\_INSTANCE\_BASE

**说明：** 模板实列化基本信息表

**数据列：**

|  序号 |               名称              |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |    说明    |
| :-: | :---------------------------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :------: |
|  1  |               ID              |  varchar |  32 |  0  |   N  |  Y  |                       |   主键ID   |
|  2  |          TEMPLATE\_ID         |  varchar |  32 |  0  |   Y  |  N  |                       |   模板ID   |
|  3  |       TEMPLATE\_VERSION       |  varchar |  32 |  0  |   N  |  N  |                       |   模板版本   |
|  4  | USE\_TEMPLATE\_SETTINGS\_FLAG |    bit   |  1  |  0  |   N  |  N  |                       | 是否使用模板配置 |
|  5  |          PROJECT\_ID          |  varchar |  64 |  0  |   N  |  N  |                       |   项目ID   |
|  6  |        TOTAL\_ITEM\_NUM       |    int   |  10 |  0  |   N  |  N  |           0           |  总实例化数量  |
|  7  |       SUCCESS\_ITEM\_NUM      |    int   |  10 |  0  |   N  |  N  |           0           |  实例化成功数量 |
|  8  |        FAIL\_ITEM\_NUM        |    int   |  10 |  0  |   N  |  N  |           0           |  实例化失败数量 |
|  9  |             STATUS            |  varchar |  32 |  0  |   N  |  N  |                       |    状态    |
|  10 |            CREATOR            |  varchar |  50 |  0  |   N  |  N  |         system        |    创建者   |
|  11 |            MODIFIER           |  varchar |  50 |  0  |   N  |  N  |         system        |    修改者   |
|  12 |          UPDATE\_TIME         | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   修改时间   |
|  13 |          CREATE\_TIME         | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   创建时间   |

**表名：** T\_TEMPLATE\_INSTANCE\_ITEM

**说明：** 模板实列化项信息表

**数据列：**

|  序号 |        名称       |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |          默认值          |     说明    |
| :-: | :-------------: | :--------: | :------: | :-: | :--: | :-: | :-------------------: | :-------: |
|  1  |        ID       |   varchar  |    32    |  0  |   N  |  Y  |                       |    主键ID   |
|  2  |   PROJECT\_ID   |   varchar  |    64    |  0  |   N  |  N  |                       |    项目ID   |
|  3  |   PIPELINE\_ID  |   varchar  |    34    |  0  |   N  |  N  |                       |   流水线ID   |
|  4  |  PIPELINE\_NAME |   varchar  |    255   |  0  |   N  |  N  |                       |   流水线名称   |
|  5  | BUILD\_NO\_INFO |   varchar  |    512   |  0  |   Y  |  N  |                       |   构建号信息   |
|  6  |      STATUS     |   varchar  |    32    |  0  |   N  |  N  |                       |     状态    |
|  7  |     BASE\_ID    |   varchar  |    32    |  0  |   N  |  N  |                       | 实列化基本信息ID |
|  8  |      PARAM      | mediumtext | 16777215 |  0  |   Y  |  N  |                       |     参数    |
|  9  |     CREATOR     |   varchar  |    50    |  0  |   N  |  N  |         system        |    创建者    |
|  10 |     MODIFIER    |   varchar  |    50    |  0  |   N  |  N  |         system        |    修改者    |
|  11 |   UPDATE\_TIME  |  datetime  |    23    |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    修改时间   |
|  12 |   CREATE\_TIME  |  datetime  |    23    |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |    创建时间   |

**表名：** T\_TEMPLATE\_PIPELINE

**说明：** 流水线模板-实例映射表

**数据列：**

|  序号 |         名称         |    数据类型    |    长度    | 小数位 | 允许空值 |  主键 |     默认值    |                说明               |
| :-: | :----------------: | :--------: | :------: | :-: | :--: | :-: | :--------: | :-----------------------------: |
|  1  |     PROJECT\_ID    |   varchar  |    64    |  0  |   N  |  N  |            |               项目ID              |
|  2  |    PIPELINE\_ID    |   varchar  |    34    |  0  |   N  |  Y  |            |              流水线ID              |
|  3  |   INSTANCE\_TYPE   |   varchar  |    32    |  0  |   N  |  N  | CONSTRAINT | 实例化类型：FREEDOM自由模式CONSTRAINT约束模式 |
|  4  | ROOT\_TEMPLATE\_ID |   varchar  |    32    |  0  |   Y  |  N  |            |              源模板ID              |
|  5  |       VERSION      |   bigint   |    20    |  0  |   N  |  N  |            |               版本号               |
|  6  |    VERSION\_NAME   |   varchar  |    64    |  0  |   N  |  N  |            |               版本名称              |
|  7  |    TEMPLATE\_ID    |   varchar  |    32    |  0  |   N  |  N  |            |               模板ID              |
|  8  |       CREATOR      |   varchar  |    64    |  0  |   N  |  N  |            |               创建者               |
|  9  |       UPDATOR      |   varchar  |    64    |  0  |   N  |  N  |            |               更新人               |
|  10 |    CREATED\_TIME   |  datetime  |    19    |  0  |   N  |  N  |            |               创建时间              |
|  11 |    UPDATED\_TIME   |  datetime  |    19    |  0  |   N  |  N  |            |               更新时间              |
|  12 |      BUILD\_NO     |    text    |   65535  |  0  |   Y  |  N  |            |               构建号               |
|  13 |        PARAM       | mediumtext | 16777215 |  0  |   Y  |  N  |            |                参数               |
|  14 |       DELETED      |     bit    |     1    |  0  |   Y  |  N  |    b'0'    |             流水线已被软删除            |
