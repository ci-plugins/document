# devops_ci_quality

**Database name:** devops_ci_quality

**Issue:** 1.0.0

**Documentation Description:** devops_ci_quality database documentation

|                       Table name                       |                 description                 |
| :----------------------------------------------------: | :-----------------------------------------: |
|          [T_CONTROL_POINT](broken-reference)           |                                             |
|      [T_CONTROL_POINT_METADATA](broken-reference)      |                                             |
|        [T_CONTROL_POINT_TASK](broken-reference)        |                                             |
|         [T_COUNT_INTERCEPT](broken-reference)          |                                             |
|          [T_COUNT_PIPELINE](broken-reference)          |                                             |
|            [T_COUNT_RULE](broken-reference)            |                                             |
|              [T_GROUP](broken-reference)               |                                             |
|             [T_HISTORY](broken-reference)              |                                             |
|      [T_QUALITY_CONTROL_POINT](broken-reference)       |    Quality red line control point table     |
|   [T_QUALITY_HIS_DETAIL_METADATA](broken-reference)    | Execution results detailed basic data table |
|   [T_QUALITY_HIS_ORIGIN_METADATA](broken-reference)    |     Execute the result base data table      |
|        [T_QUALITY_INDICATOR](broken-reference)         |      Quality red line indicator table       |
|         [T_QUALITY_METADATA](broken-reference)         |      Quality red line basic data table      |
|           [T_QUALITY_RULE](broken-reference)           |                                             |
|      [T_QUALITY_RULE_BUILD_HIS](broken-reference)      |                                             |
| [T_QUALITY_RULE_BUILD_HIS_OPERATION](broken-reference) |                                             |
|         [T_QUALITY_RULE_MAP](broken-reference)         |                                             |
|      [T_QUALITY_RULE_OPERATION](broken-reference)      |                                             |
|      [T_QUALITY_RULE_TEMPLATE](broken-reference)       |       Quality red line template table       |
|  [T_QUALITY_TEMPLATE_INDICATOR_MAP](broken-reference)  |   Template - Indicator relationship table   |
|               [T_RULE](broken-reference)               |                                             |
|               [T_TASK](broken-reference)               |                                             |

**Table name:** T_CONTROL_POINT

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |               |    Primary key ID     |
|       2       |    NAME     |  varchar  |   64   |       0       |          N           |      N      |               |         name          |
|       3       |  TASK_LIST  |   text    | 65535  |       0       |          N           |      N      |               | Task information list |
|       4       |   ONLINE    |    bit    |   1    |       0       |          N           |      N      |               |     Online or not     |
|       5       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |     Creation time     |
|       6       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |      Update time      |

**Table name:** T_CONTROL_POINT_METADATA

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description  |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------: |
|       1       |  METADATA_ID  |  varchar  |  128   |       0       |          N           |      Y      |               |  Metadata ID  |
|       2       | METADATA_TYPE |  varchar  |   32   |       0       |          N           |      N      |               | Metadata type |
|       3       | METADATA_NAME |   text    | 65535  |       0       |          N           |      N      |               | Metadata name |
|       4       |    TASK_ID    |  varchar  |   64   |       0       |          N           |      N      |               |    Task ID    |
|       5       |    ONLINE     |    bit    |   1    |       0       |          N           |      N      |               | Online or not |
|       6       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               | Creation time |
|       7       |  UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |  Update time  |

**Table name:** T_CONTROL_POINT_TASK

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |      ID       |  varchar  |   64   |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       | CONTROL_STAGE |  varchar  |   32   |       0       |          N           |      N      |               | Atomic control stage |
|       3       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |    Creation time     |
|       4       |  UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |     Update time      |

**Table name:** T_COUNT_INTERCEPT

**Explanation:**

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |         description         |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------: |
|       1       |          ID          |  bigint   |   20   |       0       |          N           |      Y      |               |       Primary key ID        |
|       2       |      PROJECT_ID      |  varchar  |   32   |       0       |          N           |      N      |               |           Item ID           |
|       3       |         DATE         |   date    |   10   |       0       |          N           |      N      |               |            date             |
|       4       |        COUNT         |    int    |   10   |       0       |          N           |      N      |               |            count            |
|       5       |     CREATE_TIME      | datetime  |   19   |       0       |          N           |      N      |               |        Creation time        |
|       6       |     UPDATE_TIME      | datetime  |   19   |       0       |          N           |      N      |               |         Update time         |
|       7       |   INTERCEPT_COUNT    |    int    |   10   |       0       |          N           |      N      |       0       |     Interception number     |
|       8       | RULE_INTERCEPT_COUNT |    int    |   10   |       0       |          N           |      N      |       0       | RULE_INTERCEPT_COUNT+count) |

