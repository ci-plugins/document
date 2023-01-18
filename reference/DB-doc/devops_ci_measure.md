# devops_ci_measure

**Database name:** devops_ci_measure

**Issue:** 1.0.0

**Documentation description:** Database documentation for devops_ci_measure

|                  Table name                  | description |
| :------------------------------------------: | :---------: |
| [T_MEASURE_BUILD_ELEMENT](broken-reference)  |             |
| [T_MEASURE_DASHBOARD_VIEW](broken-reference) |             |
| [T_MEASURE_PIPELINE_BUILD](broken-reference) |             |
|    [T_MEASURE_PROJECT](broken-reference)     |             |
|  [T_MEASURE_WETEST_INFO](broken-reference)   |             |

**Table name:** T_MEASURE_BUILD_ELEMENT

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |            description             |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------------------: |
|       1       | elementName |  varchar  |   64   |       0       |          N           |      N      |               |            Element name            |
|       2       | pipelineId  |  varchar  |   34   |       0       |          N           |      N      |               |            Pipeline ID             |
|       3       |   buildId   |  varchar  |   34   |       0       |          N           |      N      |               |              Build ID              |
|       4       |   status    |  varchar  |   32   |       0       |          N           |      N      |               |               state                |
|       5       |  beginTime  | datetime  |   19   |       0       |          N           |      N      |               |             Start time             |
|       6       |   endTime   | datetime  |   19   |       0       |          N           |      N      |               |              End time              |
|       7       |  projectId  |  varchar  |   32   |       0       |          N           |      N      |               |              Item ID               |
|       8       |    extra    |   text    | 65535  |       0       |          Y           |      N      |               |       Additional information       |
|       9       |    type     |  varchar  |   32   |       0       |          N           |      N      |               |                type                |
|      10       |  elementId  |  varchar  |   64   |       0       |          N           |      N      |               |         elementId plug-in          |
|      11       |     id      |    int    |   10   |       0       |          N           |      Y      |               |           Primary key ID           |
|      12       |  atomCode   |  varchar  |  128   |       0       |          N           |      N      |               | The unique identity of the plug-in |

**Table name:** T_MEASURE_DASHBOARD_VIEW

**Explanation:**

**Data column:**

| Serial number |    name    | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :--------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |     id     |    int     |    10    |       0       |          N           |      Y      |               |   Primary key ID   |
|       2       | projectId  |  varchar   |    36    |       0       |          N           |      N      |               |      Item ID       |
|       3       |    user    |  varchar   |    32    |       0       |          N           |      N      |               |        user        |
|       4       |    NAME    |  varchar   |    64    |       0       |          N           |      N      |               |        name        |
|       5       | viewConfig | mediumtext | 16777215 |       0       |          N           |      N      |               | View configuration |
|       6       |  viewType  |  varchar   |    32    |       0       |          N           |      N      |    SINGLE     |     View type      |

**Table name:** T_MEASURE_PIPELINE_BUILD

**Explanation:**

**Data column:**

| Serial number |       name       | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |              description               |
| :-----------: | :--------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :------------------------------------: |
|       1       |    pipelineId    |  varchar   |    34    |       0       |          N           |      N      |               |              Pipeline ID               |
|       2       |     buildId      |  varchar   |    34    |       0       |          N           |      N      |               |                Build ID                |
|       3       |    beginTime     |  datetime  |    19    |       0       |          N           |      N      |               |    The startup time of the pipeline    |
|       4       |     endTime      |  datetime  |    19    |       0       |          N           |      N      |               |   The end time of the assembly line    |
|       5       |    startType     |  varchar   |    20    |       0       |          N           |      N      |               |      The startup mode of pipeline      |
|       6       |    buildUser     |  varchar   |   255    |       0       |          N           |      N      |               |         Pipelined startup user         |
|       7       |    isParallel    |    bit     |    1     |       0       |          N           |      N      |               |     Whether pipelining is parallel     |
|       8       |   buildResult    |  varchar   |    20    |       0       |          N           |      N      |               |  The result of pipeline construction   |
|       9       |    projectId     |  varchar   |    32    |       0       |          N           |      N      |               |                Item ID                 |
|      10       |     pipeline     | mediumtext | 16777215 |       0       |          N           |      N      |               |                pipeline                |
|      11       |     buildNum     |    int     |    10    |       0       |          N           |      N      |               |          Build version number          |
|      12       |        id        |    int     |    10    |       0       |          N           |      Y      |               |             Primary key ID             |
|      13       |     metaInfo     |    text    |  65535   |       0       |          Y           |      N      |               |                metadata                |
|      14       | parentPipelineId |  varchar   |    34    |       0       |          Y           |      N      |               | Pipeline ID of the initiator pipeline  |
|      15       |  parentBuildId   |  varchar   |    34    |       0       |          Y           |      N      |               | The build ID of the initiator pipeline |

