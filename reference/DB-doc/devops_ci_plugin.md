# devops_ci_plugin

**Database name:** devops_ci_plugin

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_plugin

|                 Table name                  | description |
| :-----------------------------------------: | :---------: |
|     [T_PLUGIN_CODECC](broken-reference)     |             |
| [T_PLUGIN_CODECC_ELEMENT](broken-reference) |             |
|  [T_PLUGIN_GITHUB_CHECK](broken-reference)  |             |
|   [T_PLUGIN_GIT_CHECK](broken-reference)    |             |

**Table name:** T_PLUGIN_CODECC

**Explanation:**

**Data column:**

| Serial number |        name        | Data type |   length   | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :----------------: | :-------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |         ID         |  bigint   |     20     |       0       |          N           |      Y      |               | Primary key ID |
|       2       |     PROJECT_ID     |  varchar  |     64     |       0       |          Y           |      N      |               |    Item ID     |
|       3       |    PIPELINE_ID     |  varchar  |     34     |       0       |          Y           |      N      |               |  Pipeline ID   |
|       4       |      BUILD_ID      |  varchar  |     34     |       0       |          Y           |      N      |               |    Build ID    |
|       5       |      TASK_ID       |  varchar  |     34     |       0       |          Y           |      N      |               |    Task ID     |
|       6       | TOOL_SNAPSHOT_LIST | longtext  | 2147483647 |       0       |          Y           |      N      |               |                |

**Table name:** T_PLUGIN_CODECC_ELEMENT

**Explanation:**

**Data column:**

| Serial number |      name      | Data type |   length   | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :------------: | :-------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       ID       |  bigint   |     20     |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |   PROJECT_ID   |  varchar  |    128     |       0       |          Y           |      N      |               |                           Item ID                            |
|       3       |  PIPELINE_ID   |  varchar  |     34     |       0       |          Y           |      N      |               |                         Pipeline ID                          |
|       4       |   TASK_NAME    |  varchar  |    256     |       0       |          Y           |      N      |               |                          Task name                           |
|       5       |  TASK_CN_NAME  |  varchar  |    256     |       0       |          Y           |      N      |               |                      Task Chinese name                       |
|       6       |    TASK_ID     |  varchar  |    128     |       0       |          Y           |      N      |               |                           Task ID                            |
|       7       |    IS_SYNC     |  varchar  |     6      |       0       |          Y           |      N      |               |                      Synchronous or not                      |
|       8       |   SCAN_TYPE    |  varchar  |     6      |       0       |          Y           |      N      |               |              Scan type (0: full,1: incremental)              |
|       9       |    LANGUAGE    |  varchar  |    1024    |       0       |          Y           |      N      |               |                     Engineering language                     |
|      10       |    PLATFORM    |  varchar  |     16     |       0       |          Y           |      N      |               | codecc atomic execution environment, such as WINDOWS, LINUX, MACOS, etc |
|      11       |     TOOLS      |  varchar  |    1024    |       0       |          Y           |      N      |               |                        Scanning tool                         |
|      12       |   PY_VERSION   |  varchar  |     16     |       0       |          Y           |      N      |               | py2 indicates that python2 is used, and py3 indicates that python3 is used |
|      13       |   ESLINT_RC    |  varchar  |     16     |       0       |          Y           |      N      |               |                     js project framework                     |
|      14       |   CODE_PATH    | longtext  | 2147483647 |       0       |          Y           |      N      |               |                      Code storage path                       |
|      15       |  SCRIPT_TYPE   |  varchar  |     16     |       0       |          Y           |      N      |               |                         Script type                          |
|      16       |     SCRIPT     | longtext  | 2147483647 |       0       |          Y           |      N      |               |                        Package script                        |
|      17       |  CHANNEL_CODE  |  varchar  |     16     |       0       |          Y           |      N      |               |           Channel number. The default value is DS            |
|      18       | UPDATE_USER_ID |  varchar  |    128     |       0       |          Y           |      N      |               |                       Updated user id                        |
|      19       |   IS_DELETE    |  varchar  |     6      |       0       |          Y           |      N      |               |           Whether to delete 0 can be deleted by 1            |
|      20       |  UPDATE_TIME   | datetime  |     19     |       0       |          Y           |      N      |               |                         Update time                          |

**Table name:** T_PLUGIN_GITHUB_CHECK

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |               |   Primary key ID   |
|       2       |  PIPELINE_ID   |  varchar  |   64   |       0       |          N           |      N      |               |    Pipeline ID     |
|       3       |  BUILD_NUMBER  |    int    |   10   |       0       |          N           |      N      |               |    Build number    |
|       4       |    REPO_ID     |  varchar  |   64   |       0       |          Y           |      N      |               |    Code base ID    |
|       5       |   COMMIT_ID    |  varchar  |   64   |       0       |          N           |      N      |               | Code submission ID |
|       6       |  CHECK_RUN_ID  |  bigint   |   20   |       0       |          N           |      N      |               |                    |
|       7       |  CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      |               |   Creation time    |
|       8       |  UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      |               |    Update time     |
|       9       |   REPO_NAME    |  varchar  |  128   |       0       |          Y           |      N      |               |  Code base alias   |
|      10       | CHECK_RUN_NAME |  varchar  |   64   |       0       |          Y           |      N      |               |                    |

**Table name:** T_PLUGIN_GIT_CHECK

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |   Primary key ID   |
|       2       | PIPELINE_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Pipeline ID     |
|       3       | BUILD_NUMBER |    int    |   10   |       0       |          N           |      N      |               |    Build number    |
|       4       |   REPO_ID    |  varchar  |   64   |       0       |          Y           |      N      |               |    Code base ID    |
|       5       |  COMMIT_ID   |  varchar  |   64   |       0       |          N           |      N      |               | Code submission ID |
|       6       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |   Creation time    |
|       7       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |    Update time     |
|       8       |  REPO_NAME   |  varchar  |  128   |       0       |          Y           |      N      |               |  Code base alias   |
|       9       |   CONTEXT    |  varchar  |  255   |       0       |          Y           |      N      |               |      content       |