**Table name:** T_COUNT_PIPELINE

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |         ID          |  bigint   |   20   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       |     PROJECT_ID      |  varchar  |   32   |       0       |          N           |      N      |               |        Item ID         |
|       3       |     PIPELINE_ID     |  varchar  |   34   |       0       |          N           |      N      |               |      Pipeline ID       |
|       4       |        DATE         |   date    |   10   |       0       |          N           |      N      |               |          date          |
|       5       |        COUNT        |    int    |   10   |       0       |          N           |      N      |               |         count          |
|       6       | LAST_INTERCEPT_TIME | datetime  |   19   |       0       |          N           |      N      |               | Last interception time |
|       7       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      |               |     Creation time      |
|       8       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      |               |      Update time       |
|       9       |   INTERCEPT_COUNT   |    int    |   10   |       0       |          N           |      N      |       0       |  Interception number   |

**Table name:** T_COUNT_RULE

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |         ID          |  bigint   |   20   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       |     PROJECT_ID      |  varchar  |   32   |       0       |          N           |      N      |               |        Item ID         |
|       3       |       RULE_ID       |  bigint   |   20   |       0       |          N           |      N      |               |        Rule ID         |
|       4       |        DATE         |   date    |   10   |       0       |          N           |      N      |               |          date          |
|       5       |        COUNT        |    int    |   10   |       0       |          N           |      N      |               |         count          |
|       6       |   INTERCEPT_COUNT   |    int    |   10   |       0       |          N           |      N      |       0       |  Interception number   |
|       7       | LAST_INTERCEPT_TIME | datetime  |   19   |       0       |          N           |      N      |               | Last interception time |
|       8       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      |               |     Creation time      |
|       9       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      |               |      Update time       |

**Table name:** T_GROUP

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |       description        |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------: |
|       1       |        ID         |  bigint   |   20   |       0       |          N           |      Y      |               |      Primary key ID      |
|       2       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |               |         Item ID          |
|       3       |       NAME        |  varchar  |   64   |       0       |          N           |      N      |               |           name           |
|       4       |    INNER_USERS    |   text    | 65535  |       0       |          N           |      N      |               |         insider          |
|       5       | INNER_USERS_COUNT |    int    |   10   |       0       |          N           |      N      |               |      Internal count      |
|       6       |    OUTER_USERS    |   text    | 65535  |       0       |          N           |      N      |               |    External personnel    |
|       7       | OUTER_USERS_COUNT |    int    |   10   |       0       |          N           |      N      |               | External personnel count |
|       8       |      REMARK       |   text    | 65535  |       0       |          Y           |      N      |               |         comment          |
|       9       |      CREATOR      |  varchar  |   64   |       0       |          N           |      N      |               |         founder          |
|      10       |      UPDATOR      |  varchar  |   64   |       0       |          N           |      N      |               |         updater          |
|      11       |    CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      |               |      Creation time       |
|      12       |    UPDATE_TIME    | datetime  |   19   |       0       |          N           |      N      |               |       Update time        |

**Table name:** T_HISTORY

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |   description   |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |                   | Primary key ID  |
|       2       |   PROJECT_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |     Item ID     |
|       3       |    RULE_ID     |  bigint   |   20   |       0       |          N           |      N      |                   |     Rule ID     |
|       4       |  PIPELINE_ID   |  varchar  |   34   |       0       |          N           |      N      |                   |   Pipeline ID   |
|       5       |    BUILD_ID    |  varchar  |   34   |       0       |          N           |      N      |                   |    Build ID     |
|       6       |     RESULT     |  varchar  |   34   |       0       |          N           |      N      |                   |                 |
|       7       | INTERCEPT_LIST |   text    | 65535  |       0       |          N           |      N      |                   | Intercept list  |
|       8       |  CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      |                   |  Creation time  |
|       9       |  UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Update time   |
|      10       |  PROJECT_NUM   |  bigint   |   20   |       0       |          N           |      N      |         0         | Number of items |
|      11       |  CHECK_TIMES   |    int    |   10   |       0       |          Y           |      N      |         1         | How many checks |