**Table name:** T_MEASURE_PROJECT

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       id        |    int    |   10   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       | approval_status |    int    |   10   |       0       |          Y           |      N      |               |                         Audit status                         |
|       3       |      bg_id      |    int    |   10   |       0       |          Y           |      N      |               |                      Business group ID                       |
|       4       |     bg_name     |  varchar  |  120   |       0       |          Y           |      N      |               |                     Business group name                      |
|       5       |    cc_app_id    |    int    |   10   |       0       |          Y           |      N      |               |                        Application ID                        |
|       6       |    center_id    |    int    |   10   |       0       |          Y           |      N      |               |                          Center ID                           |
|       7       |   center_name   |  varchar  |  120   |       0       |          Y           |      N      |               |                         Central name                         |
|       8       |   created_at    | datetime  |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|       9       |     creator     |  varchar  |   32   |       0       |          Y           |      N      |               |                           founder                            |
|      10       |     data_id     |    int    |   10   |       0       |          Y           |      N      |               |                           Data ID                            |
|      11       |   deploy_type   |  varchar  |  256   |       0       |          Y           |      N      |               |                       Deployment type                        |
|      12       |     dept_id     |    int    |   10   |       0       |          Y           |      N      |               |     The project belongs to the secondary organization ID     |
|      13       |    dept_name    |  varchar  |  120   |       0       |          Y           |      N      |               | Name of the secondary organization to which the project belongs |
|      14       |   description   |   text    | 65535  |       0       |          Y           |      N      |               |                         description                          |
|      15       |  project_code   |  varchar  |  128   |       0       |          Y           |      N      |               |         The project to which the user group belongs          |
|      16       |   is_offlined   |    bit    |   1    |       0       |          Y           |      N      |               |                      Deactivate or not                       |
|      17       |   is_secrecy    |    bit    |   1    |       0       |          Y           |      N      |               |                    Confidentiality or not                    |
|      18       |      kind       |    int    |   10   |       0       |          Y           |      N      |               |                        Container type                        |
|      19       |   project_id    |  varchar  |   64   |       0       |          Y           |      N      |               |                           Item ID                            |
|      20       |  project_name   |  varchar  |  256   |       0       |          Y           |      N      |               |                         Project name                         |
|      21       |  project_type   |    int    |   10   |       0       |          Y           |      N      |               |                          Item type                           |
|      22       |   updated_at    | datetime  |   19   |       0       |          Y           |      N      |               |                         Update time                          |
|      23       |     use_bk      |    bit    |   1    |       0       |          Y           |      N      |               |                 Whether to use a blue whale                  |
|      24       |    logo_addr    |  varchar  |  1024  |       0       |          Y           |      N      |               |                         logo address                         |
|      25       | pipeline_count  |    int    |   10   |       0       |          Y           |      N      |       0       |                      Number of pipeline                      |

**Table name:** T_MEASURE_WETEST_INFO

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |        ID         |  bigint   |   20   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       |   elementKeyId    |    int    |   10   |       0       |          N           |      N      |               |     Element Keyid      |
|       3       |      testid       |  varchar  |   64   |       0       |          Y           |      N      |               |                        |
|       4       |     passrate      |    int    |   10   |       0       |          Y           |      N      |       0       |       Pass rate        |
|       5       |    failManuMap    |   text    | 65535  |       0       |          Y           |      N      |               |                        |
|       6       |  failVersionMap   |   text    | 65535  |       0       |          Y           |      N      |               |   Failed version map   |
|       7       | failResolutionMap |   text    | 65535  |       0       |          Y           |      N      |               | Failure resolution map |
|       8       |    errCodeMap     |   text    | 65535  |       0       |          Y           |      N      |               |     Error code map     |
|       9       |    errLevelMap    |   text    | 65535  |       0       |          Y           |      N      |               |    Error level map     |
|      10       |    createTime     | datetime  |   19   |       0       |          Y           |      N      |               |     Creation time      |
