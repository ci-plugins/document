# devops\_ci\_plugin

**数据库名：** devops\_ci\_plugin

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_plugin的数据库文档

|                                     表名                                     |  说明 |
| :------------------------------------------------------------------------: | :-: |
| [T\_PLUGIN\_GITHUB\_CHECK](devops\_ci\_plugin.md#T\_PLUGIN\_GITHUB\_CHECK) |     |
|    [T\_PLUGIN\_GIT\_CHECK](devops\_ci\_plugin.md#T\_PLUGIN\_GIT\_CHECK)    |     |

**表名：** T\_PLUGIN\_GITHUB\_CHECK

**说明：**

**数据列：**

|  序号 |        名称        |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :--------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |        ID        |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |   PIPELINE\_ID   |  varchar |  64 |  0  |   N  |  N  |     |  流水线ID |
|  3  |   BUILD\_NUMBER  |    int   |  10 |  0  |   N  |  N  |     |  构建编号  |
|  4  |     REPO\_ID     |  varchar |  64 |  0  |   Y  |  N  |     |  代码库ID |
|  5  |    COMMIT\_ID    |  varchar |  64 |  0  |   N  |  N  |     | 代码提交ID |
|  6  |  CHECK\_RUN\_ID  |  bigint  |  20 |  0  |   N  |  N  |     |        |
|  7  |   CREATE\_TIME   | datetime |  19 |  0  |   N  |  N  |     |  创建时间  |
|  8  |   UPDATE\_TIME   | datetime |  19 |  0  |   N  |  N  |     |  更新时间  |
|  9  |    REPO\_NAME    |  varchar | 128 |  0  |   Y  |  N  |     |  代码库别名 |
|  10 | CHECK\_RUN\_NAME |  varchar |  64 |  0  |   Y  |  N  |     |        |

**表名：** T\_PLUGIN\_GIT\_CHECK

**说明：**

**数据列：**

|  序号 |       名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |   说明   |
| :-: | :------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----: |
|  1  |       ID       |  bigint  |  20 |  0  |   N  |  Y  |     |  主键ID  |
|  2  |  PIPELINE\_ID  |  varchar |  64 |  0  |   N  |  N  |     |  流水线ID |
|  3  |  BUILD\_NUMBER |    int   |  10 |  0  |   N  |  N  |     |  构建编号  |
|  4  |    REPO\_ID    |  varchar |  64 |  0  |   Y  |  N  |     |  代码库ID |
|  5  |   COMMIT\_ID   |  varchar |  64 |  0  |   N  |  N  |     | 代码提交ID |
|  6  |  CREATE\_TIME  | datetime |  19 |  0  |   N  |  N  |     |  创建时间  |
|  7  |  UPDATE\_TIME  | datetime |  19 |  0  |   N  |  N  |     |  更新时间  |
|  8  |   REPO\_NAME   |  varchar | 128 |  0  |   Y  |  N  |     |  代码库别名 |
|  9  |     CONTEXT    |  varchar | 255 |  0  |   Y  |  N  |     |   内容   |
|  10 | TARGET\_BRANCH |  varchar | 255 |  0  |   Y  |  N  |     |  目标分支  |