**Table name:** T_QUALITY_CONTROL_POINT

Quality red line control point table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |         ID         |  bigint   |   20   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |    ELEMENT_TYPE    |  varchar  |   64   |       0       |          Y           |      N      |               |                  The ClassType of the atom                   |
|       3       |        NAME        |  varchar  |   64   |       0       |          Y           |      N      |               |               Control point name (atomic name)               |
|       4       |       STAGE        |  varchar  |   64   |       0       |          Y           |      N      |               |                          R&d stage                           |
|       5       | AVAILABLE_POSITION |  varchar  |   64   |       0       |          Y           |      N      |               | Support red line position (admittance -BEFORE, permit -AFTER) |
|       6       |  DEFAULT_POSITION  |  varchar  |   64   |       0       |          Y           |      N      |               |                  Default red line position                   |
|       7       |       ENABLE       |    bit    |   1    |       0       |          Y           |      N      |               |                        Enable or not                         |
|       8       |    CREATE_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |                        Create a user                         |
|       9       |    UPDATE_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |                         Update user                          |
|      10       |    CREATE_TIME     | datetime  |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|      11       |    UPDATE_TIME     | datetime  |   19   |       0       |          Y           |      N      |               |                         Update time                          |
|      12       |    ATOM_VERSION    |  varchar  |   16   |       0       |          Y           |      N      |     1.0.0     |                       Plug-in version                        |
|      13       |    TEST_PROJECT    |  varchar  |   64   |       0       |          N           |      N      |               |                          Test item                           |
|      14       |        TAG         |  varchar  |   64   |       0       |          Y           |      N      |               |                                                              |

**Table name:** T_QUALITY_HIS_DETAIL_METADATA

Execution results detailed basic data table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |        description        |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |               |      Primary key ID       |
|       2       |    DATA_ID     |  varchar  |  128   |       0       |          Y           |      N      |               |          Data ID          |
|       3       |   DATA_NAME    |  varchar  |  128   |       0       |          Y           |      N      |               |         Data name         |
|       4       |   DATA_TYPE    |  varchar  |   32   |       0       |          Y           |      N      |               |         Data type         |
|       5       |   DATA_DESC    |  varchar  |  128   |       0       |          Y           |      N      |               |     Data description      |
|       6       |   DATA_VALUE   |  varchar  |  256   |       0       |          Y           |      N      |               |        Data value         |
|       7       |  ELEMENT_TYPE  |  varchar  |   64   |       0       |          Y           |      N      |               | The ClassType of the atom |
|       8       | ELEMENT_DETAIL |  varchar  |   64   |       0       |          Y           |      N      |               |   Tools/Atoms subclass    |
|       9       |   PROJECT_ID   |  varchar  |   64   |       0       |          Y           |      N      |               |          Item ID          |
|      10       |  PIPELINE_ID   |  varchar  |   64   |       0       |          Y           |      N      |               |        Pipeline ID        |
|      11       |    BUILD_ID    |  varchar  |   64   |       0       |          Y           |      N      |               |         Build ID          |
|      12       |    BUILD_NO    |  varchar  |   64   |       0       |          Y           |      N      |               |       Build number        |
|      13       |  CREATE_TIME   |  bigint   |   20   |       0       |          Y           |      N      |               |       Creation time       |
|      14       |     EXTRA      |   text    | 65535  |       0       |          Y           |      N      |               |  Additional information   |

**Table name:** T_QUALITY_HIS_ORIGIN_METADATA

Execution result basic data table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar  |   64   |       0       |          Y           |      N      |               |    Item ID     |
|       3       | PIPELINE_ID |  varchar  |   64   |       0       |          Y           |      N      |               |  Pipeline ID   |
|       4       |  BUILD_ID   |  varchar  |   64   |       0       |          Y           |      N      |               |    Build ID    |
|       5       |  BUILD_NO   |  varchar  |   64   |       0       |          Y           |      N      |               |  Build number  |
|       6       | RESULT_DATA |   text    | 65535  |       0       |          Y           |      N      |               |  Return data   |
|       7       | CREATE_TIME |  bigint   |   20   |       0       |          Y           |      N      |               | Creation time  |

**Table name:** T_QUALITY_INDICATOR

