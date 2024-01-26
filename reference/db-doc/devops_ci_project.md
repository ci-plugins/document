# devops\_ci\_project

**数据库名：** devops\_ci\_project

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_project的数据库文档

|                                                     表名                                                    |     说明     |
| :-------------------------------------------------------------------------------------------------------: | :--------: |
|                             [T\_ACTIVITY](devops\_ci\_project.md#T\_ACTIVITY)                             |            |
|                         [T\_DATA\_SOURCE](devops\_ci\_project.md#T\_DATA\_SOURCE)                         |   模块数据源配置  |
|                             [T\_FAVORITE](devops\_ci\_project.md#T\_FAVORITE)                             |    关注收藏表   |
|                           [T\_GRAY\_TEST](devops\_ci\_project.md#T\_GRAY\_TEST)                           |            |
|                        [T\_I18N\_MESSAGE](devops\_ci\_project.md#T\_I18N\_MESSAGE)                        |   国际化信息表   |
|                          [T\_LEAF\_ALLOC](devops\_ci\_project.md#T\_LEAF\_ALLOC)                          |   ID管理数据表  |
|                [T\_MESSAGE\_CODE\_DETAIL](devops\_ci\_project.md#T\_MESSAGE\_CODE\_DETAIL)                |  code码详情表  |
|                               [T\_NOTICE](devops\_ci\_project.md#T\_NOTICE)                               |            |
|                              [T\_PROJECT](devops\_ci\_project.md#T\_PROJECT)                              |    项目信息表   |
|                    [T\_PROJECT\_APPROVAL](devops\_ci\_project.md#T\_PROJECT\_APPROVAL)                    |    项目审批表   |
|      [T\_PROJECT\_DATA\_MIGRATE\_HISTORY](devops\_ci\_project.md#T\_PROJECT\_DATA\_MIGRATE\_HISTORY)      |  项目数据迁移历史表 |
|                       [T\_PROJECT\_LABEL](devops\_ci\_project.md#T\_PROJECT\_LABEL)                       |            |
|                  [T\_PROJECT\_LABEL\_REL](devops\_ci\_project.md#T\_PROJECT\_LABEL\_REL)                  |            |
|                              [T\_SERVICE](devops\_ci\_project.md#T\_SERVICE)                              |    服务信息表   |
|                        [T\_SERVICE\_TYPE](devops\_ci\_project.md#T\_SERVICE\_TYPE)                        |    服务类型表   |
|              [T\_SHARDING\_ROUTING\_RULE](devops\_ci\_project.md#T\_SHARDING\_ROUTING\_RULE)              |  DB分片路由规则  |
|              [T\_TABLE\_SHARDING\_CONFIG](devops\_ci\_project.md#T\_TABLE\_SHARDING\_CONFIG)              |  数据库表分片配置  |
|                                 [T\_USER](devops\_ci\_project.md#T\_USER)                                 |     用户表    |
| [T\_USER\_DAILY\_FIRST\_AND\_LAST\_LOGIN](devops\_ci\_project.md#T\_USER\_DAILY\_FIRST\_AND\_LAST\_LOGIN) |            |
|                   [T\_USER\_DAILY\_LOGIN](devops\_ci\_project.md#T\_USER\_DAILY\_LOGIN)                   |            |
|                         [T\_USER\_LOCALE](devops\_ci\_project.md#T\_USER\_LOCALE)                         | 用户设置的国际化信息 |

**表名：** T\_ACTIVITY

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :-----------: | :------: | :--: | :-: | :--: | :-: | :-: | :--: |
|  1  |       ID      |  bigint  |  20  |  0  |   N  |  Y  |     | 主键ID |
|  2  |      TYPE     |  varchar |  32  |  0  |   N  |  N  |     |  类型  |
|  3  |      NAME     |  varchar |  128 |  0  |   N  |  N  |     |  名称  |
|  4  | ENGLISH\_NAME |  varchar |  128 |  0  |   Y  |  N  |     | 英文名称 |
|  5  |      LINK     |  varchar | 1024 |  0  |   N  |  N  |     | 跳转链接 |
|  6  |  CREATE\_TIME | datetime |  19  |  0  |   N  |  N  |     | 创建时间 |
|  7  |     STATUS    |  varchar |  32  |  0  |   N  |  N  |     |  状态  |
|  8  |    CREATOR    |  varchar |  32  |  0  |   N  |  N  |     |  创建者 |

**表名：** T\_DATA\_SOURCE

**说明：** 模块数据源配置

**数据列：**

|  序号 |         名称         |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 |          默认值          |                说明                |
| :-: | :----------------: | :------: | :--: | :-: | :--: | :-: | :-------------------: | :------------------------------: |
|  1  |         ID         |  varchar |  32  |  0  |   N  |  Y  |                       |               主键ID               |
|  2  |    CLUSTER\_NAME   |  varchar |  64  |  0  |   N  |  N  |                       |               集群名称               |
|  3  |    MODULE\_CODE    |  varchar |  64  |  0  |   N  |  N  |                       |               模块标识               |
|  4  | DATA\_SOURCE\_NAME |  varchar |  128 |  0  |   N  |  N  |                       |               数据源名称              |
|  5  |     FULL\_FLAG     |    bit   |   1  |  0  |   Y  |  N  |          b'0'         |       容量是否满标识true：是，false：否      |
|  6  |       CREATOR      |  varchar |  50  |  0  |   N  |  N  |         system        |                创建者               |
|  7  |      MODIFIER      |  varchar |  50  |  0  |   N  |  N  |         system        |                修改者               |
|  8  |       DS\_URL      |  varchar | 1024 |  0  |   Y  |  N  |                       |             数据源URL地址             |
|  9  |         TAG        |  varchar |  128 |  0  |   Y  |  N  |                       |               数据源标签              |
|  10 |        TYPE        |  varchar |  32  |  0  |   N  |  N  |           DB          | 数据库类型，DB:普通数据库，ARCHIVE\_DB:归档数据库 |
|  11 |    UPDATE\_TIME    | datetime |  23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |               修改时间               |
|  12 |    CREATE\_TIME    | datetime |  23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |               创建时间               |

**表名：** T\_FAVORITE

**说明：** 关注收藏表

**数据列：**

|  序号 |      名称     |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :---------: | :-----: | :-: | :-: | :--: | :-: | :-: | :--: |
|  1  |      id     |  bigint |  20 |  0  |   N  |  Y  |     | 主键id |
|  2  | service\_id |  bigint |  20 |  0  |   Y  |  N  |     | 服务id |
|  3  |   username  | varchar |  64 |  0  |   Y  |  N  |     |  用户  |

**表名：** T\_GRAY\_TEST

**说明：**

**数据列：**

|  序号 |      名称     |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :---------: | :-----: | :-: | :-: | :--: | :-: | :-: | :--: |
|  1  |      id     |  bigint |  20 |  0  |   N  |  Y  |     | 主键id |
|  2  | service\_id |  bigint |  20 |  0  |   Y  |  N  |     | 服务id |
|  3  |   username  | varchar |  64 |  0  |   Y  |  N  |     |  用户  |
|  4  |    status   | varchar |  64 |  0  |   Y  |  N  |     | 服务状态 |

**表名：** T\_I18N\_MESSAGE

**说明：** 国际化信息表

**数据列：**

|  序号 |      名称      |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |          默认值          |    说明   |
| :-: | :----------: | :------: | :---: | :-: | :--: | :-: | :-------------------: | :-----: |
|  1  |      ID      |  varchar |   32  |  0  |   N  |  Y  |                       |   主键ID  |
|  2  | MODULE\_CODE |  varchar |   64  |  0  |   N  |  N  |                       |   模块标识  |
|  3  |   LANGUAGE   |  varchar |   64  |  0  |   N  |  N  |                       | 国际化语言信息 |
|  4  |      KEY     |  varchar |  256  |  0  |   N  |  N  |                       |  国际化变量名 |
|  5  |     VALUE    |   text   | 65535 |  0  |   N  |  N  |                       |  国际化变量值 |
|  6  |    CREATOR   |  varchar |   50  |  0  |   N  |  N  |         system        |   创建者   |
|  7  |   MODIFIER   |  varchar |   50  |  0  |   N  |  N  |         system        |   修改者   |
|  8  | UPDATE\_TIME | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   修改时间  |
|  9  | CREATE\_TIME | datetime |   23  |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   创建时间  |

**表名：** T\_LEAF\_ALLOC

**说明：** ID管理数据表

**数据列：**

|  序号 |      名称      |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |        说明       |
| :-: | :----------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-------------: |
|  1  |   BIZ\_TAG   |  varchar  | 128 |  0  |   N  |  Y  |                    |       业务标签      |
|  2  |    MAX\_ID   |   bigint  |  20 |  0  |   N  |  N  |          1         |     当前最大ID值     |
|  3  |     STEP     |    int    |  10 |  0  |   N  |  N  |                    | 步长,每一次请求获取的ID个数 |
|  4  |  DESCRIPTION |  varchar  | 256 |  0  |   Y  |  N  |                    |        说明       |
|  5  | UPDATE\_TIME | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |       更新时间      |

**表名：** T\_MESSAGE\_CODE\_DETAIL

**说明：** code码详情表

**数据列：**

|  序号 |            名称           |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |    说明    |
| :-: | :---------------------: | :-----: | :-: | :-: | :--: | :-: | :-: | :------: |
|  1  |            ID           | varchar |  32 |  0  |   N  |  Y  |     |    主键    |
|  2  |      MESSAGE\_CODE      | varchar | 128 |  0  |   N  |  N  |     |   code码  |
|  3  |       MODULE\_CODE      |   char  |  2  |  0  |   N  |  N  |     |   模块代码   |
|  4  | MESSAGE\_DETAIL\_ZH\_CN | varchar | 500 |  0  |   N  |  N  |     | 中文简体描述信息 |
|  5  | MESSAGE\_DETAIL\_ZH\_TW | varchar | 500 |  0  |   Y  |  N  |     | 中文繁体描述信息 |
|  6  |   MESSAGE\_DETAIL\_EN   | varchar | 500 |  0  |   Y  |  N  |     |  英文描述信息  |

**表名：** T\_NOTICE

**说明：**

**数据列：**

|  序号 |        名称       |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |         默认值        |       说明       |
| :-: | :-------------: | :-------: | :---: | :-: | :--: | :-: | :----------------: | :------------: |
|  1  |        ID       |   bigint  |   20  |  0  |   N  |  Y  |                    |      主键ID      |
|  2  |  NOTICE\_TITLE  |  varchar  |  100  |  0  |   N  |  N  |                    |      公告标题      |
|  3  |   EFFECT\_DATE  | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      生效日期      |
|  4  |  INVALID\_DATE  | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      失效日期      |
|  5  |   CREATE\_DATE  | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      创建日期      |
|  6  |   UPDATE\_DATE  | timestamp |   19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      更新日期      |
|  7  | NOTICE\_CONTENT |    text   | 65535 |  0  |   N  |  N  |                    |      公告内容      |
|  8  |  REDIRECT\_URL  |  varchar  |  200  |  0  |   Y  |  N  |                    |      跳转地址      |
|  9  |   NOTICE\_TYPE  |  tinyint  |   4   |  0  |   N  |  N  |          0         | 消息类型:0.弹框1.跑马灯 |
|  10 |  SERVICE\_NAME  |  varchar  |  1024 |  0  |   Y  |  N  |                    |      服务名称      |

**表名：** T\_PROJECT

**说明：** 项目信息表

**数据列：**

|  序号 |            名称            |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 |  默认值 |          说明         |
| :-: | :----------------------: | :-------: | :---: | :-: | :--: | :-: | :--: | :-----------------: |
|  1  |            ID            |   bigint  |   20  |  0  |   N  |  Y  |      |         主键ID        |
|  2  |        created\_at       | timestamp |   19  |  0  |   Y  |  N  |      |         创建时间        |
|  3  |        updated\_at       | timestamp |   19  |  0  |   Y  |  N  |      |         更新时间        |
|  4  |        deleted\_at       | timestamp |   19  |  0  |   Y  |  N  |      |         删除时间        |
|  5  |           extra          |    text   | 65535 |  0  |   Y  |  N  |      |         额外信息        |
|  6  |          creator         |  varchar  |   32  |  0  |   Y  |  N  |      |         创建者         |
|  7  |        description       |    text   | 65535 |  0  |   Y  |  N  |      |          描述         |
|  8  |           kind           |    int    |   10  |  0  |   Y  |  N  |      |         容器类型        |
|  9  |        cc\_app\_id       |   bigint  |   20  |  0  |   Y  |  N  |      |         应用ID        |
|  10 |       cc\_app\_name      |  varchar  |   64  |  0  |   Y  |  N  |      |         应用名称        |
|  11 |       is\_offlined       |    bit    |   1   |  0  |   Y  |  N  | b'0' |         是否停用        |
|  12 |        PROJECT\_ID       |  varchar  |   32  |  0  |   N  |  N  |      |         项目ID        |
|  13 |       project\_name      |  varchar  |   64  |  0  |   N  |  N  |      |         项目名称        |
|  14 |       english\_name      |  varchar  |   64  |  0  |   N  |  N  |      |         英文名称        |
|  15 |          updator         |  varchar  |   32  |  0  |   Y  |  N  |      |         更新人         |
|  16 |       project\_type      |    int    |   10  |  0  |   Y  |  N  |      |         项目类型        |
|  17 |          use\_bk         |    bit    |   1   |  0  |   Y  |  N  | b'1' |        是否用蓝鲸        |
|  18 |       deploy\_type       |    text   | 65535 |  0  |   Y  |  N  |      |         部署类型        |
|  19 |          bg\_id          |   bigint  |   20  |  0  |   Y  |  N  |      |        事业群ID        |
|  20 |         bg\_name         |  varchar  |  255  |  0  |   Y  |  N  |      |        事业群名称        |
|  21 |    business\_line\_id    |   bigint  |   20  |  0  |   Y  |  N  |      |        业务线ID        |
|  22 |   business\_line\_name   |  varchar  |  255  |  0  |   Y  |  N  |      |        业务线名称        |
|  23 |         dept\_id         |   bigint  |   20  |  0  |   Y  |  N  |      |      项目所属二级机构ID     |
|  24 |        dept\_name        |  varchar  |  255  |  0  |   Y  |  N  |      |      项目所属二级机构名称     |
|  25 |        center\_id        |   bigint  |   20  |  0  |   Y  |  N  |      |         中心ID        |
|  26 |       center\_name       |  varchar  |  255  |  0  |   Y  |  N  |      |         中心名字        |
|  27 |         data\_id         |   bigint  |   20  |  0  |   Y  |  N  |      |         数据ID        |
|  28 |        is\_secrecy       |    bit    |   1   |  0  |   Y  |  N  | b'0' |         是否保密        |
|  29 | is\_helm\_chart\_enabled |    bit    |   1   |  0  |   Y  |  N  | b'0' |       是否启用图表激活      |
|  30 |     approval\_status     |    int    |   10  |  0  |   Y  |  N  |   1  |         审核状态        |
|  31 |        logo\_addr        |    text   | 65535 |  0  |   Y  |  N  |      |        logo地址       |
|  32 |         approver         |  varchar  |   32  |  0  |   Y  |  N  |      |         批准人         |
|  33 |          remark          |    text   | 65535 |  0  |   Y  |  N  |      |          评论         |
|  34 |      approval\_time      | timestamp |   19  |  0  |   Y  |  N  |      |         批准时间        |
|  35 |     creator\_bg\_name    |  varchar  |  128  |  0  |   Y  |  N  |      |       创建者事业群名称      |
|  36 |    creator\_dept\_name   |  varchar  |  128  |  0  |   Y  |  N  |      |    创建者项目所属二级机构名称    |
|  37 |   creator\_center\_name  |  varchar  |  128  |  0  |   Y  |  N  |      |       创建者中心名字       |
|  38 |    hybrid\_cc\_app\_id   |   bigint  |   20  |  0  |   Y  |  N  |      |         应用ID        |
|  39 |     enable\_external     |    bit    |   1   |  0  |   Y  |  N  |      |     是否支持构建机访问外网     |
|  40 |        enable\_idc       |    bit    |   1   |  0  |   Y  |  N  |      |      是否支持IDC构建机     |
|  41 |          enabled         |    bit    |   1   |  0  |   Y  |  N  |      |         是否启用        |
|  42 |          CHANNEL         |  varchar  |   32  |  0  |   N  |  N  |  BS  |         项目渠道        |
|  43 |      pipeline\_limit     |    int    |   10  |  0  |   Y  |  N  |  500 |       流水线数量上限       |
|  44 |        router\_tag       |  varchar  |   32  |  0  |   Y  |  N  |      |       网关路由tags      |
|  45 |       relation\_id       |  varchar  |   32  |  0  |   Y  |  N  |      |       扩展系统关联ID      |
|  46 |    other\_router\_tags   |  varchar  |  128  |  0  |   Y  |  N  |      |     其他系统网关路由tags    |
|  47 |        properties        |    text   | 65535 |  0  |   Y  |  N  |      |        项目其他配置       |
|  48 |      SUBJECT\_SCOPES     |    text   | 65535 |  0  |   Y  |  N  |      |      最大可授权人员范围      |
|  49 |       AUTH\_SECRECY      |    int    |   10  |  0  |   Y  |  N  |   0  | 项目性质,0-公开，1-保密,2-机密 |
|  50 |        product\_id       |    int    |   10  |  0  |   Y  |  N  |      |        运营产品ID       |

**表名：** T\_PROJECT\_APPROVAL

**说明：** 项目审批表

**数据列：**

|  序号 |          名称          |    数据类型   |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |              说明              |
| :-: | :------------------: | :-------: | :---: | :-: | :--: | :-: | :-: | :--------------------------: |
|  1  |          ID          |   bigint  |   20  |  0  |   N  |  Y  |     |             主键ID             |
|  2  |     PROJECT\_NAME    |  varchar  |   64  |  0  |   N  |  N  |     |             项目名称             |
|  3  |     ENGLISH\_NAME    |  varchar  |   64  |  0  |   N  |  N  |     |             英文名称             |
|  4  |      DESCRIPTION     |    text   | 65535 |  0  |   Y  |  N  |     |              描述              |
|  5  |      CREATED\_AT     | timestamp |   19  |  0  |   Y  |  N  |     |             创建时间             |
|  6  |      UPDATED\_AT     | timestamp |   19  |  0  |   Y  |  N  |     |             更新时间             |
|  7  |        CREATOR       |  varchar  |   32  |  0  |   Y  |  N  |     |              创建者             |
|  8  |        UPDATOR       |  varchar  |   32  |  0  |   Y  |  N  |     |              更新人             |
|  9  |        BG\_ID        |   bigint  |   20  |  0  |   Y  |  N  |     |             事业群ID            |
|  10 |       BG\_NAME       |  varchar  |  255  |  0  |   Y  |  N  |     |             事业群名称            |
|  11 |  BUSINESS\_LINE\_ID  |   bigint  |   20  |  0  |   Y  |  N  |     |             业务线ID            |
|  12 | BUSINESS\_LINE\_NAME |  varchar  |  255  |  0  |   Y  |  N  |     |             业务线名称            |
|  13 |       DEPT\_ID       |   bigint  |   20  |  0  |   Y  |  N  |     |          项目所属二级机构ID          |
|  14 |      DEPT\_NAME      |  varchar  |  255  |  0  |   Y  |  N  |     |          项目所属二级机构名称          |
|  15 |      CENTER\_ID      |   bigint  |   20  |  0  |   Y  |  N  |     |             中心ID             |
|  16 |     CENTER\_NAME     |  varchar  |  255  |  0  |   Y  |  N  |     |             中心名字             |
|  17 |      LOGO\_ADDR      |    text   | 65535 |  0  |   Y  |  N  |     |            logo地址            |
|  18 |       APPROVER       |  varchar  |   32  |  0  |   Y  |  N  |     |              批准人             |
|  19 |   APPROVAL\_STATUS   |    int    |   10  |  0  |   Y  |  N  |  1  |             审核状态             |
|  20 |    APPROVAL\_TIME    | timestamp |   19  |  0  |   Y  |  N  |     |             批准时间             |
|  21 |     RELATION\_ID     |  varchar  |   32  |  0  |   Y  |  N  |     |           扩展系统关联ID           |
|  22 |    SUBJECT\_SCOPES   |    text   | 65535 |  0  |   Y  |  N  |     |           最大可授权人员范围          |
|  23 |     AUTH\_SECRECY    |    int    |   10  |  0  |   Y  |  N  |  0  |      项目性质,0-公开,1-保密,2-机密     |
|  24 |     TIPS\_STATUS     |    int    |   10  |  0  |   Y  |  N  |  0  | 提示状态,0-不展示,1-展示创建成功,2-展示更新成功 |
|  25 |     PROJECT\_TYPE    |    int    |   10  |  0  |   Y  |  N  |     |             项目类型             |
|  26 |      PRODUCT\_ID     |    int    |   10  |  0  |   Y  |  N  |     |            运营产品ID            |
|  27 |     PRODUCT\_NAME    |  varchar  |   64  |  0  |   Y  |  N  |     |            运营产品名称            |

**表名：** T\_PROJECT\_DATA\_MIGRATE\_HISTORY

**说明：** 项目数据迁移历史表

**数据列：**

|  序号 |             名称             |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |    说明    |
| :-: | :------------------------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :------: |
|  1  |             ID             |  varchar |  32 |  0  |   N  |  Y  |                       |   主键ID   |
|  2  |         PROJECT\_ID        |  varchar |  64 |  0  |   N  |  N  |                       |   项目ID   |
|  3  |        MODULE\_CODE        |  varchar |  64 |  0  |   N  |  N  |                       |   模块标识   |
|  4  |    SOURCE\_CLUSTER\_NAME   |  varchar |  64 |  0  |   N  |  N  |                       |  被迁移集群名称 |
|  5  | SOURCE\_DATA\_SOURCE\_NAME |  varchar | 128 |  0  |   N  |  N  |                       | 被迁移数据源名称 |
|  6  |    TARGET\_CLUSTER\_NAME   |  varchar |  64 |  0  |   N  |  N  |                       |  迁移集群名称  |
|  7  | TARGET\_DATA\_SOURCE\_NAME |  varchar | 128 |  0  |   N  |  N  |                       |  迁移数据源名称 |
|  8  |      TARGET\_DATA\_TAG     |  varchar | 128 |  0  |   Y  |  N  |                       |  迁移数据源标签 |
|  9  |        PIPELINE\_ID        |  varchar |  34 |  0  |   Y  |  N  |                       |   流水线ID  |
|  10 |           CREATOR          |  varchar |  50 |  0  |   N  |  N  |         system        |    创建者   |
|  11 |          MODIFIER          |  varchar |  50 |  0  |   N  |  N  |         system        |    修改者   |
|  12 |        UPDATE\_TIME        | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   修改时间   |
|  13 |        CREATE\_TIME        | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   创建时间   |

**表名：** T\_PROJECT\_LABEL

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--: |
|  1  |      ID      |  varchar |  32 |  0  |   N  |  Y  |                    | 主键ID |
|  2  |  LABEL\_NAME |  varchar |  45 |  0  |   N  |  N  |                    | 标签名称 |
|  3  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 创建时间 |
|  4  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 修改时间 |

**表名：** T\_PROJECT\_LABEL\_REL

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--: |
|  1  |      ID      |  varchar |  32 |  0  |   N  |  Y  |                    | 主键ID |
|  2  |   LABEL\_ID  |  varchar |  32 |  0  |   N  |  N  |                    | 标签ID |
|  3  |  PROJECT\_ID |  varchar |  32 |  0  |   N  |  N  |                    | 项目ID |
|  4  | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 创建时间 |
|  5  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP | 修改时间 |

**表名：** T\_SERVICE

**说明：** 服务信息表

**数据列：**

|  序号 |          名称         |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 |  默认值 |       说明       |
| :-: | :-----------------: | :------: | :---: | :-: | :--: | :-: | :--: | :------------: |
|  1  |          id         |  bigint  |   20  |  0  |   N  |  Y  |      |       id       |
|  2  |         name        |  varchar |   64  |  0  |   Y  |  N  |      |       名称       |
|  3  |    english\_name    |  varchar |   64  |  0  |   Y  |  N  |      |      英文名称      |
|  4  |  service\_type\_id  |  bigint  |   20  |  0  |   Y  |  N  |      |     服务类型ID     |
|  5  |         link        |  varchar |  255  |  0  |   Y  |  N  |      |      跳转链接      |
|  6  |      link\_new      |  varchar |  255  |  0  |   Y  |  N  |      |      新跳转链接     |
|  7  |     inject\_type    |  varchar |   64  |  0  |   Y  |  N  |      |      注入类型      |
|  8  |     iframe\_url     |  varchar |  255  |  0  |   Y  |  N  |      |   iframeUrl地址  |
|  9  |       css\_url      |  varchar |  255  |  0  |   Y  |  N  |      |    cssUrl地址    |
|  10 |       js\_url       |  varchar |  255  |  0  |   Y  |  N  |      |     jsUrl地址    |
|  11 | show\_project\_list |    bit   |   1   |  0  |   Y  |  N  |      |     是否在页面显示    |
|  12 |      show\_nav      |    bit   |   1   |  0  |   Y  |  N  |      |     showNav    |
|  13 |  project\_id\_type  |  varchar |   64  |  0  |   Y  |  N  |      |     项目ID类型     |
|  14 |        status       |  varchar |   64  |  0  |   Y  |  N  |      |       状态       |
|  15 |    created\_user    |  varchar |   64  |  0  |   Y  |  N  |      |       创建者      |
|  16 |    created\_time    | datetime |   19  |  0  |   Y  |  N  |      |      创建时间      |
|  17 |    updated\_user    |  varchar |   64  |  0  |   Y  |  N  |      |       修改者      |
|  18 |    updated\_time    | datetime |   19  |  0  |   Y  |  N  |      |      修改时间      |
|  19 |       deleted       |    bit   |   1   |  0  |   Y  |  N  |      |      是否删除      |
|  20 |    gray\_css\_url   |  varchar |  255  |  0  |   Y  |  N  |      |   灰度cssUrl地址   |
|  21 |    gray\_js\_url    |  varchar |  255  |  0  |   Y  |  N  |      |    灰度jsUrl地址   |
|  22 |      logo\_url      |  varchar |  256  |  0  |   Y  |  N  |      |     logo地址     |
|  23 |     web\_socket     |   text   | 65535 |  0  |   Y  |  N  |      | 支持webSocket的页面 |
|  24 |        weight       |    int   |   10  |  0  |   Y  |  N  |      |       权值       |
|  25 |  gray\_iframe\_url  |  varchar |  255  |  0  |   Y  |  N  |      |  灰度iframeUrl地址 |
|  26 |     new\_window     |    bit   |   1   |  0  |   Y  |  N  | b'0' |    是否打开新标签页    |
|  27 |    new\_windowUrl   |  varchar |  200  |  0  |   Y  |  N  |      |     新标签页地址     |
|  28 |    cluster\_type    |  varchar |   32  |  0  |   N  |  N  |      |      集群类型      |

**表名：** T\_SERVICE\_TYPE

**说明：** 服务类型表

**数据列：**

|  序号 |       名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |       ID       |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |      title     |  varchar |  64 |  0  |   Y  |  N  |     |  邮件标题  |
|  3  | english\_title |  varchar |  64 |  0  |   Y  |  N  |     | 英文邮件标题 |
|  4  |  created\_user |  varchar |  64 |  0  |   Y  |  N  |     |   创建者  |
|  5  |  created\_time | datetime |  19 |  0  |   Y  |  N  |     |  创建时间  |
|  6  |  updated\_user |  varchar |  64 |  0  |   Y  |  N  |     |   修改者  |
|  7  |  updated\_time | datetime |  19 |  0  |   Y  |  N  |     |  修改时间  |
|  8  |     deleted    |    bit   |  1  |  0  |   Y  |  N  |     |  是否删除  |
|  9  |     weight     |    int   |  10 |  0  |   Y  |  N  |     |   权值   |

**表名：** T\_SHARDING\_ROUTING\_RULE

**说明：** DB分片路由规则

**数据列：**

|  序号 |         名称         |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |           说明           |
| :-: | :----------------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :--------------------: |
|  1  |         ID         |  varchar |  32 |  0  |   N  |  Y  |                       |          主键ID          |
|  2  |    ROUTING\_NAME   |  varchar | 128 |  0  |   N  |  N  |                       |          路由名称          |
|  3  |    ROUTING\_RULE   |  varchar | 256 |  0  |   N  |  N  |                       |          路由规则          |
|  4  |    CLUSTER\_NAME   |  varchar |  64 |  0  |   N  |  N  |          prod         |          集群名称          |
|  5  |    MODULE\_CODE    |  varchar |  64 |  0  |   N  |  N  |        PROCESS        |          模块标识          |
|  6  |        TYPE        |  varchar |  32 |  0  |   N  |  N  |           DB          | 路由类型，DB:数据库，TABLE:数据库表 |
|  7  | DATA\_SOURCE\_NAME |  varchar | 128 |  0  |   N  |  N  |         ds\_0         |          数据源名称         |
|  8  |     TABLE\_NAME    |  varchar | 128 |  0  |   Y  |  N  |                       |         数据库表名称         |
|  9  |       CREATOR      |  varchar |  50 |  0  |   N  |  N  |         system        |           创建者          |
|  10 |      MODIFIER      |  varchar |  50 |  0  |   N  |  N  |         system        |           修改者          |
|  11 |    UPDATE\_TIME    | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |          修改时间          |
|  12 |    CREATE\_TIME    | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |          创建时间          |

**表名：** T\_TABLE\_SHARDING\_CONFIG

**说明：** 数据库表分片配置

**数据列：**

|  序号 |       名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |   说明   |
| :-: | :-----------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :----: |
|  1  |       ID      |  varchar |  32 |  0  |   N  |  Y  |                       |  主键ID  |
|  2  | CLUSTER\_NAME |  varchar |  64 |  0  |   N  |  N  |                       |  集群名称  |
|  3  |  MODULE\_CODE |  varchar |  64 |  0  |   N  |  N  |                       |  模块标识  |
|  4  |  TABLE\_NAME  |  varchar | 128 |  0  |   N  |  N  |                       | 数据库表名称 |
|  5  | SHARDING\_NUM |    int   |  10 |  0  |   N  |  N  |           5           |  分表数量  |
|  6  |    CREATOR    |  varchar |  50 |  0  |   N  |  N  |         system        |   创建者  |
|  7  |    MODIFIER   |  varchar |  50 |  0  |   N  |  N  |         system        |   修改者  |
|  8  |  UPDATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |  修改时间  |
|  9  |  CREATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |  创建时间  |

**表名：** T\_USER

**说明：** 用户表

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |       说明       |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :------------: |
|  1  |   USER\_ID   |  varchar |  64 |  0  |   N  |  Y  |                    |      用户ID      |
|  2  |     NAME     |  varchar |  64 |  0  |   N  |  N  |                    |       名称       |
|  3  |    BG\_ID    |    int   |  10 |  0  |   N  |  N  |                    |      事业群ID     |
|  4  |   BG\_NAME   |  varchar | 256 |  0  |   N  |  N  |                    |      事业群名称     |
|  5  |   DEPT\_ID   |    int   |  10 |  0  |   Y  |  N  |                    |   项目所属二级机构ID   |
|  6  |  DEPT\_NAME  |  varchar | 256 |  0  |   Y  |  N  |                    |   项目所属二级机构名称   |
|  7  |  CENTER\_ID  |    int   |  10 |  0  |   Y  |  N  |                    |      中心ID      |
|  8  | CENTER\_NAME |  varchar | 256 |  0  |   Y  |  N  |                    |      中心名字      |
|  9  |   GROYP\_ID  |    int   |  10 |  0  |   Y  |  N  |                    |      用户组ID     |
|  10 |  GROUP\_NAME |  varchar | 256 |  0  |   Y  |  N  |                    |      用户组名称     |
|  11 | CREATE\_TIME | datetime |  19 |  0  |   N  |  N  |                    |      创建时间      |
|  12 | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |      更新时间      |
|  13 |  USER\_TYPE  |    bit   |  1  |  0  |   N  |  N  |        b'0'        | 用户类型0普通用户1公共账号 |

**表名：** T\_USER\_DAILY\_FIRST\_AND\_LAST\_LOGIN

**说明：**

**数据列：**

|  序号 |         名称         |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :----------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |         ID         |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |      USER\_ID      |  varchar |  64 |  0  |   N  |  N  |     |  用户ID  |
|  3  |        DATE        |   date   |  10 |  0  |   N  |  N  |     |   日期   |
|  4  | FIRST\_LOGIN\_TIME | datetime |  19 |  0  |   N  |  N  |     | 首次登录时间 |
|  5  |  LAST\_LOGIN\_TIME | datetime |  19 |  0  |   N  |  N  |     | 最近登录时间 |

**表名：** T\_USER\_DAILY\_LOGIN

**说明：**

**数据列：**

|  序号 |      名称     |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :---------: | :------: | :-: | :-: | :--: | :-: | :-: | :--: |
|  1  |      ID     |  bigint  |  20 |  0  |   N  |  Y  |     | 主键ID |
|  2  |   USER\_ID  |  varchar |  64 |  0  |   N  |  N  |     | 用户ID |
|  3  |     DATE    |   date   |  10 |  0  |   N  |  N  |     |  日期  |
|  4  | LOGIN\_TIME | datetime |  19 |  0  |   N  |  N  |     | 登录时间 |
|  5  |      OS     |  varchar |  32 |  0  |   N  |  N  |     | 操作系统 |
|  6  |      IP     |  varchar |  32 |  0  |   N  |  N  |     | ip地址 |

**表名：** T\_USER\_LOCALE

**说明：** 用户设置的国际化信息

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |          默认值          |    说明   |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-------------------: | :-----: |
|  1  |   USER\_ID   |  varchar |  64 |  0  |   N  |  Y  |                       |   用户ID  |
|  2  |   LANGUAGE   |  varchar |  64 |  0  |   N  |  N  |                       | 国际化语言信息 |
|  3  | UPDATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   修改时间  |
|  4  | CREATE\_TIME | datetime |  23 |  0  |   N  |  N  | CURRENT\_TIMESTAMP(3) |   创建时间  |
