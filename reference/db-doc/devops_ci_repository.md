# devops\_ci\_repository

**数据库名：** devops\_ci\_repository

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_repository的数据库文档

|                                              表名                                              |         说明        |
| :------------------------------------------------------------------------------------------: | :---------------: |
|                   [T\_REPOSITORY](devops\_ci\_repository.md#T\_REPOSITORY)                   |        代码库表       |
|        [T\_REPOSITORY\_CODE\_GIT](devops\_ci\_repository.md#T\_REPOSITORY\_CODE\_GIT)        |      工蜂代码库明细表     |
|     [T\_REPOSITORY\_CODE\_GITLAB](devops\_ci\_repository.md#T\_REPOSITORY\_CODE\_GITLAB)     |    gitlab代码库明细表   |
|         [T\_REPOSITORY\_CODE\_P4](devops\_ci\_repository.md#T\_REPOSITORY\_CODE\_P4)         |                   |
|        [T\_REPOSITORY\_CODE\_SVN](devops\_ci\_repository.md#T\_REPOSITORY\_CODE\_SVN)        |     svn代码库明细表     |
|           [T\_REPOSITORY\_COMMIT](devops\_ci\_repository.md#T\_REPOSITORY\_COMMIT)           |      代码库变更记录      |
|           [T\_REPOSITORY\_GITHUB](devops\_ci\_repository.md#T\_REPOSITORY\_GITHUB)           |    github代码库明细表   |
|    [T\_REPOSITORY\_GITHUB\_TOKEN](devops\_ci\_repository.md#T\_REPOSITORY\_GITHUB\_TOKEN)    | githuboauthtoken表 |
|       [T\_REPOSITORY\_GIT\_CHECK](devops\_ci\_repository.md#T\_REPOSITORY\_GIT\_CHECK)       |   工蜂oauthtoken表   |
|       [T\_REPOSITORY\_GIT\_TOKEN](devops\_ci\_repository.md#T\_REPOSITORY\_GIT\_TOKEN)       |  工蜂commitchecker表 |
|    [T\_REPOSITORY\_PIPELINE\_REF](devops\_ci\_repository.md#T\_REPOSITORY\_PIPELINE\_REF)    |     流水线引用代码库表     |
|      [T\_REPOSITORY\_TGIT\_TOKEN](devops\_ci\_repository.md#T\_REPOSITORY\_TGIT\_TOKEN)      |  外网工蜂OAUTHtoken表  |
| [T\_REPOSITORY\_WEBHOOK\_REQUEST](devops\_ci\_repository.md#T\_REPOSITORY\_WEBHOOK\_REQUEST) |   代码库WEBHOOK请求表   |

**表名：** T\_REPOSITORY

**说明：** 代码库表

**数据列：**

|  序号 |          名称          |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |     说明     |
| :-: | :------------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :--------: |
|  1  |    REPOSITORY\_ID    |   bigint  |  20 |  0  |   N  |  Y  |                    |    主键ID    |
|  2  |      PROJECT\_ID     |  varchar  |  32 |  0  |   N  |  N  |                    |    项目ID    |
|  3  |       USER\_ID       |  varchar  |  64 |  0  |   N  |  N  |                    |    用户ID    |
|  4  |      ALIAS\_NAME     |  varchar  | 255 |  0  |   N  |  N  |                    |     别名     |
|  5  |          URL         |  varchar  | 255 |  0  |   N  |  N  |                    |    url地址   |
|  6  |         TYPE         |  varchar  |  20 |  0  |   N  |  N  |                    |     类型     |
|  7  | REPOSITORY\_HASH\_ID |  varchar  |  64 |  0  |   Y  |  N  |                    |    哈希ID    |
|  8  |     CREATED\_TIME    | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |    创建时间    |
|  9  |     UPDATED\_TIME    | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |    修改时间    |
|  10 |      IS\_DELETED     |    bit    |  1  |  0  |   N  |  N  |                    | 是否删除0可用1删除 |
|  11 |     UPDATED\_USER    |  varchar  |  64 |  0  |   Y  |  N  |                    |  代码库最近修改人  |

**表名：** T\_REPOSITORY\_CODE\_GIT

**说明：** 工蜂代码库明细表

**数据列：**

|  序号 |        名称        |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :--------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |  REPOSITORY\_ID  |   bigint  |  20 |  0  |   N  |  Y  |                    |   仓库ID  |
|  2  |   PROJECT\_NAME  |  varchar  | 255 |  0  |   N  |  N  |                    |   项目名称  |
|  3  |    USER\_NAME    |  varchar  |  64 |  0  |   N  |  N  |                    |   用户名称  |
|  4  |   CREATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |   创建时间  |
|  5  |   UPDATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |   修改时间  |
|  6  |  CREDENTIAL\_ID  |  varchar  |  64 |  0  |   N  |  N  |                    |   凭据ID  |
|  7  |    AUTH\_TYPE    |  varchar  |  8  |  0  |   Y  |  N  |                    |   认证方式  |
|  8  | GIT\_PROJECT\_ID |   bigint  |  20 |  0  |   Y  |  N  |          0         | GIT项目ID |

**表名：** T\_REPOSITORY\_CODE\_GITLAB

**说明：** gitlab代码库明细表

**数据列：**

|  序号 |        名称        |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :--------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |  REPOSITORY\_ID  |   bigint  |  20 |  0  |   N  |  Y  |                    |   仓库ID  |
|  2  |   PROJECT\_NAME  |  varchar  | 255 |  0  |   N  |  N  |                    |   项目名称  |
|  3  |  CREDENTIAL\_ID  |  varchar  |  64 |  0  |   N  |  N  |                    |   凭据ID  |
|  4  |   CREATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |   创建时间  |
|  5  |   UPDATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 |   修改时间  |
|  6  |    USER\_NAME    |  varchar  |  64 |  0  |   N  |  N  |                    |   用户名称  |
|  7  |    AUTH\_TYPE    |  varchar  |  8  |  0  |   Y  |  N  |                    |   凭证类型  |
|  8  | GIT\_PROJECT\_ID |   bigint  |  20 |  0  |   Y  |  N  |          0         | GIT项目ID |

**表名：** T\_REPOSITORY\_CODE\_P4

**说明：**

**数据列：**

|  序号 |       名称       |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |  说明 |
| :-: | :------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-: |
|  1  | REPOSITORY\_ID |   bigint  |  20 |  0  |   N  |  Y  |                    |     |
|  2  |  PROJECT\_NAME |  varchar  | 255 |  0  |   N  |  N  |                    |     |
|  3  |   USER\_NAME   |  varchar  |  64 |  0  |   N  |  N  |                    |     |
|  4  | CREDENTIAL\_ID |  varchar  |  64 |  0  |   N  |  N  |                    |     |
|  5  |  CREATED\_TIME | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |     |
|  6  |  UPDATED\_TIME | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |     |

**表名：** T\_REPOSITORY\_CODE\_SVN

**说明：** svn代码库明细表

**数据列：**

|  序号 |       名称       |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |  说明  |
| :-: | :------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :--: |
|  1  | REPOSITORY\_ID |   bigint  |  20 |  0  |   N  |  Y  |                    | 仓库ID |
|  2  |     REGION     |  varchar  | 255 |  0  |   N  |  N  |                    |  地区  |
|  3  |  PROJECT\_NAME |  varchar  | 255 |  0  |   N  |  N  |                    | 项目名称 |
|  4  |   USER\_NAME   |  varchar  |  64 |  0  |   N  |  N  |                    | 用户名称 |
|  5  |  CREATED\_TIME | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 | 创建时间 |
|  6  |  UPDATED\_TIME | timestamp |  19 |  0  |   N  |  N  | 2019-08-0100:00:00 | 修改时间 |
|  7  | CREDENTIAL\_ID |  varchar  |  64 |  0  |   N  |  N  |                    | 凭据ID |
|  8  |    SVN\_TYPE   |  varchar  |  32 |  0  |   Y  |  N  |                    | 仓库类型 |

**表名：** T\_REPOSITORY\_COMMIT

**说明：** 代码库变更记录

**数据列：**

|  序号 |      名称      |   数据类型   |     长度     | 小数位 | 允许空值 |  主键 | 默认值 |          说明          |
| :-: | :----------: | :------: | :--------: | :-: | :--: | :-: | :-: | :------------------: |
|  1  |      ID      |  bigint  |     20     |  0  |   N  |  Y  |     |         主键ID         |
|  2  |   BUILD\_ID  |  varchar |     34     |  0  |   Y  |  N  |     |         构建ID         |
|  3  | PIPELINE\_ID |  varchar |     34     |  0  |   Y  |  N  |     |         流水线ID        |
|  4  |   REPO\_ID   |  bigint  |     20     |  0  |   Y  |  N  |     |         代码库ID        |
|  5  |     TYPE     | smallint |      6     |  0  |   Y  |  N  |     | 1-svn,2-git,3-gitlab |
|  6  |    COMMIT    |  varchar |     64     |  0  |   Y  |  N  |     |          提交          |
|  7  |   COMMITTER  |  varchar |     32     |  0  |   Y  |  N  |     |          提交者         |
|  8  | COMMIT\_TIME | datetime |     19     |  0  |   Y  |  N  |     |         提交时间         |
|  9  |    COMMENT   | longtext | 2147483647 |  0  |   Y  |  N  |     |          评论          |
|  10 |  ELEMENT\_ID |  varchar |     34     |  0  |   Y  |  N  |     |         原子ID         |
|  11 |  REPO\_NAME  |  varchar |     128    |  0  |   Y  |  N  |     |         代码库别名        |
|  12 |      URL     |  varchar |     255    |  0  |   Y  |  N  |     |        代码库URL        |

**表名：** T\_REPOSITORY\_GITHUB

**说明：** github代码库明细表

**数据列：**

|  序号 |        名称        |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :--------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |  REPOSITORY\_ID  |   bigint  |  20 |  0  |   N  |  Y  |                    |   仓库ID  |
|  2  |  CREDENTIAL\_ID  |  varchar  | 128 |  0  |   Y  |  N  |                    |   凭据ID  |
|  3  |   PROJECT\_NAME  |  varchar  | 255 |  0  |   N  |  N  |                    |   项目名称  |
|  4  |    USER\_NAME    |  varchar  |  64 |  0  |   N  |  N  |                    |   用户名称  |
|  5  |   CREATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   创建时间  |
|  6  |   UPDATED\_TIME  | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   修改时间  |
|  7  | GIT\_PROJECT\_ID |   bigint  |  20 |  0  |   Y  |  N  |          0         | GIT项目ID |

**表名：** T\_REPOSITORY\_GITHUB\_TOKEN

**说明：** githuboauthtoken表

**数据列：**

|  序号 |       名称      |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |                   说明                  |
| :-: | :-----------: | :------: | :---: | :-: | :--: | :-: | :----------------: | :-----------------------------------: |
|  1  |       ID      |  bigint  |   20  |  0  |   N  |  Y  |                    |                  主键ID                 |
|  2  |    USER\_ID   |  varchar |   64  |  0  |   N  |  N  |                    |                  用户ID                 |
|  3  | ACCESS\_TOKEN |  varchar |   96  |  0  |   N  |  N  |                    |                权限Token                |
|  4  |  TOKEN\_TYPE  |  varchar |   64  |  0  |   N  |  N  |                    |                token类型                |
|  5  |     SCOPE     |   text   | 65535 |  0  |   N  |  N  |                    |                  生效范围                 |
|  6  |  CREATE\_TIME | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |                  创建时间                 |
|  7  |  UPDATE\_TIME | datetime |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |                  更新时间                 |
|  8  |      TYPE     |  varchar |   32  |  0  |   Y  |  N  |     GITHUB\_APP    | GitHubtoken类型（GITHUB\_APP、OAUTH\_APP） |

**表名：** T\_REPOSITORY\_GIT\_CHECK

**说明：** 工蜂oauthtoken表

**数据列：**

|  序号 |       名称       |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |   说明   |
| :-: | :------------: | :------: | :--: | :-: | :--: | :-: | :----------------: | :----: |
|  1  |       ID       |  bigint  |  20  |  0  |   N  |  Y  |                    |  主键ID  |
|  2  |  PIPELINE\_ID  |  varchar |  64  |  0  |   N  |  N  |                    |  流水线ID |
|  3  |  BUILD\_NUMBER |    int   |  10  |  0  |   N  |  N  |                    |  构建编号  |
|  4  |    REPO\_ID    |  varchar |  64  |  0  |   Y  |  N  |                    |  代码库ID |
|  5  |   COMMIT\_ID   |  varchar |  64  |  0  |   N  |  N  |                    | 代码提交ID |
|  6  |  CREATE\_TIME  | datetime |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  创建时间  |
|  7  |  UPDATE\_TIME  | datetime |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |  更新时间  |
|  8  |   REPO\_NAME   |  varchar |  128 |  0  |   Y  |  N  |                    |  代码库别名 |
|  9  |     CONTEXT    |  varchar |  255 |  0  |   Y  |  N  |                    |   内容   |
|  10 |     SOURCE     |  varchar |  64  |  0  |   N  |  N  |                    |  事件来源  |
|  11 | TARGET\_BRANCH |  varchar | 1024 |  0  |   N  |  N  |                    |  目标分支  |

**表名：** T\_REPOSITORY\_GIT\_TOKEN

**说明：** 工蜂commitchecker表

**数据列：**

|  序号 |       名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |     说明     |
| :-: | :------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--------: |
|  1  |       ID       |  bigint  |  20 |  0  |   N  |  Y  |                    |    主键ID    |
|  2  |    USER\_ID    |  varchar |  64 |  0  |   Y  |  N  |                    |    用户ID    |
|  3  |  ACCESS\_TOKEN |  varchar |  96 |  0  |   Y  |  N  |                    |   权限Token  |
|  4  | REFRESH\_TOKEN |  varchar |  96 |  0  |   Y  |  N  |                    |   刷新token  |
|  5  |   TOKEN\_TYPE  |  varchar |  64 |  0  |   Y  |  N  |                    |   token类型  |
|  6  |   EXPIRES\_IN  |  bigint  |  20 |  0  |   Y  |  N  |                    |    过期时间    |
|  7  |  CREATE\_TIME  | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP | token的创建时间 |

**表名：** T\_REPOSITORY\_PIPELINE\_REF

**说明：** 流水线引用代码库表

**数据列：**

|  序号 |            名称           |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |       说明      |
| :-: | :---------------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :-----------: |
|  1  |            ID           |   bigint  |   20  |  0  |   N  |  Y  |                    |               |
|  2  |       PROJECT\_ID       |  varchar  |   64  |  0  |   N  |  N  |                    |     蓝盾项目ID    |
|  3  |       PIPELINE\_ID      |  varchar  |   64  |  0  |   N  |  N  |                    |     流水线ID     |
|  4  |      PIPELINE\_NAME     |  varchar  |  255  |  0  |   N  |  N  |                    |     流水线名称     |
|  5  |      REPOSITORY\_ID     |   bigint  |   20  |  0  |   N  |  N  |                    |     代码库ID     |
|  6  |         TASK\_ID        |  varchar  |   64  |  0  |   N  |  N  |                    |      任务ID     |
|  7  |        TASK\_NAME       |  varchar  |  128  |  0  |   Y  |  N  |                    |  原子名称，用户是可以修改 |
|  8  |        ATOM\_CODE       |  varchar  |   32  |  0  |   N  |  N  |                    |    插件的唯一标识    |
|  9  |      ATOM\_CATEGORY     |  varchar  |   10  |  0  |   N  |  N  |                    |      插件类别     |
|  10 |       TASK\_PARAMS      |    text   | 65535 |  0  |   N  |  N  |                    |      插件参数     |
|  11 |     TASK\_REPO\_TYPE    |  varchar  |   10  |  0  |   N  |  N  |                    |   插件代码库类型配置   |
|  12 |   TASK\_REPO\_HASH\_ID  |  varchar  |   64  |  0  |   Y  |  N  |                    | 插件代码库hashId配置 |
|  13 |     TASK\_REPO\_NAME    |  varchar  |  255  |  0  |   Y  |  N  |                    |   插件代码库别名配置   |
|  14 |      TRIGGER\_TYPE      |  varchar  |   64  |  0  |   Y  |  N  |                    |      触发类型     |
|  15 |       EVENT\_TYPE       |  varchar  |   64  |  0  |   Y  |  N  |                    |      事件类型     |
|  16 |    TRIGGER\_CONDITION   |    text   | 65535 |  0  |   Y  |  N  |                    |      触发条件     |
|  17 | TRIGGER\_CONDITION\_MD5 |  varchar  |   64  |  0  |   Y  |  N  |                    |    触发条件md5    |
|  18 |       CREATE\_TIME      | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      创建时间     |
|  19 |       UPDATE\_TIME      | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      更新时间     |

**表名：** T\_REPOSITORY\_TGIT\_TOKEN

**说明：** 外网工蜂OAUTHtoken表

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |     说明     |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--------: |
|  1  |        ID       |  bigint  |  20 |  0  |   N  |  Y  |                    |    主键ID    |
|  2  |     USER\_ID    |  varchar |  64 |  0  |   Y  |  N  |                    |    用户ID    |
|  3  |  ACCESS\_TOKEN  |  varchar |  96 |  0  |   Y  |  N  |                    |   权限Token  |
|  4  |  REFRESH\_TOKEN |  varchar |  96 |  0  |   Y  |  N  |                    |   刷新token  |
|  5  |   TOKEN\_TYPE   |  varchar |  64 |  0  |   Y  |  N  |                    |   token类型  |
|  6  |   EXPIRES\_IN   |  bigint  |  20 |  0  |   Y  |  N  |                    |    过期时间    |
|  7  |   CREATE\_TIME  | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP | token的创建时间 |
|  8  | OAUTH\_USER\_ID |  varchar |  64 |  0  |   N  |  N  |                    |   账户实际名称   |

**表名：** T\_REPOSITORY\_WEBHOOK\_REQUEST

**说明：** 代码库WEBHOOK请求表

**数据列：**

|  序号 |        名称        |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :--------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |    REQUEST\_ID   |  varchar  |   64  |  0  |   N  |  Y  |                    |   请求ID  |
|  2  |   EXTERNAL\_ID   |  varchar  |  255  |  0  |   Y  |  N  |                    | 代码库平台ID |
|  3  | REPOSITORY\_TYPE |  varchar  |   32  |  0  |   Y  |  N  |                    |   触发类型  |
|  4  |    EVENT\_TYPE   |  varchar  |  255  |  0  |   Y  |  N  |                    |   事件类型  |
|  5  |   TRIGGER\_USER  |  varchar  |  100  |  0  |   N  |  N  |                    |   触发用户  |
|  6  |  EVENT\_MESSAGE  |    text   | 65535 |  0  |   N  |  N  |                    |   事件信息  |
|  7  |  REQUEST\_HEADER |    text   | 65535 |  0  |   Y  |  N  |                    |  事件请求头  |
|  8  |  REQUEST\_PARAM  |    text   | 65535 |  0  |   Y  |  N  |                    |  事件请求参数 |
|  9  |   REQUEST\_BODY  |    text   | 65535 |  0  |   Y  |  N  |                    |  事件请求体  |
|  10 |   CREATE\_TIME   | timestamp |   19  |  0  |   N  |  Y  | CURRENT\_TIMESTAMP |   创建时间  |