Quality red line index table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                        description                         |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------------------------------------------: |
|       1       |         ID          |  bigint   |   20   |       0       |          N           |      Y      |               |                       Primary key ID                       |
|       2       |    ELEMENT_TYPE     |  varchar  |   32   |       0       |          Y           |      N      |               |                 The ClassType of the atom                  |
|       3       |    ELEMENT_NAME     |  varchar  |   64   |       0       |          Y           |      N      |               |                       Producing atom                       |
|       4       |   ELEMENT_DETAIL    |  varchar  |   64   |       0       |          Y           |      N      |               |                    Tools/Atoms subclass                    |
|       5       |       EN_NAME       |  varchar  |   64   |       0       |          Y           |      N      |               |                         Index name                         |
|       6       |       CN_NAME       |  varchar  |   64   |       0       |          Y           |      N      |               |                     Index Chinese name                     |
|       7       |    METADATA_IDS     |   text    | 65535  |       0       |          Y           |      N      |               |               Indicators contain basic data                |
|       8       |  DEFAULT_OPERATION  |  varchar  |   32   |       0       |          Y           |      N      |               |                     Default operation                      |
|       9       | OPERATION_AVAILABLE |   text    | 65535  |       0       |          Y           |      N      |               |                    Available operation                     |
|      10       |      THRESHOLD      |  varchar  |   64   |       0       |          Y           |      N      |               |                     Default threshold                      |
|      11       |   THRESHOLD_TYPE    |  varchar  |   32   |       0       |          Y           |      N      |               |                       Threshold type                       |
|      12       |        DESC         |  varchar  |  256   |       0       |          Y           |      N      |               |                        description                         |
|      13       | INDICATOR_READ_ONLY |    bit    |   1    |       0       |          Y           |      N      |               |                    Whether to read only                    |
|      14       |        STAGE        |  varchar  |   32   |       0       |          Y           |      N      |               |                           stage                            |
|      15       |   INDICATOR_RANGE   |   text    | 65535  |       0       |          Y           |      N      |               |                        Index range                         |
|      16       |       ENABLE        |    bit    |   1    |       0       |          Y           |      N      |               |                       Enable or not                        |
|      17       |        TYPE         |  varchar  |   32   |       0       |          Y           |      N      |    SYSTEM     |                         Index type                         |
|      18       |         TAG         |  varchar  |   32   |       0       |          Y           |      N      |               | Indicator label used for front end differentiation control |
|      19       |     CREATE_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |                       Create a user                        |
|      20       |     UPDATE_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |                        Update user                         |
|      21       |     CREATE_TIME     | datetime  |   19   |       0       |          Y           |      N      |               |                       Creation time                        |
|      22       |     UPDATE_TIME     | datetime  |   19   |       0       |          Y           |      N      |               |                        Update time                         |
|      23       |    ATOM_VERSION     |  varchar  |   16   |       0       |          N           |      N      |     1.0.0     |                   Plug-in version number                   |
|      24       |     LOG_PROMPT      |  varchar  |  1024  |       0       |          N           |      N      |               |                         Log prompt                         |

**Table name:** T_QUALITY_METADATA

Quality red line basic data table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                 description                  |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------------------------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |               |                Primary key ID                |
|       2       |    DATA_ID     |  varchar  |   64   |       0       |          Y           |      N      |               |                   Data ID                    |
|       3       |   DATA_NAME    |  varchar  |   64   |       0       |          Y           |      N      |               |                  Data name                   |
|       4       |  ELEMENT_TYPE  |  varchar  |   64   |       0       |          Y           |      N      |               |          The ClassType of the atom           |
|       5       |  ELEMENT_NAME  |  varchar  |   64   |       0       |          Y           |      N      |               |                Producing atom                |
|       6       | ELEMENT_DETAIL |  varchar  |   64   |       0       |          Y           |      N      |               |             Tools/Atoms subclass             |
|       7       |   VALUE_TYPE   |  varchar  |   32   |       0       |          Y           |      N      |               | value Specifies the front-end component type |
|       8       |      DESC      |  varchar  |  256   |       0       |          Y           |      N      |               |                 description                  |
|       9       |     EXTRA      |   text    | 65535  |       0       |          Y           |      N      |               |            Additional information            |
|      10       |  CREATE_USER   |  varchar  |   64   |       0       |          Y           |      N      |               |                   founder                    |
|      11       |  UPDATE_USER   |  varchar  |   64   |       0       |          Y           |      N      |               |                   modifier                   |
|      12       |  create_time   | datetime  |   19   |       0       |          Y           |      N      |               |                Creation time                 |
|      13       |  UPDATE_TIME   | datetime  |   19   |       0       |          Y           |      N      |               |                 Update time                  |

