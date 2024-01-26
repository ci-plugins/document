# devops\_ci\_dispatch

**数据库名：** devops\_ci\_dispatch

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_dispatch的数据库文档

|                                                                 表名                                                                 |                 说明                |
| :--------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------: |
|                      [T\_DISPATCH\_KUBERNETES\_BUILD](devops\_ci\_dispatch.md#T\_DISPATCH\_KUBERNETES\_BUILD)                      |    dispatch-kubernetes流水线构建机信息    |
| [T\_DISPATCH\_KUBERNETES\_BUILD\_CONTAINER\_POOL\_NO](devops\_ci\_dispatch.md#T\_DISPATCH\_KUBERNETES\_BUILD\_CONTAINER\_POOL\_NO) | buildId和containerName,poolNo的映射关系 |
|                 [T\_DISPATCH\_KUBERNETES\_BUILD\_HIS](devops\_ci\_dispatch.md#T\_DISPATCH\_KUBERNETES\_BUILD\_HIS)                 |      dispatchkubernetes构建历史记录     |
|                        [T\_DISPATCH\_PIPELINE\_BUILD](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_BUILD)                        |                                   |
|                [T\_DISPATCH\_PIPELINE\_DOCKER\_BUILD](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_BUILD)                |                                   |
|                [T\_DISPATCH\_PIPELINE\_DOCKER\_DEBUG](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_DEBUG)                |                                   |
|               [T\_DISPATCH\_PIPELINE\_DOCKER\_ENABLE](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_ENABLE)               |                                   |
|                 [T\_DISPATCH\_PIPELINE\_DOCKER\_HOST](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_HOST)                 |                                   |
|           [T\_DISPATCH\_PIPELINE\_DOCKER\_HOST\_ZONE](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_HOST\_ZONE)           |                                   |
|             [T\_DISPATCH\_PIPELINE\_DOCKER\_IP\_INFO](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_IP\_INFO)             |            DOCKER构建机负载表           |
|                 [T\_DISPATCH\_PIPELINE\_DOCKER\_POOL](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_POOL)                 |           DOCKER并发构建池状态表          |
|                 [T\_DISPATCH\_PIPELINE\_DOCKER\_TASK](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_TASK)                 |                                   |
|          [T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_DRIFT](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_DRIFT)          |          DOCKER构建任务漂移记录表          |
|         [T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_SIMPLE](devops\_ci\_dispatch.md#T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_SIMPLE)         |            DOCKER构建任务表            |
|                     [T\_DISPATCH\_PROJECT\_RUN\_TIME](devops\_ci\_dispatch.md#T\_DISPATCH\_PROJECT\_RUN\_TIME)                     |             项目当月已使用额度             |
|                     [T\_DISPATCH\_QUOTA\_JOB\_SYSTEM](devops\_ci\_dispatch.md#T\_DISPATCH\_QUOTA\_JOB\_SYSTEM)                     |            流水线JOB配额系统表            |
|                         [T\_DISPATCH\_QUOTA\_PROJECT](devops\_ci\_dispatch.md#T\_DISPATCH\_QUOTA\_PROJECT)                         |                项目配额               |
|                          [T\_DISPATCH\_QUOTA\_SYSTEM](devops\_ci\_dispatch.md#T\_DISPATCH\_QUOTA\_SYSTEM)                          |                系统配额               |
|                          [T\_DISPATCH\_RUNNING\_JOBS](devops\_ci\_dispatch.md#T\_DISPATCH\_RUNNING\_JOBS)                          |              运行中的JOB              |
|               [T\_DISPATCH\_THIRDPARTY\_AGENT\_BUILD](devops\_ci\_dispatch.md#T\_DISPATCH\_THIRDPARTY\_AGENT\_BUILD)               |                                   |
|       [T\_DISPATCH\_THIRDPARTY\_AGENT\_DOCKER\_DEBUG](devops\_ci\_dispatch.md#T\_DISPATCH\_THIRDPARTY\_AGENT\_DOCKER\_DEBUG)       |          第三方构建机Docker登录调试         |
|                        [T\_DOCKER\_RESOURCE\_OPTIONS](devops\_ci\_dispatch.md#T\_DOCKER\_RESOURCE\_OPTIONS)                        |            docker基础配额表            |

**表名：** T\_DISPATCH\_KUBERNETES\_BUILD

**说明：** dispatch-kubernetes流水线构建机信息

**数据列：**

|  序号 |        名称       |    数据类型   |  长度  | 小数位 | 允许空值 |  主键 |   默认值  |      说明     |
| :-: | :-------------: | :-------: | :--: | :-: | :--: | :-: | :----: | :---------: |
|  1  |   PIPELINE\_ID  |  varchar  |  34  |  0  |   N  |  Y  |        |             |
|  2  |   VM\_SEQ\_ID   |  varchar  |  34  |  0  |   N  |  Y  |        |             |
|  3  |     POOL\_NO    |    int    |  10  |  0  |   N  |  Y  |        |             |
|  4  |   PROJECT\_ID   |  varchar  |  64  |  0  |   N  |  N  |        |             |
|  5  | CONTAINER\_NAME |  varchar  |  128 |  0  |   N  |  N  |        |             |
|  6  |      IMAGES     |  varchar  | 1024 |  0  |   N  |  N  |        |             |
|  7  |      STATUS     |    int    |  10  |  0  |   N  |  N  |        |             |
|  8  |  CREATED\_TIME  | timestamp |  19  |  0  |   Y  |  N  |        |             |
|  9  |   UPDATE\_TIME  | timestamp |  19  |  0  |   Y  |  N  |        |             |
|  10 |     USER\_ID    |  varchar  |  34  |  0  |   N  |  N  |        |             |
|  11 |  DEBUG\_STATUS  |    bit    |   1  |  0  |   Y  |  N  |  b'0'  | 是否处于debug状态 |
|  12 |   DEBUG\_TIME   | timestamp |  19  |  0  |   Y  |  N  |        |   debug时间   |
|  13 |       CPU       |    int    |  10  |  0  |   Y  |  N  |   16   |     CPU     |
|  14 |      MEMORY     |  varchar  |  64  |  0  |   Y  |  N  | 32768M |      内存     |
|  15 |       DISK      |  varchar  |  64  |  0  |   Y  |  N  |  100G  |      磁盘     |

**表名：** T\_DISPATCH\_KUBERNETES\_BUILD\_CONTAINER\_POOL\_NO

**说明：** buildId和containerName,poolNo的映射关系

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |    BUILD\_ID    |  varchar |  64 |  0  |   N  |  Y  |                    |   构建ID  |
|  2  |   VM\_SEQ\_ID   |  varchar |  64 |  0  |   N  |  Y  |                    | VmSeqID |
|  3  | CONTAINER\_NAME |  varchar | 128 |  0  |   Y  |  N  |                    |   容器名称  |
|  4  |     POOL\_NO    |  varchar | 128 |  0  |   Y  |  N  |                    |  构建机池编号 |
|  5  |   CREATE\_TIME  | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |   创建时间  |
|  6  |  EXECUTE\_COUNT |    int   |  10 |  0  |   N  |  Y  |          1         | 流水线重试次数 |

**表名：** T\_DISPATCH\_KUBERNETES\_BUILD\_HIS

**说明：** dispatchkubernetes构建历史记录

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |     说明     |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :--------: |
|  1  |        ID       |  bigint  |  20 |  0  |   N  |  Y  |                    |            |
|  2  |   PIPELINE\_ID  |  varchar |  64 |  0  |   N  |  N  |                    | pipelineid |
|  3  |    BUIDLD\_ID   |  varchar |  64 |  0  |   N  |  N  |                    |   buildid  |
|  4  |   VM\_SEQ\_ID   |  varchar |  64 |  0  |   N  |  N  |                    |   vmseqid  |
|  5  | CONTAINER\_NAME |  varchar | 128 |  0  |   Y  |  N  |                    |    容器名称    |
|  6  |   GMT\_CREATE   | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |    创建时间    |
|  7  |  GMT\_MODIFIED  | datetime |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |    修改时间    |
|  8  |       CPU       |    int   |  10 |  0  |   Y  |  N  |         16         |     CPU    |
|  9  |      MEMORY     |  varchar |  64 |  0  |   Y  |  N  |       32768M       |     内存     |
|  10 |       DISK      |  varchar |  64 |  0  |   Y  |  N  |        100G        |     磁盘     |
|  11 |   SECRET\_KEY   |  varchar |  64 |  0  |   Y  |  N  |                    |    构建密钥    |
|  12 |     POOL\_NO    |  varchar |  64 |  0  |   Y  |  N  |                    |    并发构建池   |
|  13 |  EXECUTE\_COUNT |    int   |  10 |  0  |   Y  |  N  |          1         |   流水线重试次数  |

**表名：** T\_DISPATCH\_PIPELINE\_BUILD

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :-----------: | :------: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  |       ID      |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID |
|  2  |  PROJECT\_ID  |  varchar |  32 |  0  |   N  |  N  |     |  项目ID |
|  3  |  PIPELINE\_ID |  varchar |  34 |  0  |   N  |  N  |     | 流水线ID |
|  4  |   BUILD\_ID   |  varchar |  34 |  0  |   N  |  N  |     |  构建ID |
|  5  |  VM\_SEQ\_ID  |  varchar |  34 |  0  |   N  |  N  |     | 构建序列号 |
|  6  |     VM\_ID    |  bigint  |  20 |  0  |   N  |  N  |     | 虚拟机ID |
|  7  | CREATED\_TIME | datetime |  19 |  0  |   N  |  N  |     |  创建时间 |
|  8  | UPDATED\_TIME | datetime |  19 |  0  |   N  |  N  |     |  更新时间 |
|  9  |     STATUS    |    int   |  10 |  0  |   N  |  N  |     |   状态  |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_BUILD

**说明：**

**数据列：**

|  序号 |         名称        |   数据类型   |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |     说明     |
| :-: | :---------------: | :------: | :---: | :-: | :--: | :-: | :-: | :--------: |
|  1  |         ID        |  bigint  |   20  |  0  |   N  |  Y  |     |    主键ID    |
|  2  |     BUILD\_ID     |  varchar |   64  |  0  |   N  |  N  |     |    构建ID    |
|  3  |    VM\_SEQ\_ID    |    int   |   10  |  0  |   N  |  N  |     |    构建序列号   |
|  4  |    SECRET\_KEY    |  varchar |   64  |  0  |   N  |  N  |     |     密钥     |
|  5  |       STATUS      |    int   |   10  |  0  |   N  |  N  |     |     状态     |
|  6  |   CREATED\_TIME   | datetime |   19  |  0  |   N  |  N  |     |    创建时间    |
|  7  |   UPDATED\_TIME   | datetime |   19  |  0  |   N  |  N  |     |    更新时间    |
|  8  |        ZONE       |  varchar |  128  |  0  |   Y  |  N  |     |    构建机地域   |
|  9  |    PROJECT\_ID    |  varchar |   34  |  0  |   Y  |  N  |     |    项目ID    |
|  10 |    PIPELINE\_ID   |  varchar |   34  |  0  |   Y  |  N  |     |    流水线ID   |
|  11 | DISPATCH\_MESSAGE |  varchar |  4096 |  0  |   Y  |  N  |     |    发送信息    |
|  12 |  STARTUP\_MESSAGE |   text   | 65535 |  0  |   Y  |  N  |     |    启动信息    |
|  13 |     ROUTE\_KEY    |  varchar |   64  |  0  |   Y  |  N  |     | 消息队列的路由KEY |
|  14 |  DOCKER\_INST\_ID |  bigint  |   20  |  0  |   Y  |  N  |     |            |
|  15 |    VERSION\_ID    |    int   |   10  |  0  |   Y  |  N  |     |    版本ID    |
|  16 |    TEMPLATE\_ID   |    int   |   10  |  0  |   Y  |  N  |     |    模板ID    |
|  17 |   NAMESPACE\_ID   |  bigint  |   20  |  0  |   Y  |  N  |     |   命名空间ID   |
|  18 |     DOCKER\_IP    |  varchar |   64  |  0  |   Y  |  N  |     |    构建机IP   |
|  19 |   CONTAINER\_ID   |  varchar |  128  |  0  |   Y  |  N  |     |   构建容器ID   |
|  20 |      POOL\_NO     |    int   |   10  |  0  |   Y  |  N  |  0  |   构建容器池序号  |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_DEBUG

**说明：**

**数据列：**

|  序号 |          名称         |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |       说明       |
| :-: | :-----------------: | :------: | :--: | :-: | :--: | :-: | :-: | :------------: |
|  1  |          ID         |  bigint  |  20  |  0  |   N  |  Y  |     |      主键ID      |
|  2  |     PROJECT\_ID     |  varchar |  64  |  0  |   N  |  N  |     |      项目ID      |
|  3  |     PIPELINE\_ID    |  varchar |  34  |  0  |   N  |  N  |     |      流水线ID     |
|  4  |     VM\_SEQ\_ID     |  varchar |  34  |  0  |   N  |  N  |     |      构建序列号     |
|  5  |       POOL\_NO      |    int   |  10  |  0  |   N  |  N  |  0  |      构建池序号     |
|  6  |        STATUS       |    int   |  10  |  0  |   N  |  N  |     |       状态       |
|  7  |        TOKEN        |  varchar |  128 |  0  |   Y  |  N  |     |      TOKEN     |
|  8  |     IMAGE\_NAME     |  varchar | 1024 |  0  |   N  |  N  |     |      镜像名称      |
|  9  |      HOST\_TAG      |  varchar |  128 |  0  |   Y  |  N  |     |      主机标签      |
|  10 |    CONTAINER\_ID    |  varchar |  128 |  0  |   Y  |  N  |     |     构建容器ID     |
|  11 |    CREATED\_TIME    | datetime |  19  |  0  |   N  |  N  |     |      创建时间      |
|  12 |    UPDATED\_TIME    | datetime |  19  |  0  |   N  |  N  |     |      修改时间      |
|  13 |         ZONE        |  varchar |  128 |  0  |   Y  |  N  |     |      构建机地域     |
|  14 |      BUILD\_ENV     |  varchar | 4096 |  0  |   Y  |  N  |     |     构建机环境变量    |
|  15 |    REGISTRY\_USER   |  varchar |  128 |  0  |   Y  |  N  |     |      注册用户名     |
|  16 |    REGISTRY\_PWD    |  varchar |  128 |  0  |   Y  |  N  |     |     注册用户密码     |
|  17 |     IMAGE\_TYPE     |  varchar |  128 |  0  |   Y  |  N  |     |      镜像类型      |
|  18 | IMAGE\_PUBLIC\_FLAG |    bit   |   1  |  0  |   Y  |  N  |     | 镜像是否为公共镜像：0否1是 |
|  19 |   IMAGE\_RD\_TYPE   |    bit   |   1  |  0  |   Y  |  N  |     | 镜像研发来源：0自研1第三方 |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_ENABLE

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明  |
| :-: | :----------: | :-----: | :-: | :-: | :--: | :-: | :-: | :---: |
|  1  | PIPELINE\_ID | varchar |  64 |  0  |   N  |  Y  |     | 流水线ID |
|  2  |    ENABLE    |   bit   |  1  |  0  |   N  |  N  |  0  |  是否启用 |
|  3  |  VM\_SEQ\_ID |   int   |  10 |  0  |   N  |  Y  |  -1 | 构建序列号 |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_HOST

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |     说明     |
| :-: | :-----------: | :------: | :--: | :-: | :--: | :-: | :-: | :--------: |
|  1  | PROJECT\_CODE |  varchar |  128 |  0  |   N  |  Y  |     |   用户组所属项目  |
|  2  |    HOST\_IP   |  varchar |  128 |  0  |   N  |  Y  |     |    主机ip    |
|  3  |     REMARK    |  varchar | 1024 |  0  |   Y  |  N  |     |     评论     |
|  4  | CREATED\_TIME | datetime |  19  |  0  |   N  |  N  |     |    创建时间    |
|  5  | UPDATED\_TIME | datetime |  19  |  0  |   N  |  N  |     |    更新时间    |
|  6  |      TYPE     |    int   |  10  |  0  |   N  |  N  |  0  |     类型     |
|  7  |   ROUTE\_KEY  |  varchar |  45  |  0  |   Y  |  N  |     | 消息队列的路由KEY |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_HOST\_ZONE

**说明：**

**数据列：**

|  序号 |       名称      |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |     说明     |
| :-: | :-----------: | :------: | :--: | :-: | :--: | :-: | :-: | :--------: |
|  1  |    HOST\_IP   |  varchar |  128 |  0  |   N  |  Y  |     |    主机ip    |
|  2  |      ZONE     |  varchar |  128 |  0  |   N  |  N  |     |    构建机地域   |
|  3  |     ENABLE    |    bit   |   1  |  0  |   Y  |  N  |  1  |    是否启用    |
|  4  |     REMARK    |  varchar | 1024 |  0  |   Y  |  N  |     |     评论     |
|  5  | CREATED\_TIME | datetime |  19  |  0  |   N  |  N  |     |    创建时间    |
|  6  | UPDATED\_TIME | datetime |  19  |  0  |   N  |  N  |     |    更新时间    |
|  7  |      TYPE     |    int   |  10  |  0  |   N  |  N  |  0  |     类型     |
|  8  |   ROUTE\_KEY  |  varchar |  45  |  0  |   Y  |  N  |     | 消息队列的路由KEY |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_IP\_INFO

**说明：** DOCKER构建机负载表

**数据列：**

|  序号 |         名称         |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |      说明      |
| :-: | :----------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :----------: |
|  1  |         ID         |  bigint  |  20 |  0  |   N  |  Y  |                    |      主键      |
|  2  |     DOCKER\_IP     |  varchar |  64 |  0  |   N  |  N  |                    |   DOCKERIP   |
|  3  | DOCKER\_HOST\_PORT |    int   |  10 |  0  |   N  |  N  |         80         |  DOCKERPORT  |
|  4  |      CAPACITY      |    int   |  10 |  0  |   N  |  N  |          0         |    节点容器总容量   |
|  5  |      USED\_NUM     |    int   |  10 |  0  |   N  |  N  |          0         |   节点容器已使用容量  |
|  6  |      CPU\_LOAD     |    int   |  10 |  0  |   N  |  N  |          0         |   节点容器CPU负载  |
|  7  |      MEM\_LOAD     |    int   |  10 |  0  |   N  |  N  |          0         |   节点容器MEM负载  |
|  8  |     DISK\_LOAD     |    int   |  10 |  0  |   N  |  N  |          0         |  节点容器DISK负载  |
|  9  |   DISK\_IO\_LOAD   |    int   |  10 |  0  |   N  |  N  |          0         | 节点容器DISKIO负载 |
|  10 |       ENABLE       |    bit   |  1  |  0  |   Y  |  N  |        b'0'        |    节点是否可用    |
|  11 |     SPECIAL\_ON    |    bit   |  1  |  0  |   Y  |  N  |        b'0'        |   节点是否作为专用机  |
|  12 |      GRAY\_ENV     |    bit   |  1  |  0  |   Y  |  N  |        b'0'        |    是否为灰度节点   |
|  13 |    CLUSTER\_NAME   |  varchar |  64 |  0  |   Y  |  N  |       COMMON       |    构建集群类型    |
|  14 |     GMT\_CREATE    | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |     创建时间     |
|  15 |    GMT\_MODIFIED   | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |     修改时间     |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_POOL

**说明：** DOCKER并发构建池状态表

**数据列：**

|  序号 |       名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |   说明  |
| :-: | :-----------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :---: |
|  1  |       ID      |  bigint  |  20 |  0  |   N  |  Y  |                    |   主键  |
|  2  |  PIPELINE\_ID |  varchar |  64 |  0  |   N  |  N  |                    | 流水线ID |
|  3  |    VM\_SEQ    |  varchar |  64 |  0  |   N  |  N  |                    | 构建机序号 |
|  4  |    POOL\_NO   |    int   |  10 |  0  |   N  |  N  |          0         | 构建池序号 |
|  5  |     STATUS    |    int   |  10 |  0  |   N  |  N  |          0         | 构建池状态 |
|  6  |  GMT\_CREATE  | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |  创建时间 |
|  7  | GMT\_MODIFIED | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |  修改时间 |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_TASK

**说明：**

**数据列：**

|  序号 |          名称         |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 | 默认值 |       说明       |
| :-: | :-----------------: | :------: | :--: | :-: | :--: | :-: | :-: | :------------: |
|  1  |          ID         |  bigint  |  20  |  0  |   N  |  Y  |     |      主键ID      |
|  2  |     PROJECT\_ID     |  varchar |  64  |  0  |   N  |  N  |     |      项目ID      |
|  3  |      AGENT\_ID      |  varchar |  32  |  0  |   N  |  N  |     |      构建机ID     |
|  4  |     PIPELINE\_ID    |  varchar |  34  |  0  |   N  |  N  |     |      流水线ID     |
|  5  |      BUILD\_ID      |  varchar |  34  |  0  |   N  |  N  |     |      构建ID      |
|  6  |     VM\_SEQ\_ID     |    int   |  10  |  0  |   N  |  N  |     |      构建序列号     |
|  7  |        STATUS       |    int   |  10  |  0  |   N  |  N  |     |       状态       |
|  8  |     SECRET\_KEY     |  varchar |  128 |  0  |   N  |  N  |     |       密钥       |
|  9  |     IMAGE\_NAME     |  varchar | 1024 |  0  |   N  |  N  |     |      镜像名称      |
|  10 |    CHANNEL\_CODE    |  varchar |  128 |  0  |   Y  |  N  |     |    渠道号，默认为DS   |
|  11 |      HOST\_TAG      |  varchar |  128 |  0  |   Y  |  N  |     |      主机标签      |
|  12 |    CONTAINER\_ID    |  varchar |  128 |  0  |   Y  |  N  |     |     构建容器ID     |
|  13 |    CREATED\_TIME    | datetime |  19  |  0  |   N  |  N  |     |      创建时间      |
|  14 |    UPDATED\_TIME    | datetime |  19  |  0  |   N  |  N  |     |      更新时间      |
|  15 |         ZONE        |  varchar |  128 |  0  |   Y  |  N  |     |      构建机地域     |
|  16 |    REGISTRY\_USER   |  varchar |  128 |  0  |   Y  |  N  |     |      注册用户名     |
|  17 |    REGISTRY\_PWD    |  varchar |  128 |  0  |   Y  |  N  |     |     注册用户密码     |
|  18 |     IMAGE\_TYPE     |  varchar |  128 |  0  |   Y  |  N  |     |      镜像类型      |
|  19 | CONTAINER\_HASH\_ID |  varchar |  128 |  0  |   Y  |  N  |     |    构建Job唯一标识   |
|  20 | IMAGE\_PUBLIC\_FLAG |    bit   |   1  |  0  |   Y  |  N  |     | 镜像是否为公共镜像：0否1是 |
|  21 |   IMAGE\_RD\_TYPE   |    bit   |   1  |  0  |   Y  |  N  |     | 镜像研发来源：0自研1第三方 |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_DRIFT

**说明：** DOCKER构建任务漂移记录表

**数据列：**

|  序号 |           名称          |   数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |    说明   |
| :-: | :-------------------: | :------: | :--: | :-: | :--: | :-: | :----------------: | :-----: |
|  1  |           ID          |  bigint  |  20  |  0  |   N  |  Y  |                    |    主键   |
|  2  |      PIPELINE\_ID     |  varchar |  64  |  0  |   N  |  N  |                    |  流水线ID  |
|  3  |       BUILD\_ID       |  varchar |  64  |  0  |   N  |  N  |                    |   构建ID  |
|  4  |        VM\_SEQ        |  varchar |  64  |  0  |   N  |  N  |                    |  构建机序号  |
|  5  |    OLD\_DOCKER\_IP    |  varchar |  64  |  0  |   N  |  N  |                    | 旧构建容器IP |
|  6  |    NEW\_DOCKER\_IP    |  varchar |  64  |  0  |   N  |  N  |                    | 新构建容器IP |
|  7  | OLD\_DOCKER\_IP\_INFO |  varchar | 1024 |  0  |   N  |  N  |                    | 旧容器IP负载 |
|  8  |      GMT\_CREATE      | datetime |  19  |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |   创建时间  |
|  9  |     GMT\_MODIFIED     | datetime |  19  |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |   修改时间  |

**表名：** T\_DISPATCH\_PIPELINE\_DOCKER\_TASK\_SIMPLE

**说明：** DOCKER构建任务表

**数据列：**

|  序号 |            名称            |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |   说明   |
| :-: | :----------------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :----: |
|  1  |            ID            |  bigint  |  20 |  0  |   N  |  Y  |                    |   主键   |
|  2  |       PIPELINE\_ID       |  varchar |  64 |  0  |   N  |  N  |                    |  流水线ID |
|  3  |          VM\_SEQ         |  varchar |  64 |  0  |   N  |  N  |                    |  构建机序号 |
|  4  |        DOCKER\_IP        |  varchar |  64 |  0  |   N  |  N  |                    | 构建容器IP |
|  5  | DOCKER\_RESOURCE\_OPTION |    int   |  10 |  0  |   N  |  N  |          0         | 构建资源配置 |
|  6  |        GMT\_CREATE       | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |  创建时间  |
|  7  |       GMT\_MODIFIED      | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |  修改时间  |

**表名：** T\_DISPATCH\_PROJECT\_RUN\_TIME

**说明：** 项目当月已使用额度

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |  说明  |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :--: |
|  1  |  PROJECT\_ID |  varchar | 128 |  0  |   N  |  Y  |     | 项目ID |
|  2  |   VM\_TYPE   |  varchar | 128 |  0  |   N  |  Y  |     | VM类型 |
|  3  |   RUN\_TIME  |  bigint  |  20 |  0  |   N  |  N  |     | 运行时长 |
|  4  | UPDATE\_TIME | datetime |  19 |  0  |   N  |  N  |     | 更新时间 |

**表名：** T\_DISPATCH\_QUOTA\_JOB\_SYSTEM

**说明：** 流水线JOB配额系统表

**数据列：**

|  序号 |                 名称                |    数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |             说明            |
| :-: | :-------------------------------: | :-------: | :-: | :-: | :--: | :-: | :----------------: | :-----------------------: |
|  1  |                 ID                |   bigint  |  20 |  0  |   N  |  Y  |                    |            自增ID           |
|  2  |              VM\_TYPE             |  varchar  |  64 |  0  |   N  |  N  |                    |           构建机类型           |
|  3  |           CHANNEL\_CODE           |  varchar  | 128 |  0  |   N  |  N  |                    | 构建来源，包含：BS,CODECC,AM,GIT等 |
|  4  |     RUNNING\_JOBS\_MAX\_SYSTEM    |    int    |  10 |  0  |   N  |  N  |        1000        |         系统最大并发JOB数        |
|  5  |    RUNNING\_JOBS\_MAX\_PROJECT    |    int    |  10 |  0  |   N  |  N  |         100        |       单项目默认最大并发JOB数       |
|  6  |      RUNNING\_TIME\_JOB\_MAX      |    int    |  10 |  0  |   N  |  N  |         24         |     系统默认所有单个JOB最大执行时间     |
|  7  |  RUNNING\_TIME\_JOB\_MAX\_PROJECT |    int    |  10 |  0  |   N  |  N  |        1000        |      默认单项目所有JOB最大执行时间     |
|  8  |  PROJECT\_RUNNING\_JOB\_THRESHOLD |    int    |  10 |  0  |   N  |  N  |         80         |       项目执行job数量告警阈值       |
|  9  | PROJECT\_RUNNING\_TIME\_THRESHOLD |    int    |  10 |  0  |   N  |  N  |         80         |       项目执行job时间告警阈值       |
|  10 |  SYSTEM\_RUNNING\_JOB\_THRESHOLD  |    int    |  10 |  0  |   N  |  N  |         80         |       系统执行job数量告警阈值       |
|  11 |              OPERATOR             |  varchar  | 128 |  0  |   N  |  N  |                    |            操作人            |
|  12 |            CREATE\_TIME           | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |            创建时间           |
|  13 |            UPDATE\_TIME           | timestamp |  19 |  0  |   N  |  N  | CURRENT\_TIMESTAMP |            修改时间           |

**表名：** T\_DISPATCH\_QUOTA\_PROJECT

**说明：** 项目配额

**数据列：**

|  序号 |              名称             |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |             说明            |
| :-: | :-------------------------: | :------: | :-: | :-: | :--: | :-: | :-: | :-----------------------: |
|  1  |         PROJECT\_ID         |  varchar | 128 |  0  |   N  |  Y  |     |            项目ID           |
|  2  |           VM\_TYPE          |  varchar | 128 |  0  |   N  |  Y  |     |            VM类型           |
|  3  |        CHANNEL\_CODE        |  varchar | 128 |  0  |   N  |  Y  |  BS | 构建来源，包含：BS,CODECC,AM,GIT等 |
|  4  |      RUNNING\_JOBS\_MAX     |    int   |  10 |  0  |   N  |  N  |     |         项目最大并发JOB数        |
|  5  |   RUNNING\_TIME\_JOB\_MAX   |    int   |  10 |  0  |   N  |  N  |     |        项目单JOB最大执行时间       |
|  6  | RUNNING\_TIME\_PROJECT\_MAX |    int   |  10 |  0  |   N  |  N  |     |       项目所有JOB最大执行时间       |
|  7  |        CREATED\_TIME        | datetime |  19 |  0  |   N  |  N  |     |            创建时间           |
|  8  |        UPDATED\_TIME        | datetime |  19 |  0  |   N  |  N  |     |            更新时间           |
|  9  |           OPERATOR          |  varchar | 128 |  0  |   N  |  N  |     |            操作人            |

**表名：** T\_DISPATCH\_QUOTA\_SYSTEM

**说明：** 系统配额

**数据列：**

|  序号 |                    名称                   |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |         说明        |
| :-: | :-------------------------------------: | :------: | :-: | :-: | :--: | :-: | :-: | :---------------: |
|  1  |                 VM\_TYPE                |  varchar | 128 |  0  |   N  |  Y  |     |       构建机类型       |
|  2  |        RUNNING\_JOBS\_MAX\_SYSTEM       |    int   |  10 |  0  |   N  |  N  |     |    蓝盾系统最大并发JOB数   |
|  3  |       RUNNING\_JOBS\_MAX\_PROJECT       |    int   |  10 |  0  |   N  |  N  |     |   单项目默认最大并发JOB数   |
|  4  |         RUNNING\_TIME\_JOB\_MAX         |    int   |  10 |  0  |   N  |  N  |     | 系统默认所有单个JOB最大执行时间 |
|  5  |     RUNNING\_TIME\_JOB\_MAX\_PROJECT    |    int   |  10 |  0  |   N  |  N  |     |  默认单项目所有JOB最大执行时间 |
|  6  |    RUNNING\_JOBS\_MAX\_GITCI\_SYSTEM    |    int   |  10 |  0  |   N  |  N  |     |  工蜂CI系统总最大并发JOB数量 |
|  7  |    RUNNING\_JOBS\_MAX\_GITCI\_PROJECT   |    int   |  10 |  0  |   N  |  N  |     |  工蜂CI单项目最大并发JOB数量 |
|  8  |      RUNNING\_TIME\_JOB\_MAX\_GITCI     |    int   |  10 |  0  |   N  |  N  |     |   工蜂CI单JOB最大执行时间  |
|  9  | RUNNING\_TIME\_JOB\_MAX\_PROJECT\_GITCI |    int   |  10 |  0  |   N  |  N  |     |   工蜂CI单项目最大执行时间   |
|  10 |     PROJECT\_RUNNING\_JOB\_THRESHOLD    |    int   |  10 |  0  |   N  |  N  |     |   项目执行job数量告警阈值   |
|  11 |    PROJECT\_RUNNING\_TIME\_THRESHOLD    |    int   |  10 |  0  |   N  |  N  |     |   项目执行job时间告警阈值   |
|  12 |     SYSTEM\_RUNNING\_JOB\_THRESHOLD     |    int   |  10 |  0  |   N  |  N  |     |   系统执行job数量告警阈值   |
|  13 |              CREATED\_TIME              | datetime |  19 |  0  |   N  |  N  |     |        创建时间       |
|  14 |              UPDATED\_TIME              | datetime |  19 |  0  |   N  |  N  |     |        更新时间       |
|  15 |                 OPERATOR                |  varchar | 128 |  0  |   N  |  N  |     |        操作人        |

**表名：** T\_DISPATCH\_RUNNING\_JOBS

**说明：** 运行中的JOB

**数据列：**

|  序号 |         名称         |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |             说明            |
| :-: | :----------------: | :------: | :-: | :-: | :--: | :-: | :-: | :-----------------------: |
|  1  |         ID         |    int   |  10 |  0  |   N  |  Y  |     |            主键ID           |
|  2  |     PROJECT\_ID    |  varchar | 128 |  0  |   N  |  N  |     |            项目ID           |
|  3  |      VM\_TYPE      |  varchar | 128 |  0  |   N  |  N  |     |            VM类型           |
|  4  |    CHANNEL\_CODE   |  varchar | 128 |  0  |   N  |  N  |  BS | 构建来源，包含：BS,CODECC,AM,GIT等 |
|  5  |      BUILD\_ID     |  varchar | 128 |  0  |   N  |  N  |     |            构建ID           |
|  6  |     VM\_SEQ\_ID    |  varchar | 128 |  0  |   N  |  N  |     |           构建序列号           |
|  7  |   EXECUTE\_COUNT   |    int   |  10 |  0  |   N  |  N  |     |            执行次数           |
|  8  |    CREATED\_TIME   | datetime |  19 |  0  |   N  |  N  |     |            创建时间           |
|  9  | AGENT\_START\_TIME | datetime |  19 |  0  |   Y  |  N  |     |          构建机启动时间          |

**表名：** T\_DISPATCH\_THIRDPARTY\_AGENT\_BUILD

**说明：**

**数据列：**

|  序号 |          名称         |   数据类型   |     长度     | 小数位 | 允许空值 |  主键 | 默认值 |        说明        |
| :-: | :-----------------: | :------: | :--------: | :-: | :--: | :-: | :-: | :--------------: |
|  1  |          ID         |  bigint  |     20     |  0  |   N  |  Y  |     |       主键ID       |
|  2  |     PROJECT\_ID     |  varchar |     64     |  0  |   N  |  N  |     |       项目ID       |
|  3  |      AGENT\_ID      |  varchar |     32     |  0  |   N  |  N  |     |       构建机ID      |
|  4  |     PIPELINE\_ID    |  varchar |     34     |  0  |   N  |  N  |     |       流水线ID      |
|  5  |      BUILD\_ID      |  varchar |     34     |  0  |   N  |  N  |     |       构建ID       |
|  6  |     VM\_SEQ\_ID     |  varchar |     34     |  0  |   N  |  N  |     |       构建序列号      |
|  7  |        STATUS       |    int   |     10     |  0  |   N  |  N  |     |        状态        |
|  8  |    CREATED\_TIME    | datetime |     19     |  0  |   N  |  N  |     |       创建时间       |
|  9  |    UPDATED\_TIME    | datetime |     19     |  0  |   N  |  N  |     |       更新时间       |
|  10 |      WORKSPACE      |  varchar |    4096    |  0  |   Y  |  N  |     |       工作空间       |
|  11 |      BUILD\_NUM     |    int   |     10     |  0  |   Y  |  N  |  0  |       构建次数       |
|  12 |    PIPELINE\_NAME   |  varchar |     255    |  0  |   Y  |  N  |     |       流水线名称      |
|  13 |      TASK\_NAME     |  varchar |     255    |  0  |   Y  |  N  |     |       任务名称       |
|  14 |      AGENT\_IP      |  varchar |     128    |  0  |   Y  |  N  |     |       节点IP       |
|  15 |       NODE\_ID      |  bigint  |     20     |  0  |   Y  |  N  |  0  |  第三方构建机NODE\_ID  |
|  16 |     DOCKER\_INFO    |   json   | 1073741824 |  0  |   Y  |  N  |     | 第三方构建机docker构建信息 |
|  17 |    EXECUTE\_COUNT   |    int   |     10     |  0  |   Y  |  N  |     |      流水线执行次数     |
|  18 | CONTAINER\_HASH\_ID |  varchar |     128    |  0  |   Y  |  N  |     |     容器ID日志使用     |

**表名：** T\_DISPATCH\_THIRDPARTY\_AGENT\_DOCKER\_DEBUG

**说明：** 第三方构建机Docker登录调试

**数据列：**

|  序号 |       名称      |   数据类型   |     长度     | 小数位 | 允许空值 |  主键 | 默认值 |        说明        |
| :-: | :-----------: | :------: | :--------: | :-: | :--: | :-: | :-: | :--------------: |
|  1  |       ID      |  bigint  |     20     |  0  |   N  |  Y  |     |       主键ID       |
|  2  |   AGENT\_ID   |  varchar |     32     |  0  |   N  |  N  |     |       构建机ID      |
|  3  |  PROJECT\_ID  |  varchar |     64     |  0  |   N  |  N  |     |       项目ID       |
|  4  |  PIPELINE\_ID |  varchar |     34     |  0  |   N  |  N  |     |       流水线ID      |
|  5  |   BUILD\_ID   |  varchar |     34     |  0  |   N  |  N  |     |       构建ID       |
|  6  |  VM\_SEQ\_ID  |  varchar |     34     |  0  |   N  |  N  |     |       构建序列号      |
|  7  |    USER\_ID   |  varchar |     34     |  0  |   N  |  N  |     |       调试用户       |
|  8  |     STATUS    |    int   |     10     |  0  |   N  |  N  |     |        状态        |
|  9  | CREATED\_TIME | datetime |     19     |  0  |   N  |  N  |     |       创建时间       |
|  10 | UPDATED\_TIME | datetime |     19     |  0  |   N  |  N  |     |       修改时间       |
|  11 |   WORKSPACE   |  varchar |    4096    |  0  |   Y  |  N  |     |       工作空间       |
|  12 |  DOCKER\_INFO |   json   | 1073741824 |  0  |   Y  |  N  |     | 第三方构建机docker构建信息 |
|  13 |    ERR\_MSG   |   text   |    65535   |  0  |   Y  |  N  |     |    启动构建时的错误信息    |
|  14 |   DEBUG\_URL  |  varchar |    4096    |  0  |   Y  |  N  |     |      debug链接     |

**表名：** T\_DOCKER\_RESOURCE\_OPTIONS

**说明：** docker基础配额表

**数据列：**

|  序号 |             名称            |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 |         默认值        |       说明      |
| :-: | :-----------------------: | :------: | :-: | :-: | :--: | :-: | :----------------: | :-----------: |
|  1  |             ID            |  bigint  |  20 |  0  |   N  |  Y  |                    |       主键      |
|  2  |        CPU\_PERIOD        |    int   |  10 |  0  |   N  |  N  |        10000       |     CPU配置     |
|  3  |         CPU\_QUOTA        |    int   |  10 |  0  |   N  |  N  |       160000       |     CPU配置     |
|  4  |    MEMORY\_LIMIT\_BYTES   |  bigint  |  20 |  0  |   N  |  N  |     34359738368    |     内存：32G    |
|  5  |            DISK           |    int   |  10 |  0  |   N  |  N  |         100        |    磁盘：100G    |
|  6  | BLKIO\_DEVICE\_WRITE\_BPS |  bigint  |  20 |  0  |   N  |  N  |      125829120     | 磁盘写入速率，120m/s |
|  7  |  BLKIO\_DEVICE\_READ\_BPS |  bigint  |  20 |  0  |   N  |  N  |      125829120     | 磁盘读入速率，120m/s |
|  8  |        DESCRIPTION        |  varchar | 128 |  0  |   N  |  N  |                    |       描述      |
|  9  |        GMT\_CREATE        | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |      创建时间     |
|  10 |       GMT\_MODIFIED       | datetime |  19 |  0  |   Y  |  N  | CURRENT\_TIMESTAMP |      修改时间     |