**Table name:** T_QUALITY_RULE

**Explanation:**

**Data column:**

| Serial number |          name           | Data type | length | Decimal place | Allowable null value | Primary key | Default value |               description               |
| :-----------: | :---------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------------: |
|       1       |           ID            |  bigint   |   20   |       0       |          N           |      Y      |               |             Primary key ID              |
|       2       |          NAME           |  varchar  |  128   |       0       |          Y           |      N      |               |                Rule name                |
|       3       |          DESC           |  varchar  |  256   |       0       |          Y           |      N      |               |            Rule description             |
|       4       |     INDICATOR_RANGE     |   text    | 65535  |       0       |          Y           |      N      |               |               Index range               |
|       5       |      CONTROL_POINT      |  varchar  |   64   |       0       |          Y           |      N      |               |        Control point atomic type        |
|       6       | CONTROL_POINT_POSITION  |  varchar  |   64   |       0       |          Y           |      N      |               |     Control point red line position     |
|       7       |       CREATE_USER       |  varchar  |   64   |       0       |          Y           |      N      |               |              Create a user              |
|       8       |       UPDATE_USER       |  varchar  |   64   |       0       |          Y           |      N      |               |               Update user               |
|       9       |       CREATE_TIME       | datetime  |   19   |       0       |          Y           |      N      |               |              Creation time              |
|      10       |       UPDATE_TIME       | datetime  |   19   |       0       |          Y           |      N      |               |               Update time               |
|      11       |         ENABLE          |    bit    |   1    |       0       |          Y           |      N      |     B '1'     |              Enable or not              |
|      12       |       PROJECT_ID        |  varchar  |   64   |       0       |          Y           |      N      |               |                 Item id                 |
|      13       |     INTERCEPT_TIMES     |    int    |   10   |       0       |          Y           |      N      |       0       |         Number of interceptions         |
|      14       |      EXECUTE_COUNT      |    int    |   10   |       0       |          Y           |      N      |       0       | Number of pipeline executions in effect |
|      15       | PIPELINE_TEMPLATE_RANGE |   text    | 65535  |       0       |          Y           |      N      |               |      Pipeline template valid range      |
|      16       |       GATEWAY_ID        |  varchar  |  128   |       0       |          N           |      N      |               |       The red line matches the id       |

**Table name:** T_QUALITY_RULE_BUILD_HIS

**Explanation:**

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |               description               |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------------: |
|       1       |          ID          |  bigint   |   20   |       0       |          N           |      Y      |               |             Primary key ID              |
|       2       |      PROJECT_ID      |  varchar  |   64   |       0       |          Y           |      N      |               |                 Item ID                 |
|       3       |     PIPELINE_ID      |  varchar  |   40   |       0       |          Y           |      N      |               |               Pipeline ID               |
|       4       |       BUILD_ID       |  varchar  |   40   |       0       |          Y           |      N      |               |                Build ID                 |
|       5       |       RULE_POS       |  varchar  |   8    |       0       |          Y           |      N      |               |         Control point position          |
|       6       |      RULE_NAME       |  varchar  |  123   |       0       |          Y           |      N      |               |                Rule name                |
|       7       |      RULE_DESC       |  varchar  |  256   |       0       |          Y           |      N      |               |            Rule description             |
|       8       |      GATEWAY_ID      |  varchar  |  128   |       0       |          Y           |      N      |               |       The red line matches the id       |
|       9       |    PIPELINE_RANGE    |   text    | 65535  |       0       |          Y           |      N      |               |      Set of pipeline ids in effect      |
|      10       |    TEMPLATE_RANGE    |   text    | 65535  |       0       |          Y           |      N      |               | Set of pipelined template ids in effect |
|      11       |    INDICATOR_IDS     |   text    | 65535  |       0       |          Y           |      N      |               |               Index type                |
|      12       | INDICATOR_OPERATIONS |   text    | 65535  |       0       |          Y           |      N      |               |             Index operation             |
|      13       | INDICATOR_THRESHOLDS |   text    | 65535  |       0       |          Y           |      N      |               |           Indicator threshold           |
|      14       |    OPERATION_LIST    |   text    | 65535  |       0       |          Y           |      N      |               |             Operating list              |
|      15       |     CREATE_TIME      | datetime  |   19   |       0       |          Y           |      N      |               |              Creation time              |
|      16       |     CREATE_USER      |  varchar  |   32   |       0       |          Y           |      N      |               |                 founder                 |
|      17       |       STAGE_ID       |  varchar  |   40   |       0       |          N           |      N      |       1       |                stage_id                 |
|      18       |        STATUS        |  varchar  |   20   |       0       |          Y           |      N      |               |             Red line state              |
|      19       |     GATE_KEEPERS     |  varchar  |  1024  |       0       |          Y           |      N      |               |           Red line gatekeeper           |

**Table name:** T_QUALITY_RULE_BUILD_HIS_OPERATION

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |      ID       |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |    RULE_ID    |  bigint   |   20   |       0       |          N           |      N      |               |    Rule id     |
|       3       |   STAGE_ID    |  varchar  |   40   |       0       |          N           |      N      |               |                |
|       4       | GATE_OPT_USER |  varchar  |   32   |       0       |          Y           |      N      |               |                |
|       5       | GATE_OPT_TIME | datetime  |   19   |       0       |          Y           |      N      |               |                |

**Table name:** T_QUALITY_RULE_MAP

**Explanation:**

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description     |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------: |
|       1       |          ID          |  bigint   |   20   |       0       |          N           |      Y      |               |   Primary key ID    |
|       2       |       RULE_ID        |  bigint   |   20   |       0       |          Y           |      N      |               |       Rule ID       |
|       3       |    INDICATOR_IDS     |   text    | 65535  |       0       |          Y           |      N      |               |     Index type      |
|       4       | INDICATOR_OPERATIONS |   text    | 65535  |       0       |          Y           |      N      |               |   Index operation   |
|       5       | INDICATOR_THRESHOLDS |   text    | 65535  |       0       |          Y           |      N      |               | Indicator threshold |

**Table name:** T_QUALITY_RULE_OPERATION

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |       ID        |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |     RULE_ID     |  bigint   |   20   |       0       |          Y           |      N      |               |      Rule ID      |
|       3       |      TYPE       |  varchar  |   16   |       0       |          Y           |      N      |               |       type        |
|       4       |   NOTIFY_USER   |   text    | 65535  |       0       |          Y           |      N      |               | Notifying officer |
|       5       | NOTIFY_GROUP_ID |   text    | 65535  |       0       |          Y           |      N      |               |   User group ID   |
|       6       |  NOTIFY_TYPES   |  varchar  |   64   |       0       |          Y           |      N      |               | Notification type |
|       7       |   AUDIT_USER    |   text    | 65535  |       0       |          Y           |      N      |               |      auditor      |
|       8       |  AUDIT_TIMEOUT  |    int    |   10   |       0       |          Y           |      N      |               |   Audit timeout   |

**Table name:** T_QUALITY_RULE_TEMPLATE

Quality red line template table

**Data column:**

| Serial number |          name          | Data type | length | Decimal place | Allowable null value | Primary key | Default value |           description           |
| :-----------: | :--------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------: |
|       1       |           ID           |  bigint   |   20   |       0       |          N           |      Y      |               |         Primary key ID          |
|       2       |          NAME          |  varchar  |   64   |       0       |          Y           |      N      |               |              name               |
|       3       |          TYPE          |  varchar  |   16   |       0       |          Y           |      N      |               |              type               |
|       4       |          DESC          |  varchar  |  256   |       0       |          Y           |      N      |               |           description           |
|       5       |         STAGE          |  varchar  |   64   |       0       |          Y           |      N      |               |              stage              |
|       6       |     CONTROL_POINT      |  varchar  |   64   |       0       |          Y           |      N      |               |    Control point atomic type    |
|       7       | CONTROL_POINT_POSITION |  varchar  |   64   |       0       |          Y           |      N      |               | Control point red line position |
|       8       |      CREATE_USER       |  varchar  |   64   |       0       |          Y           |      N      |               |             founder             |
|       9       |      UPDATE_USER       |  varchar  |   64   |       0       |          Y           |      N      |               |            modifier             |
|      10       |      create_time       | datetime  |   19   |       0       |          Y           |      N      |               |          Creation time          |
|      11       |      UPDATE_TIME       | datetime  |   19   |       0       |          Y           |      N      |               |           Update time           |
|      12       |         ENABLE         |    bit    |   1    |       0       |          Y           |      N      |     B '1'     |          Enable or not          |

**Table name:** T_QUALITY_TEMPLATE_INDICATOR_MAP

**Note:** Template-indicator relationship table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |   Primary key ID   |
|       2       | TEMPLATE_ID  |  bigint   |   20   |       0       |          Y           |      N      |               |    Template ID     |
|       3       | INDICATOR_ID |  bigint   |   20   |       0       |          Y           |      N      |               |    Indicator ID    |
|       4       |  OPERATION   |  varchar  |   32   |       0       |          Y           |      N      |               | Optional operation |
|       5       |  THRESHOLD   |  varchar  |   64   |       0       |          Y           |      N      |               | Default threshold  |

**Table name:** T_RULE

**Explanation:**

**Data column:**

| Serial number |              name               | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                      description                       |
| :-----------: | :-----------------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------: |
|       1       |               ID                |  bigint   |   20   |       0       |          N           |      Y      |                   |                     Primary key ID                     |
|       2       |           PROJECT_ID            |  varchar  |   32   |       0       |          N           |      N      |                   |                        Item ID                         |
|       3       |              NAME               |  varchar  |  128   |       0       |          N           |      N      |                   |                          name                          |
|       4       |             REMARK              |   text    | 65535  |       0       |          Y           |      N      |                   |                        comment                         |
|       5       |              TYPE               |  varchar  |   32   |       0       |          N           |      N      |                   |                          type                          |
|       6       |          CONTROL_POINT          |  varchar  |   32   |       0       |          N           |      N      |                   |               Control point atomic type                |
|       7       |             TASK_ID             |  varchar  |   64   |       0       |          N           |      N      |                   |                        Task ID                         |
|       8       |            THRESHOLD            |   text    | 65535  |       0       |          N           |      N      |                   |                   Default threshold                    |
|       9       |         INDICATOR_RANGE         |   text    | 65535  |       0       |          Y           |      N      |                   |                      Index range                       |
|      10       |      RANGE_IDENTIFICATION       |   text    | 65535  |       0       |          N           |      N      |                   | ANY- Item ID collection,PART_BY_NAME- empty collection |
|      11       |            OPERATION            |  varchar  |   32   |       0       |          N           |      N      |                   |                   Optional operation                   |
|      12       |    OPERATION_END_NOTIFY_TYPE    |  varchar  |  128   |       0       |          Y           |      N      |                   |            Operation end notification type             |
|      13       |   OPERATION_END_NOTIFY_GROUP    |   text    | 65535  |       0       |          Y           |      N      |                   |  Notify the user group that the operation is complete  |
|      14       |    OPERATION_END_NOTIFY_USER    |   text    | 65535  |       0       |          Y           |      N      |                   |     Notify the user that the operation is complete     |
|      15       |   OPERATION_AUDIT_NOTIFY_USER   |   text    | 65535  |       0       |          Y           |      N      |                   |          Notify users of the operation audit           |
|      16       |         INTERCEPT_TIMES         |    int    |   10   |       0       |          N           |      N      |         0         |                Number of interceptions                 |
|      17       |             ENABLE              |    bit    |   1    |       0       |          N           |      N      |                   |                     Enable or not                      |
|      18       |             CREATOR             |  varchar  |   32   |       0       |          N           |      N      |                   |                        founder                         |
|      19       |             UPDATOR             |  varchar  |   32   |       0       |          N           |      N      |                   |                        updater                         |
|      20       |           CREATE_TIME           | datetime  |   19   |       0       |          N           |      N      |                   |                     Creation time                      |
|      21       |           UPDATE_TIME           | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                      Update time                       |
|      22       |           IS_DELETED            |    bit    |   1    |       0       |          N           |      N      |                   |        Whether to delete 0 can be deleted by 1         |
|      23       | OPERATION_AUDIT_TIMEOUT_MINUTES |    int    |   10   |       0       |          Y           |      N      |                   |                     Audit timeout                      |

**Table name:** T_TASK

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  varchar  |   64   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |    NAME     |  varchar  |  255   |       0       |          N           |      N      |               |      name      |
|       3       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       4       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
