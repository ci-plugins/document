# devops_ci_process

**Database name:** devops_ci_process

**Issue:** 1.0.0

**Documentation Description:** Database documentation for devops_ci_process

|                       Table name                        |                      description                       |
| :-----------------------------------------------------: | :----------------------------------------------------: |
|          [T_AUDIT_RESOURCE](broken-reference)           |                                                        |
|        [T_BUILD_STARTUP_PARAM](broken-reference)        |            Pipeline startup variable table             |
|             [T_METADATA](broken-reference)              |                                                        |
|    [T_PIPELINE_ATOM_REPLACE_BASE](broken-reference)     | Pipelined plug-in replaces the basic information table |
|   [T_PIPELINE_ATOM_REPLACE_HISTORY](broken-reference)   |  Pipelined plug-in replaces history information table  |
|    [T_PIPELINE_ATOM_REPLACE_ITEM](broken-reference)     |  Pipeline plug-in replacement item information table   |
|     [T_PIPELINE_BUILD_CONTAINER](broken-reference)      |     Pipelining builds container environment tables     |
|       [T_PIPELINE_BUILD_DETAIL](broken-reference)       |           Pipelining builds the detail table           |
|      [T_PIPELINE_BUILD_HISTORY](broken-reference)       |            Pipelining builds history tables            |
|   [T_PIPELINE_BUILD_HIS_DATA_CLEAR](broken-reference)   |   Pipelining builds data cleansing statistics tables   |
|       [T_PIPELINE_BUILD_STAGE](broken-reference)        |               Pipeline build phase table               |
|      [T_PIPELINE_BUILD_SUMMARY](broken-reference)       |            Pipelined builds summary tables             |
|        [T_PIPELINE_BUILD_TASK](broken-reference)        |            Pipelining builds the task list             |
|        [T_PIPELINE_BUILD_VAR](broken-reference)         |                Pipeline variable meter                 |
|    [T_PIPELINE_CONTAINER_MONITOR](broken-reference)     |                                                        |
|        [T_PIPELINE_DATA_CLEAR](broken-reference)        |        Pipeline data cleaning statistics table         |
|   [T_PIPELINE_FAILURE_NOTIFY_USER](broken-reference)    |                                                        |
|          [T_PIPELINE_FAVOR](broken-reference)           |               Pipeline collection table                |
|          [T_PIPELINE_GROUP](broken-reference)           |                Pipeline grouping table                 |
|           [T_PIPELINE_INFO](broken-reference)           |               Pipeline information table               |
|     [T_PIPELINE_JOB_MUTEX_GROUP](broken-reference)      |                                                        |
|          [T_PIPELINE_LABEL](broken-reference)           |                  Pipeline label table                  |
|      [T_PIPELINE_LABEL_PIPELINE](broken-reference)      |              Pipeline-label mapping table              |
|        [T_PIPELINE_MODEL_TASK](broken-reference)        |             Pipeline model task Task table             |
|       [T_PIPELINE_MUTEX_GROUP](broken-reference)        |                 Pipelined mutex table                  |
|       [T_PIPELINE_PAUSE_VALUE](broken-reference)        |             Pipeline pause variable table              |
|       [T_PIPELINE_REMOTE_AUTH](broken-reference)        |         Pipeline-triggered auth table remotely         |
|         [T_PIPELINE_RESOURCE](broken-reference)         |                Pipeline resource table                 |
|     [T_PIPELINE_RESOURCE_VERSION](broken-reference)     |            Pipeline resource version table             |
|           [T_PIPELINE_RULE](broken-reference)           |            Pipeline rule information table             |
|         [T_PIPELINE_SETTING](broken-reference)          |           Pipeline basic configuration table           |
|     [T_PIPELINE_SETTING_VERSION](broken-reference)      |       Pipeline basic configuration version table       |
|        [T_PIPELINE_STAGE_TAG](broken-reference)         |                                                        |
|         [T_PIPELINE_TEMPLATE](broken-reference)         |                Pipeline template table                 |
|          [T_PIPELINE_TIMER](broken-reference)           |                                                        |
|           [T_PIPELINE_USER](broken-reference)           |                                                        |
|           [T_PIPELINE_VIEW](broken-reference)           |                                                        |
|        [T_PIPELINE_VIEW_LABEL](broken-reference)        |                                                        |
|       [T_PIPELINE_VIEW_PROJECT](broken-reference)       |                                                        |
|   [T_PIPELINE_VIEW_USER_LAST_VIEW](broken-reference)    |                                                        |
|    [T_PIPELINE_VIEW_USER_SETTINGS](broken-reference)    |                                                        |
|         [T_PIPELINE_WEBHOOK](broken-reference)          |                                                        |
|    [T_PIPELINE_WEBHOOK_BUILD_LOG](broken-reference)     |                                                        |
| [T_PIPELINE_WEBHOOK_BUILD_LOG_DETAIL](broken-reference) |                                                        |
|      [T_PIPELINE_WEBHOOK_QUEUE](broken-reference)       |                                                        |
|     [T_PROJECT_PIPELINE_CALLBACK](broken-reference)     |                                                        |
| [T_PROJECT_PIPELINE_CALLBACK_HISTORY](broken-reference) |                                                        |
|              [T_REPORT](broken-reference)               |                 Pipeline product table                 |
|             [T_TEMPLATE](broken-reference)              |          Pipeline template information table           |
|      [T_TEMPLATE_INSTANCE_BASE](broken-reference)       |          The template lists basic information          |
|      [T_TEMPLATE_INSTANCE_ITEM](broken-reference)       |       Template real list item information table        |
|         [T_TEMPLATE_PIPELINE](broken-reference)         |       Pipelining template-instance mapping table       |

**Table name:** T_AUDIT_RESOURCE

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |                   |  Primary key ID   |
|       2       | RESOURCE_TYPE  |  varchar  |   32   |       0       |          N           |      N      |                   |   Resource type   |
|       3       |  RESOURCE_ID   |  varchar  |  128   |       0       |          N           |      N      |                   |    Resource ID    |
|       4       | RESOURCE_NAME  |  varchar  |  128   |       0       |          N           |      N      |                   |   Resource name   |
|       5       |    USER_ID     |  varchar  |   64   |       0       |          N           |      N      |                   |      User ID      |
|       6       |     ACTION     |  varchar  |   64   |       0       |          N           |      N      |                   |     operation     |
|       7       | ACTION_CONTENT |  varchar  |  1024  |       0       |          N           |      N      |                   | Operation content |
|       8       |  CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time   |
|       9       |     STATUS     |  varchar  |   32   |       0       |          Y           |      N      |                   |       state       |
|      10       |   PROJECT_ID   |  varchar  |  128   |       0       |          N           |      N      |                   |      Item ID      |

**Table name:** T_BUILD_STARTUP_PARAM

Pipeline startup variable table

**Data column:**

| Serial number |    name     | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |   bigint   |    20    |       0       |          N           |      Y      |               | Primary key ID |
|       2       |  BUILD_ID   |  varchar   |    64    |       0       |          N           |      N      |               |    Build ID    |
|       3       |    PARAM    | mediumtext | 16777215 |       0       |          N           |      N      |               |   parameter    |
|       4       | PROJECT_ID  |  varchar   |    64    |       0       |          Y           |      N      |               |    Item ID     |
|       5       | PIPELINE_ID |  varchar   |    64    |       0       |          Y           |      N      |               |  Pipeline ID   |

**Table name:** T_METADATA

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |       ID        |  bigint   |   20   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       |   PROJECT_ID    |  varchar  |   32   |       0       |          N           |      N      |                   |    Item ID     |
|       3       |   PIPELINE_ID   |  varchar  |   34   |       0       |          N           |      N      |                   |  Pipeline ID   |
|       4       |    BUILD_ID     |  varchar  |   34   |       0       |          N           |      N      |                   |    Build ID    |
|       5       |  META_DATA_ID   |  varchar  |  128   |       0       |          N           |      N      |                   |  Metadata ID   |
|       6       | META_DATA_VALUE |  varchar  |  255   |       0       |          N           |      N      |                   | Metadata value |
|       7       |   CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |

**Table name:** T_PIPELINE_ATOM_REPLACE_BASE

**Pipelined** plug-in replaces basic information table

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |       description       |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :---------------------: |
|       1       |        ID        |  varchar  |   32   |       0       |          N           |      Y      |                      |     Primary key ID      |
|       2       |    PROJECT_ID    |  varchar  |   64   |       0       |          Y           |      N      |                      |         Item ID         |
|       3       | PIPELINE_ID_INFO |   text    | 65535  |       0       |          Y           |      N      |                      | Pipeline ID information |
|       4       |  FROM_ATOM_CODE  |  varchar  |   64   |       0       |          N           |      N      |                      |  Replaced plug-in code  |
|       5       |   TO_ATOM_CODE   |  varchar  |   64   |       0       |          N           |      N      |                      |  Replaced plug-in code  |
|       6       |      STATUS      |  varchar  |   32   |       0       |          N           |      N      |         INIT         |          state          |
|       7       |     CREATOR      |  varchar  |   50   |       0       |          N           |      N      |        system        |         founder         |
|       8       |     MODIFIER     |  varchar  |   50   |       0       |          N           |      N      |        system        |        modifier         |
|       9       |   UPDATE_TIME    | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |    Modification time    |
|      10       |   CREATE_TIME    | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |      Creation time      |

**Table name:** T_PIPELINE_ATOM_REPLACE_HISTORY

**Pipelined** plug-in replaces history information table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |              description              |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :-----------------------------------: |
|       1       |       ID       |  varchar  |   32   |       0       |          N           |      Y      |                      |            Primary key ID             |
|       2       |   PROJECT_ID   |  varchar  |   64   |       0       |          Y           |      N      |                      |                Item ID                |
|       3       |     BUS_ID     |  varchar  |   34   |       0       |          N           |      N      |                      |              Service ID               |
|       4       |    BUS_TYPE    |  varchar  |   32   |       0       |          N           |      N      |       PIPELINE       |           Type of business            |
|       5       | SOURCE_VERSION |    int    |   10   |       0       |          N           |      N      |                      |         Source version number         |
|       6       | TARGET_VERSION |    int    |   10   |       0       |          Y           |      N      |                      |         Target version number         |
|       7       |     STATUS     |  varchar  |   32   |       0       |          N           |      N      |                      |                 state                 |
|       8       |      LOG       |  varchar  |  128   |       0       |          Y           |      N      |                      |                  log                  |
|       9       |    BASE_ID     |  varchar  |   32   |       0       |          N           |      N      |                      | Plug-in replaces basic information ID |
|      10       |    ITEM_ID     |  varchar  |   32   |       0       |          N           |      N      |                      |  ID of the plug-in replacement item   |
|      11       |    CREATOR     |  varchar  |   50   |       0       |          N           |      N      |        system        |                founder                |
|      12       |    MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |        system        |               modifier                |
|      13       |  UPDATE_TIME   | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |           Modification time           |
|      14       |  CREATE_TIME   | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |             Creation time             |

**Table name:** T_PIPELINE_ATOM_REPLACE_ITEM

Pipeline plug-in replacement item information table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |                description                |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :---------------------------------------: |
|       1       |         ID         |  varchar  |   32   |       0       |          N           |      Y      |                      |              Primary key ID               |
|       2       |   FROM_ATOM_CODE   |  varchar  |   64   |       0       |          N           |      N      |                      |           Replaced plug-in code           |
|       3       | FROM_ATOM_VERSION  |  varchar  |   20   |       0       |          N           |      N      |                      |      Version of the replaced plug-in      |
|       4       |    TO_ATOM_CODE    |  varchar  |   64   |       0       |          N           |      N      |                      |         Replacement plug-in code          |
|       5       |  TO_ATOM_VERSION   |  varchar  |   20   |       0       |          N           |      N      |                      |    Replace the plug-in version number     |
|       6       |       STATUS       |  varchar  |   32   |       0       |          N           |      N      |         INIT         |                   state                   |
|       7       | PARAM_REPLACE_INFO |   text    | 65535  |       0       |          Y           |      N      |                      | Plug-in parameter replacement information |
|       8       |      BASE_ID       |  varchar  |   32   |       0       |          N           |      N      |                      |   Plug-in replaces basic information ID   |
|       9       |      CREATOR       |  varchar  |   50   |       0       |          N           |      N      |        system        |                  founder                  |
|      10       |      MODIFIER      |  varchar  |   50   |       0       |          N           |      N      |        system        |                 modifier                  |
|      11       |    UPDATE_TIME     | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |             Modification time             |
|      12       |    CREATE_TIME     | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |               Creation time               |

**Table name:** T_PIPELINE_BUILD_CONTAINER

Pipeline build container environment table

**Data column:**

| Serial number |      name      | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |     description      |
| :-----------: | :------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :------------------: |
|       1       |   PROJECT_ID   |  varchar   |    64    |       0       |          N           |      N      |                   |       Item ID        |
|       2       |  PIPELINE_ID   |  varchar   |    64    |       0       |          N           |      N      |                   |     Pipeline ID      |
|       3       |    BUILD_ID    |  varchar   |    64    |       0       |          N           |      Y      |                   |       Build ID       |
|       4       |    STAGE_ID    |  varchar   |    64    |       0       |          N           |      Y      |                   |   Current stageId    |
|       5       |  CONTAINER_ID  |  varchar   |    64    |       0       |          N           |      Y      |                   |  Build container ID  |
|       6       | CONTAINER_TYPE |  varchar   |    45    |       0       |          Y           |      N      |                   |    Container type    |
|       7       |      SEQ       |    int     |    10    |       0       |          N           |      N      |                   |                      |
|       8       |     STATUS     |    int     |    10    |       0       |          Y           |      N      |                   |        state         |
|       9       |   START_TIME   | timestamp  |    19    |       0       |          Y           |      N      | CURRENT_TIMESTAMP |      Start time      |
|      10       |    END_TIME    | timestamp  |    19    |       0       |          Y           |      N      |                   |       End time       |
|      11       |      COST      |    int     |    10    |       0       |          Y           |      N      |         0         |         cost         |
|      12       | EXECUTE_COUNT  |    int     |    10    |       0       |          Y           |      N      |         1         | Number of executions |
|      13       |   CONDITIONS   | mediumtext | 16777215 |       0       |          Y           |      N      |                   |      condition       |

**Table name:** T_PIPELINE_BUILD_DETAIL

**Pipeline** build details table

**Data column:**

| Serial number |    name     | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :---------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       | PROJECT_ID  |  varchar   |    64    |       0       |          N           |      N      |               |                  |
|       2       |  BUILD_ID   |  varchar   |    34    |       0       |          N           |      Y      |               |     Build ID     |
|       3       |  BUILD_NUM  |    int     |    10    |       0       |          Y           |      N      |               | Number of builds |
|       4       |    MODEL    | mediumtext | 16777215 |       0       |          Y           |      N      |               |  Pipeline model  |
|       5       | START_USER  |  varchar   |    32    |       0       |          Y           |      N      |               |    initiator     |
|       6       |   TRIGGER   |  varchar   |    32    |       0       |          Y           |      N      |               |    flip-flop     |
|       7       | START_TIME  |  datetime  |    19    |       0       |          Y           |      N      |               |    Start time    |
|       8       |  END_TIME   |  datetime  |    19    |       0       |          Y           |      N      |               |     End time     |
|       9       |   STATUS    |  varchar   |    32    |       0       |          Y           |      N      |               |      state       |
|      10       | CANCEL_USER |  varchar   |    32    |       0       |          Y           |      N      |               |    canceller     |

**Table name:** T_PIPELINE_BUILD_HISTORY

**Pipeline** build history table

**Data column:**

| Serial number |       name        | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |             description             |
| :-----------: | :---------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :---------------------------------: |
|       1       |     BUILD_ID      |  varchar   |    34    |       0       |          N           |      Y      |               |              Build ID               |
|       2       |  PARENT_BUILD_ID  |  varchar   |    34    |       0       |          Y           |      N      |               |           Parent build ID           |
|       3       |  PARENT_TASK_ID   |  varchar   |    34    |       0       |          Y           |      N      |               |        ID of the parent task        |
|       4       |     BUILD_NUM     |    int     |    10    |       0       |          Y           |      N      |       0       |          Number of builds           |
|       5       |    PROJECT_ID     |  varchar   |    64    |       0       |          N           |      N      |               |               Item ID               |
|       6       |    PIPELINE_ID    |  varchar   |    34    |       0       |          N           |      N      |               |             Pipeline ID             |
|       7       |      VERSION      |    int     |    10    |       0       |          Y           |      N      |               |           Version number            |
|       8       |    START_USER     |  varchar   |    64    |       0       |          Y           |      N      |               |              initiator              |
|       9       |      TRIGGER      |  varchar   |    32    |       0       |          N           |      N      |               |              flip-flop              |
|      10       |    START_TIME     | timestamp  |    19    |       0       |          Y           |      N      |               |             Start time              |
|      11       |     END_TIME      | timestamp  |    19    |       0       |          Y           |      N      |               |              End time               |
|      12       |      STATUS       |    int     |    10    |       0       |          Y           |      N      |               |                state                |
|      13       |   STAGE_STATUS    |    text    |  65535   |       0       |          Y           |      N      |               | State of each stage of the pipeline |
|      14       |    TASK_COUNT     |    int     |    10    |       0       |          Y           |      N      |               |      Number of pipeline tasks       |
|      15       |   FIRST_TASK_ID   |  varchar   |    34    |       0       |          Y           |      N      |               |            First task id            |
|      16       |      CHANNEL      |  varchar   |    32    |       0       |          Y           |      N      |               |           Project channel           |
|      17       |   TRIGGER_USER    |  varchar   |    64    |       0       |          Y           |      N      |               |               trigger               |
|      18       |     MATERIAL      | mediumtext | 16777215 |       0       |          Y           |      N      |               |            Raw material             |
|      19       |    QUEUE_TIME     | timestamp  |    19    |       0       |          Y           |      N      |               |          Queue start time           |
|      20       |   ARTIFACT_INFO   | mediumtext | 16777215 |       0       |          Y           |      N      |               |     Component list information      |
|      21       |      REMARK       |  varchar   |   4096   |       0       |          Y           |      N      |               |               comment               |
|      22       |   EXECUTE_TIME    |   bigint   |    20    |       0       |          Y           |      N      |               |           Execution time            |
|      23       | BUILD_PARAMETERS  | mediumtext | 16777215 |       0       |          Y           |      N      |               |     Build environment parameter     |
|      24       |   WEBHOOK_TYPE    |  varchar   |    64    |       0       |          Y           |      N      |               |            WEBHOOK type             |
|      25       | RECOMMEND_VERSION |  varchar   |    64    |       0       |          Y           |      N      |               |     Recommended version number      |
|      26       |    ERROR_TYPE     |    int     |    10    |       0       |          Y           |      N      |               |             Error type              |
|      27       |    ERROR_CODE     |    int     |    10    |       0       |          Y           |      N      |               |             Error code              |
|      28       |     ERROR_MSG     |    text    |  65535   |       0       |          Y           |      N      |               |           misdescription            |
|      29       |   WEBHOOK_INFO    |    text    |  65535   |       0       |          Y           |      N      |               |         WEBHOOK information         |
|      30       |     IS_RETRY      |    bit     |    1     |       0       |          Y           |      N      |     B '0'     |            Retry or not             |
|      31       |    ERROR_INFO     |    text    |  65535   |       0       |          Y           |      N      |               |            Error message            |
|      32       |     BUILD_MSG     |  varchar   |   255    |       0       |          Y           |      N      |               |      Construction information       |
|      33       |  BUILD_NUM_ALIAS  |  varchar   |   256    |       0       |          Y           |      N      |               |         Custom build number         |

**Table name:** T_PIPELINE_BUILD_HIS_DATA_CLEAR

**Pipeline** construction data cleaning statistical table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     | description |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :---------: |
|       1       |  BUILD_ID   |  varchar  |   34   |       0       |          N           |      Y      |                      |  Build ID   |
|       2       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |                      | Pipeline ID |
|       3       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |                      |   Item ID   |
|       4       |  DEL_TIME   | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |             |

**Table name:** T_PIPELINE_BUILD_STAGE

**Pipeline** construction stage table

**Data column:**

| Serial number |     name      | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |        description         |
| :-----------: | :-----------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :------------------------: |
|       1       |  PROJECT_ID   |  varchar   |    64    |       0       |          N           |      N      |                   |          Item ID           |
|       2       |  PIPELINE_ID  |  varchar   |    64    |       0       |          N           |      N      |                   |        Pipeline ID         |
|       3       |   BUILD_ID    |  varchar   |    64    |       0       |          N           |      Y      |                   |          Build ID          |
|       4       |   STAGE_ID    |  varchar   |    64    |       0       |          N           |      Y      |                   |      Current stageId       |
|       5       |      SEQ      |    int     |    10    |       0       |          N           |      N      |                   |                            |
|       6       |    STATUS     |    int     |    10    |       0       |          Y           |      N      |                   |           state            |
|       7       |  START_TIME   | timestamp  |    19    |       0       |          Y           |      N      | CURRENT_TIMESTAMP |         Start time         |
|       8       |   END_TIME    | timestamp  |    19    |       0       |          Y           |      N      |                   |          End time          |
|       9       |     COST      |    int     |    10    |       0       |          Y           |      N      |         0         |            cost            |
|      10       | EXECUTE_COUNT |    int     |    10    |       0       |          Y           |      N      |         1         |    Number of executions    |
|      11       |  CONDITIONS   | mediumtext | 16777215 |       0       |          Y           |      N      |                   |         condition          |
|      12       |   CHECK_IN    | mediumtext | 16777215 |       0       |          Y           |      N      |                   | Access check configuration |
|      13       |   CHECK_OUT   | mediumtext | 16777215 |       0       |          Y           |      N      |                   |  Check the configuration   |

**Table name:** T_PIPELINE_BUILD_SUMMARY

Pipeline construction summary table

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description     |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------: |
|       1       |    PIPELINE_ID    |  varchar  |   34   |       0       |          N           |      Y      |               |     Pipeline ID     |
|       2       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |               |       Item ID       |
|       3       |     BUILD_NUM     |    int    |   10   |       0       |          Y           |      N      |       0       |  Number of builds   |
|       4       |     BUILD_NO      |    int    |   10   |       0       |          Y           |      N      |       0       |    Build number     |
|       5       |   FINISH_COUNT    |    int    |   10   |       0       |          Y           |      N      |       0       | Number of finishes  |
|       6       |   RUNNING_COUNT   |    int    |   10   |       0       |          Y           |      N      |       0       |   Number of runs    |
|       7       |    QUEUE_COUNT    |    int    |   10   |       0       |          Y           |      N      |       0       |  Number of queues   |
|       8       |  LATEST_BUILD_ID  |  varchar  |   34   |       0       |          Y           |      N      |               |    Last build ID    |
|       9       |  LATEST_TASK_ID   |  varchar  |   34   |       0       |          Y           |      N      |               |   Recent task ID    |
|      10       | LATEST_START_USER |  varchar  |   64   |       0       |          Y           |      N      |               |   Recent starter    |
|      11       | LATEST_START_TIME | timestamp |   19   |       0       |          Y           |      N      |               |   Last start time   |
|      12       |  LATEST_END_TIME  | timestamp |   19   |       0       |          Y           |      N      |               |    Last end time    |
|      13       | LATEST_TASK_COUNT |    int    |   10   |       0       |          Y           |      N      |               |  Recent task count  |
|      14       | LATEST_TASK_NAME  |  varchar  |  128   |       0       |          Y           |      N      |               |  Recent task name   |
|      15       |   LATEST_STATUS   |    int    |   10   |       0       |          Y           |      N      |               |    Nearest state    |
|      16       |  BUILD_NUM_ALIAS  |  varchar  |  256   |       0       |          Y           |      N      |               | Custom build number |

**Table name:** T_PIPELINE_BUILD_TASK

**Pipeline** build task table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |            description             |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------------------: |
|       1       |    PIPELINE_ID     |  varchar   |    34    |       0       |          N           |      N      |               |            Pipeline ID             |
|       2       |     PROJECT_ID     |  varchar   |    64    |       0       |          N           |      N      |               |              Item ID               |
|       3       |      BUILD_ID      |  varchar   |    34    |       0       |          N           |      Y      |               |              Build ID              |
|       4       |      STAGE_ID      |  varchar   |    34    |       0       |          N           |      N      |               |          Current stageId           |
|       5       |    CONTAINER_ID    |  varchar   |    34    |       0       |          N           |      N      |               |         Build container ID         |
|       6       |     TASK_NAME      |  varchar   |   128    |       0       |          Y           |      N      |               |             Task name              |
|       7       |      TASK_ID       |  varchar   |    34    |       0       |          N           |      Y      |               |              Task ID               |
|       8       |    TASK_PARAMS     | mediumtext | 16777215 |       0       |          Y           |      N      |               |         Task parameter set         |
|       9       |     TASK_TYPE      |  varchar   |    64    |       0       |          N           |      N      |               |             Task type              |
|      10       |     TASK_ATOM      |  varchar   |   128    |       0       |          Y           |      N      |               |           Task atom code           |
|      11       |     ATOM_CODE      |  varchar   |   128    |       0       |          Y           |      N      |               | The unique identity of the plug-in |
|      12       |     START_TIME     | timestamp  |    19    |       0       |          Y           |      N      |               |             Start time             |
|      13       |      END_TIME      | timestamp  |    19    |       0       |          Y           |      N      |               |              End time              |
|      14       |      STARTER       |  varchar   |    64    |       0       |          N           |      N      |               |              executor              |
|      15       |      APPROVER      |  varchar   |    64    |       0       |          Y           |      N      |               |              approver              |
|      16       |       STATUS       |    int     |    10    |       0       |          Y           |      N      |               |               state                |
|      17       |   EXECUTE_COUNT    |    int     |    10    |       0       |          Y           |      N      |       0       |        Number of executions        |
|      18       |      TASK_SEQ      |    int     |    10    |       0       |          Y           |      N      |       1       |           Task sequence            |
|      19       |   SUB_PROJECT_ID   |  varchar   |    64    |       0       |          Y           |      N      |               |           Subproject id            |
|      20       |    SUB_BUILD_ID    |  varchar   |    34    |       0       |          Y           |      N      |               |            Subbuild id             |
|      21       |   CONTAINER_TYPE   |  varchar   |    45    |       0       |          Y           |      N      |               |           Container type           |
|      22       | ADDITIONAL_OPTIONS | mediumtext | 16777215 |       0       |          Y           |      N      |               |           Other options            |
|      23       |     TOTAL_TIME     |   bigint   |    20    |       0       |          Y           |      N      |               |             Total time             |
|      24       |     ERROR_TYPE     |    int     |    10    |       0       |          Y           |      N      |               |             Error type             |
|      25       |     ERROR_CODE     |    int     |    10    |       0       |          Y           |      N      |               |             Error code             |
|      26       |     ERROR_MSG      |    text    |  65535   |       0       |          Y           |      N      |               |           misdescription           |
|      27       | CONTAINER_HASH_ID  |  varchar   |    64    |       0       |          Y           |      N      |               |  Build Job unique identification   |

**Table name:** T_PIPELINE_BUILD_VAR

**Pipeline** variable scale

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |  BUILD_ID   |  varchar  |   34   |       0       |          N           |      Y      |               |       Build ID       |
|       2       |     KEY     |  varchar  |  255   |       0       |          N           |      Y      |               |         key          |
|       3       |    VALUE    |  varchar  |  4000  |       0       |          Y           |      N      |               |        value         |
|       4       | PROJECT_ID  |  varchar  |   64   |       0       |          Y           |      N      |               |       Item ID        |
|       5       | PIPELINE_ID |  varchar  |   64   |       0       |          Y           |      N      |               |     Pipeline ID      |
|       6       |  VAR_TYPE   |  varchar  |   64   |       0       |          Y           |      N      |               |    Variable type     |
|       7       |  READ_ONLY  |    bit    |   1    |       0       |          Y           |      N      |               | Whether to read only |

**Table name:** T_PIPELINE_CONTAINER_MONITOR

**Explanation:**

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       |     OS_TYPE      |  varchar  |   32   |       0       |          N           |      N      |               |      System type       |
|       3       |    BUILD_TYPE    |  varchar  |   32   |       0       |          N           |      N      |               |       Build type       |
|       4       | MAX_STARTUP_TIME |  bigint   |   20   |       0       |          N           |      N      |               |  Maximum startup time  |
|       5       | MAX_EXECUTE_TIME |  bigint   |   20   |       0       |          N           |      N      |               | Maximum execution time |
|       6       |      USERS       |  varchar  |  1024  |       0       |          N           |      N      |               |       User list        |

**Table name:** T_PIPELINE_DATA_CLEAR

**Pipeline** data cleaning statistical table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     | description |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :---------: |
|       1       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      Y      |                      | Pipeline ID |
|       2       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |                      |   Item ID   |
|       3       |  DEL_TIME   | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |             |

**Table name:** T_PIPELINE_FAILURE_NOTIFY_USER

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |   USER_ID    |  varchar  |   32   |       0       |          Y           |      N      |               |      User ID      |
|       3       | NOTIFY_TYPES |  varchar  |   32   |       0       |          Y           |      N      |               | Notification type |

**Table name:** T_PIPELINE_FAVOR

**Assembly** line collection table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID     |
|       3       | PIPELINE_ID |  varchar  |   64   |       0       |          N           |      N      |               |  Pipeline ID   |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       5       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |

**Table name:** T_PIPELINE_GROUP

**Pipeline** group table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar  |   32   |       0       |          N           |      N      |               |    Item ID     |
|       3       |    NAME     |  varchar  |   64   |       0       |          N           |      N      |               |      name      |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       5       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
|       6       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |
|       7       | UPDATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    modifier    |

**Table name:** T_PIPELINE_INFO

**Pipeline** information table

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |        description        |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------: |
|       1       |     PIPELINE_ID      |  varchar  |   34   |       0       |          N           |      Y      |                   |        Pipeline ID        |
|       2       |      PROJECT_ID      |  varchar  |   64   |       0       |          N           |      N      |                   |          Item ID          |
|       3       |    PIPELINE_NAME     |  varchar  |  255   |       0       |          N           |      N      |                   |       Pipeline name       |
|       4       |    PIPELINE_DESC     |  varchar  |  255   |       0       |          Y           |      N      |                   |   Pipeline description    |
|       5       |       VERSION        |    int    |   10   |       0       |          Y           |      N      |         1         |      Version number       |
|       6       |     CREATE_TIME      | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |       Creation time       |
|       7       |       CREATOR        |  varchar  |   64   |       0       |          N           |      N      |                   |          founder          |
|       8       |     UPDATE_TIME      | timestamp |   19   |       0       |          Y           |      N      |                   |        Update time        |
|       9       |   LAST_MODIFY_USER   |  varchar  |   64   |       0       |          N           |      N      |                   |      Recent modifier      |
|      10       |       CHANNEL        |  varchar  |   32   |       0       |          Y           |      N      |                   |      Project channel      |
|      11       |    MANUAL_STARTUP    |    int    |   10   |       0       |          Y           |      N      |         1         | Whether to start manually |
|      12       |     ELEMENT_SKIP     |    int    |   10   |       0       |          Y           |      N      |         0         | Whether to skip plug-ins  |
|      13       |      TASK_COUNT      |    int    |   10   |       0       |          Y           |      N      |         0         | Number of pipeline tasks  |
|      14       |        DELETE        |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |       Delete or not       |
|      15       |          ID          |  bigint   |   20   |       0       |          N           |      N      |                   |      Primary key ID       |
|      16       | PIPELINE_NAME_PINYIN |  varchar  |  1300  |       0       |          Y           |      N      |                   |   Pipeline name pinyin    |

**Table name:** T_PIPELINE_JOB_MUTEX_GROUP

**Explanation:**

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |       description        |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------: |
|       1       |      PROJECT_ID      |  varchar  |   64   |       0       |          N           |      Y      |               |         Item ID          |
|       2       | JOB_MUTEX_GROUP_NAME |  varchar  |  127   |       0       |          N           |      Y      |               | Job exclusive group name |

**Table name:** T_PIPELINE_LABEL

**Pipeline** label table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID     |
|       3       |  GROUP_ID   |  bigint   |   20   |       0       |          N           |      N      |               | User group ID  |
|       4       |    NAME     |  varchar  |   64   |       0       |          N           |      N      |               |      name      |
|       5       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       6       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
|       7       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |
|       8       | UPDATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    modifier    |

**Table name:** T_PIPELINE_LABEL_PIPELINE

**Pipeline-label** mapping table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID     |
|       3       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |               |  Pipeline ID   |
|       4       |  LABEL_ID   |  bigint   |   20   |       0       |          N           |      N      |               |     Tag ID     |
|       5       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       6       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |

**Table name:** T_PIPELINE_MODEL_TASK

**Pipeline** model task task table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |            description             |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------------------: |
|       1       |    PIPELINE_ID     |  varchar   |    64    |       0       |          N           |      Y      |               |            Pipeline ID             |
|       2       |     PROJECT_ID     |  varchar   |    64    |       0       |          N           |      Y      |               |              Item ID               |
|       3       |      STAGE_ID      |  varchar   |    64    |       0       |          N           |      Y      |               |          Current stageId           |
|       4       |    CONTAINER_ID    |  varchar   |    64    |       0       |          N           |      Y      |               |         Build container ID         |
|       5       |      TASK_ID       |  varchar   |    64    |       0       |          N           |      Y      |               |              Task ID               |
|       6       |     TASK_NAME      |  varchar   |   128    |       0       |          Y           |      N      |               |             Task name              |
|       7       |     CLASS_TYPE     |  varchar   |    64    |       0       |          N           |      N      |               |           Plug-in class            |
|       8       |     TASK_ATOM      |  varchar   |   128    |       0       |          Y           |      N      |               |           Task atom code           |
|       9       |      TASK_SEQ      |    int     |    10    |       0       |          Y           |      N      |       1       |           Task sequence            |
|      10       |    TASK_PARAMS     | mediumtext | 16777215 |       0       |          Y           |      N      |               |         Task parameter set         |
|      11       |         OS         |  varchar   |    45    |       0       |          Y           |      N      |               |          Operating system          |
|      12       | ADDITIONAL_OPTIONS | mediumtext | 16777215 |       0       |          Y           |      N      |               |           Other options            |
|      13       |     ATOM_CODE      |  varchar   |    32    |       0       |          N           |      N      |               | The unique identity of the plug-in |
|      14       |    ATOM_VERSION    |  varchar   |    20    |       0       |          Y           |      N      |               |       Plug-in version number       |
|      15       |    CREATE_TIME     |  datetime  |    23    |       0       |          Y           |      N      |               |           Creation time            |
|      16       |    UPDATE_TIME     |  datetime  |    23    |       0       |          Y           |      N      |               |            Update time             |

**Table name:** T_PIPELINE_MUTEX_GROUP

**Pipelined** mutually exclusive table

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description   |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------: |
|       1       | PROJECT_ID |  varchar  |   64   |       0       |          N           |      Y      |               |     Item ID     |
|       2       | GROUP_NAME |  varchar  |  127   |       0       |          N           |      Y      |               | User group name |

**Table name:** T_PIPELINE_PAUSE_VALUE

**Pipeline** suspension variable table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |               description               |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------------: |
|       1       |  PROJECT_ID   |  varchar  |   64   |       0       |          N           |      N      |               |                                         |
|       2       |   BUILD_ID    |  varchar  |   34   |       0       |          N           |      Y      |               |                Build ID                 |
|       3       |    TASK_ID    |  varchar  |   34   |       0       |          N           |      Y      |               |                 Task ID                 |
|       4       | DEFAULT_VALUE |   text    | 65535  |       0       |          Y           |      N      |               |            Default variable             |
|       5       |   NEW_VALUE   |   text    | 65535  |       0       |          Y           |      N      |               | User-supplied variable after suspension |
|       6       |  CREATE_TIME  | timestamp |   19   |       0       |          Y           |      N      |               |                Add time                 |

**Table name:** T_PIPELINE_REMOTE_AUTH

**Pipelining** remote trigger auth table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |  PIPELINE_ID  |  varchar  |   34   |       0       |          N           |      Y      |               |     Pipeline ID      |
|       2       | PIPELINE_AUTH |  varchar  |   32   |       0       |          N           |      N      |               | Pipelining authority |
|       3       |  PROJECT_ID   |  varchar  |   32   |       0       |          N           |      N      |               |       Item ID        |
|       4       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |    Creation time     |
|       5       |  CREATE_USER  |  varchar  |   64   |       0       |          N           |      N      |               |       founder        |

**Table name:** T_PIPELINE_RESOURCE

**Pipeline** resource table

**Data column:**

| Serial number |    name     | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       | PROJECT_ID  |  varchar   |    64    |       0       |          N           |      N      |                   |    Item ID     |
|       2       | PIPELINE_ID |  varchar   |    34    |       0       |          N           |      Y      |                   |  Pipeline ID   |
|       3       |   VERSION   |    int     |    10    |       0       |          N           |      Y      |         1         | Version number |
|       4       |    MODEL    | mediumtext | 16777215 |       0       |          Y           |      N      |                   | Pipeline model |
|       5       |   CREATOR   |  varchar   |    64    |       0       |          Y           |      N      |                   |    founder     |
|       6       | CREATE_TIME | timestamp  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |

**Table name:** T_PIPELINE_RESOURCE_VERSION

**Pipeline** resource version table

**Data column:**

| Serial number |     name     | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :----------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |  PROJECT_ID  |  varchar   |    64    |       0       |          N           |      N      |                   |    Item ID     |
|       2       | PIPELINE_ID  |  varchar   |    34    |       0       |          N           |      Y      |                   |  Pipeline ID   |
|       3       |   VERSION    |    int     |    10    |       0       |          N           |      Y      |         1         | Version number |
|       4       | VERSION_NAME |  varchar   |    64    |       0       |          N           |      N      |                   |  Version name  |
|       5       |    MODEL     | mediumtext | 16777215 |       0       |          Y           |      N      |                   | Pipeline model |
|       6       |   CREATOR    |  varchar   |    64    |       0       |          Y           |      N      |                   |    founder     |
|       7       | CREATE_TIME  | timestamp  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |

**Table name:** T_PIPELINE_RULE

**Pipeline** rules information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                      |     Primary key ID     |
|       2       |  RULE_NAME  |  varchar  |  256   |       0       |          N           |      N      |                      |       Rule name        |
|       3       |  BUS_CODE   |  varchar  |  128   |       0       |          N           |      N      |                      | Service identification |
|       4       |  PROCESSOR  |  varchar  |  128   |       0       |          N           |      N      |                      |       processor        |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |        system        |        founder         |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |        system        |        modifier        |
|       7       | UPDATE_TIME | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |   Modification time    |
|       8       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |     Creation time      |

**Table name:** T_PIPELINE_SETTING

**Pipeline** basic configuration table

**Data column:**

| Serial number |                name                | Data type  |   length   | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :--------------------------------: | :--------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |            PIPELINE_ID             |  varchar   |     34     |       0       |          N           |      Y      |               |                         Pipeline ID                          |
|       2       |                DESC                |  varchar   |    1024    |       0       |          Y           |      N      |               |                         description                          |
|       3       |              RUN_TYPE              |    int     |     10     |       0       |          Y           |      N      |               |                                                              |
|       4       |                NAME                |  varchar   |    255     |       0       |          Y           |      N      |               |                             name                             |
|       5       |          SUCCESS_RECEIVER          | mediumtext |  16777215  |       0       |          Y           |      N      |               |                     Successful recipient                     |
|       6       |           FAIL_RECEIVER            | mediumtext |  16777215  |       0       |          Y           |      N      |               |                      Failure recipient                       |
|       7       |           SUCCESS_GROUP            | mediumtext |  16777215  |       0       |          Y           |      N      |               |                       Successful group                       |
|       8       |             FAIL_GROUP             | mediumtext |  16777215  |       0       |          Y           |      N      |               |                        Failure group                         |
|       9       |            SUCCESS_TYPE            |  varchar   |     32     |       0       |          Y           |      N      |               |                Successful notification method                |
|      10       |             FAIL_TYPE              |  varchar   |     32     |       0       |          Y           |      N      |               |                  Failure notification mode                   |
|      11       |             PROJECT_ID             |  varchar   |     64     |       0       |          Y           |      N      |               |                           Item ID                            |
|      12       |     SUCCESS_WECHAT_GROUP_FLAG      |    bit     |     1      |       0       |          N           |      N      |     B '0'     |    Successful enterprise wechat group notification switch    |
|      13       |        SUCCESS_WECHAT_GROUP        |  varchar   |    1024    |       0       |          N           |      N      |               |   Successful enterprise wechat group notification group ID   |
|      14       |       FAIL_WECHAT_GROUP_FLAG       |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The enterprise wechat group notification switch failed. Procedure |
|      15       |         FAIL_WECHAT_GROUP          |  varchar   |    1024    |       0       |          N           |      N      |               | ID of the failed enterprise wechat group notification group  |
|      16       |           RUN_LOCK_TYPE            |    int     |     10     |       0       |          Y           |      N      |       1       |                          Lock type                           |
|      17       |        SUCCESS_DETAIL_FLAG         |    bit     |     1      |       0       |          Y           |      N      |     B '0'     | Pipeline details connection switch for successful notification |
|      18       |          FAIL_DETAIL_FLAG          |    bit     |     1      |       0       |          Y           |      N      |     B '0'     | Pipeline details connection switch for notification of failure |
|      19       |          SUCCESS_CONTENT           |  longtext  | 2147483647 |       0       |          Y           |      N      |               | The notification content was successfully customized. Procedure |
|      20       |            FAIL_CONTENT            |  longtext  | 2147483647 |       0       |          Y           |      N      |               |   The user-defined notification content failed. Procedure    |
|      21       |       WAIT_QUEUE_TIME_SECOND       |    int     |     10     |       0       |          Y           |      N      |     7200      |                    Maximum queue duration                    |
|      22       |           MAX_QUEUE_SIZE           |    int     |     10     |       0       |          Y           |      N      |      10       |                   Maximum number of queues                   |
|      23       |            IS_TEMPLATE             |    bit     |     1      |       0       |          Y           |      N      |     B '0'     |                      Template yes or no                      |
|      24       | SUCCESS_WECHAT_GROUP_MARKDOWN_FLAG |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The successful enterprise wechat group notification is converted to Markdown format switch |
|      25       |  FAIL_WECHAT_GROUP_MARKDOWN_FLAG   |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The enterprise wechat group notification fails to be converted to the Markdown format |
|      26       |        MAX_PIPELINE_RES_NUM        |    int     |     10     |       0       |          Y           |      N      |      500      |      Saves the maximum number of pipelined choreography      |
|      27       |     MAX_CON_RUNNING_QUEUE_SIZE     |    int     |     10     |       0       |          Y           |      N      |      50       |                       并发构建数量限制                       |
|      28       |           BUILD_NUM_RULE           |  varchar   |    512     |       0       |          Y           |      N      |               |                        构建号生成规则                        |

**Table name:** T_PIPELINE_SETTING_VERSION

**Pipeline** basic configuration version table

**Data column:**

| Serial number |                name                | Data type  |   length   | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :--------------------------------: | :--------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |                 ID                 |   bigint   |     20     |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |            PIPELINE_ID             |  varchar   |     34     |       0       |          N           |      N      |               |                         Pipeline ID                          |
|       3       |          SUCCESS_RECEIVER          | mediumtext |  16777215  |       0       |          Y           |      N      |               |                          成功接受者                          |
|       4       |           FAIL_RECEIVER            | mediumtext |  16777215  |       0       |          Y           |      N      |               |                          失败接受者                          |
|       5       |           SUCCESS_GROUP            | mediumtext |  16777215  |       0       |          Y           |      N      |               |                            成功组                            |
|       6       |             FAIL_GROUP             | mediumtext |  16777215  |       0       |          Y           |      N      |               |                            失败组                            |
|       7       |            SUCCESS_TYPE            |  varchar   |     32     |       0       |          Y           |      N      |               |                        成功的通知方式                        |
|       8       |             FAIL_TYPE              |  varchar   |     32     |       0       |          Y           |      N      |               |                  Failure notification mode                   |
|       9       |             PROJECT_ID             |  varchar   |     64     |       0       |          Y           |      N      |               |                           Item ID                            |
|      10       |     SUCCESS_WECHAT_GROUP_FLAG      |    bit     |     1      |       0       |          N           |      N      |     B '0'     |    Successful enterprise wechat group notification switch    |
|      11       |        SUCCESS_WECHAT_GROUP        |  varchar   |    1024    |       0       |          N           |      N      |               |   Successful enterprise wechat group notification group ID   |
|      12       |       FAIL_WECHAT_GROUP_FLAG       |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The enterprise wechat group notification switch failed. Procedure |
|      13       |         FAIL_WECHAT_GROUP          |  varchar   |    1024    |       0       |          N           |      N      |               | ID of the failed enterprise wechat group notification group  |
|      14       |        SUCCESS_DETAIL_FLAG         |    bit     |     1      |       0       |          Y           |      N      |     B '0'     | Pipeline details connection switch for successful notification |
|      15       |          FAIL_DETAIL_FLAG          |    bit     |     1      |       0       |          Y           |      N      |     B '0'     | Pipeline details connection switch for notification of failure |
|      16       |          SUCCESS_CONTENT           |  longtext  | 2147483647 |       0       |          Y           |      N      |               | The notification content was successfully customized. Procedure |
|      17       |            FAIL_CONTENT            |  longtext  | 2147483647 |       0       |          Y           |      N      |               |   The user-defined notification content failed. Procedure    |
|      18       |            IS_TEMPLATE             |    bit     |     1      |       0       |          Y           |      N      |     B '0'     |                      Template yes or no                      |
|      19       |              VERSION               |    int     |     10     |       0       |          N           |      N      |       1       |                        Version number                        |
|      20       | SUCCESS_WECHAT_GROUP_MARKDOWN_FLAG |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The successful enterprise wechat group notification is converted to Markdown format switch |
|      21       |  FAIL_WECHAT_GROUP_MARKDOWN_FLAG   |    bit     |     1      |       0       |          N           |      N      |     B '0'     | The enterprise wechat group notification fails to be converted to the Markdown format |

**Table name:** T_PIPELINE_STAGE_TAG

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |       ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |    Primary key     |
|       2       | STAGE_TAG_NAME |  varchar  |   45   |       0       |          N           |      N      |                   |  Stage label name  |
|       3       |     WEIGHT     |    int    |   10   |       0       |          N           |      N      |         0         | Phase label weight |
|       4       |    CREATOR     |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       5       |    MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |   Recent reviser   |
|       6       |  CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       7       |  UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Modification time  |

**Table name:** T_PIPELINE_TEMPLATE

Pipeline template table

**Data column:**

| Serial number |      name       | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |                 description                 |
| :-----------: | :-------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------------------------: |
|       1       |       ID        |   bigint   |    20    |       0       |          N           |      Y      |                   |               Primary key ID                |
|       2       |      TYPE       |  varchar   |    32    |       0       |          N           |      N      |      FREEDOM      |                    type                     |
|       3       |    CATEGORY     |  varchar   |   128    |       0       |          Y           |      N      |                   |            Application category             |
|       4       |  TEMPLATE_NAME  |  varchar   |    64    |       0       |          N           |      N      |                   |                Template name                |
|       5       |      ICON       |  varchar   |    32    |       0       |          N           |      N      |                   |                Template icon                |
|       6       |    LOGO_URL     |  varchar   |   512    |       0       |          Y           |      N      |                   |               LOGOURL address               |
|       7       |  PROJECT_CODE   |  varchar   |    32    |       0       |          Y           |      N      |                   | The project to which the user group belongs |
|       8       | SRC_TEMPLATE_ID |  varchar   |    32    |       0       |          Y           |      N      |                   |          ID of the source template          |
|       9       |     AUTHOR      |  varchar   |    64    |       0       |          N           |      N      |                   |                   author                    |
|      10       |     ATOMNUM     |    int     |    10    |       0       |          N           |      N      |                   |             Number of plug-ins              |
|      11       |   PUBLIC_FLAG   |    bit     |    1     |       0       |          N           |      N      |       B '0'       |        Whether it is a public mirror        |
|      12       |    TEMPLATE     | mediumtext | 16777215 |       0       |          Y           |      N      |                   |                  template                   |
|      13       |     CREATOR     |  varchar   |    32    |       0       |          N           |      N      |                   |                   founder                   |
|      14       |   CREATE_TIME   |  datetime  |    19    |       0       |          Y           |      N      | CURRENT_TIMESTAMP |                Creation time                |

**Table name:** T_PIPELINE_TIMER

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description  |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------: |
|       1       | PROJECT_ID  |  varchar  |   32   |       0       |          N           |      Y      |                   |    Item ID    |
|       2       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      Y      |                   |  Pipeline ID  |
|       3       |   CRONTAB   |  varchar  |  2048  |       0       |          N           |      N      |                   |    Task ID    |
|       4       |   CREATOR   |  varchar  |   64   |       0       |          N           |      N      |                   |    founder    |
|       5       | CREATE_TIME | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time |
|       6       |   CHANNEL   |  varchar  |   32   |       0       |          N           |      N      |        BS         |   项目渠道    |

**Table name:** T_PIPELINE_USER

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |               |  Pipeline ID   |
|       3       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       4       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
|       5       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |
|       6       | UPDATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    modifier    |

**Table name:** T_PIPELINE_VIEW

**Explanation:**

**Data column:**

| Serial number |          name          | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :--------------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       |           ID           |   bigint   |    20    |       0       |          N           |      Y      |               |  Primary key ID  |
|       2       |       PROJECT_ID       |  varchar   |    32    |       0       |          N           |      N      |               |     Item ID      |
|       3       |          NAME          |  varchar   |    64    |       0       |          N           |      N      |               |       name       |
|       4       | FILTER_BY_PIPEINE_NAME |  varchar   |   128    |       0       |          Y           |      N      |               | 流水线名称过滤器 |
|       5       |   FILTER_BY_CREATOR    |  varchar   |    64    |       0       |          Y           |      N      |               |   创建者过滤器   |
|       6       |      CREATE_TIME       |  datetime  |    19    |       0       |          N           |      N      |               |  Creation time   |
|       7       |      UPDATE_TIME       |  datetime  |    19    |       0       |          N           |      N      |               |   Update time    |
|       8       |      CREATE_USER       |  varchar   |    64    |       0       |          N           |      N      |               |     founder      |
|       9       |       IS_PROJECT       |    bit     |    1     |       0       |          Y           |      N      |     B '0'     |     是否项目     |
|      10       |         LOGIC          |  varchar   |    32    |       0       |          Y           |      N      |      AND      |      逻辑符      |
|      11       |        FILTERS         | mediumtext | 16777215 |       0       |          Y           |      N      |               |      过滤器      |

**Table name:** T_PIPELINE_VIEW_LABEL

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description  |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------: |
|       1       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID    |
|       2       |   VIEW_ID   |  bigint   |   20   |       0       |          N           |      Y      |               |    视图ID     |
|       3       |  LABEL_ID   |  bigint   |   20   |       0       |          N           |      Y      |               |    Tag ID     |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time |

**Table name:** T_PIPELINE_VIEW_PROJECT

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |   VIEW_ID   |  bigint   |   20   |       0       |          N           |      N      |               |    View ID     |
|       3       | PROJECT_ID  |  varchar  |   32   |       0       |          N           |      N      |               |    Item ID     |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       5       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
|       6       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    founder     |

**Table name:** T_PIPELINE_VIEW_USER_LAST_VIEW

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description  |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------: |
|       1       |   USER_ID   |  varchar  |   32   |       0       |          N           |      Y      |                   |    User ID    |
|       2       | PROJECT_ID  |  varchar  |   32   |       0       |          N           |      Y      |                   |    Item ID    |
|       3       |   VIEW_ID   |  varchar  |   64   |       0       |          N           |      N      |                   |    View ID    |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |                   | Creation time |
|       5       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time  |

**Table name:** T_PIPELINE_VIEW_USER_SETTINGS

**Explanation:**

**Data column:**

| Serial number |    name     | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |          description          |
| :-----------: | :---------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------: |
|       1       |   USER_ID   |  varchar   |   255    |       0       |          N           |      Y      |                   |            User ID            |
|       2       | PROJECT_ID  |  varchar   |    32    |       0       |          N           |      Y      |                   |            Item ID            |
|       3       |  SETTINGS   | mediumtext | 16777215 |       0       |          N           |      N      |                   | Attribute configuration table |
|       4       | CREATE_TIME |  datetime  |    19    |       0       |          N           |      N      |                   |         Creation time         |
|       5       | UPDATE_TIME |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |          Update time          |

**Table name:** T_PIPELINE_WEBHOOK

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |           description           |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------: |
|       1       | REPOSITORY_TYPE |  varchar  |   64   |       0       |          N           |      N      |               | The type of the new git plug-in |
|       2       |   PROJECT_ID    |  varchar  |   32   |       0       |          N           |      N      |               |             Item ID             |
|       3       |   PIPELINE_ID   |  varchar  |   34   |       0       |          N           |      N      |               |           Pipeline ID           |
|       4       |  REPO_HASH_ID   |  varchar  |   45   |       0       |          Y           |      N      |               |        Repository HASHID        |
|       5       |       ID        |  bigint   |   20   |       0       |          N           |      Y      |               |         Primary key ID          |
|       6       |    REPO_NAME    |  varchar  |  128   |       0       |          Y           |      N      |               |         Code base alias         |
|       7       |    REPO_TYPE    |  varchar  |   32   |       0       |          Y           |      N      |               |         Code base type          |
|       8       |  PROJECT_NAME   |  varchar  |  128   |       0       |          Y           |      N      |               |          Project name           |
|       9       |     TASK_ID     |  varchar  |   34   |       0       |          Y           |      N      |               |             Task id             |
|      10       |     DELETE      |    bit    |   1    |       0       |          Y           |      N      |     B '0'     |          Delete or not          |

**Table name:** T_PIPELINE_WEBHOOK_BUILD_LOG

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |       ID        |  bigint   |   20   |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       |    CODE_TYPE    |  varchar  |   32   |       0       |          N           |      N      |                   |   Code base type   |
|       3       |    REPO_NAME    |  varchar  |  128   |       0       |          N           |      N      |                   |  Code base alias   |
|       4       |    COMMIT_ID    |  varchar  |   64   |       0       |          N           |      N      |                   | Code submission ID |
|       5       | REQUEST_CONTENT |   text    | 65535  |       0       |          Y           |      N      |                   |   Event content    |
|       6       |  CREATED_TIME   | datetime  |   19   |       0       |          N           |      Y      | CURRENT_TIMESTAMP |   Creation time    |
|       7       |  RECEIVED_TIME  | datetime  |   19   |       0       |          N           |      N      |                   |   Reception time   |
|       8       |  FINISHED_TIME  | datetime  |   19   |       0       |          N           |      N      |                   |  Completion time   |

**Table name:** T_PIPELINE_WEBHOOK_BUILD_LOG_DETAIL

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       |     LOG_ID     |  bigint   |   20   |       0       |          N           |      N      |                   |                    |
|       3       |   CODE_TYPE    |  varchar  |   32   |       0       |          N           |      N      |                   |   Code base type   |
|       4       |   REPO_NAME    |  varchar  |  128   |       0       |          N           |      N      |                   |  Code base alias   |
|       5       |   COMMIT_ID    |  varchar  |   64   |       0       |          N           |      N      |                   | Code submission ID |
|       6       |   PROJECT_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |      Item ID       |
|       7       |  PIPELINE_ID   |  varchar  |   34   |       0       |          N           |      N      |                   |    Pipeline ID     |
|       8       |    TASK_ID     |  varchar  |   34   |       0       |          N           |      N      |                   |      Task id       |
|       9       |   TASK_NAME    |  varchar  |  128   |       0       |          Y           |      N      |                   |     Task name      |
|      10       |    SUCCESS     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |   Success or not   |
|      11       | TRIGGER_RESULT |   text    | 65535  |       0       |          Y           |      N      |                   |   Trigger result   |
|      12       |  CREATED_TIME  | datetime  |   19   |       0       |          N           |      Y      | CURRENT_TIMESTAMP |   Creation time    |

**Table name:** T_PIPELINE_WEBHOOK_QUEUE

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |       description        |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------: |
|       1       |        ID         |  bigint   |   20   |       0       |          N           |      Y      |                   |      Primary key ID      |
|       2       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |                   |         Item ID          |
|       3       |    PIPELINE_ID    |  varchar  |   64   |       0       |          N           |      N      |                   |       Pipeline ID        |
|       4       | SOURCE_PROJECT_ID |  bigint   |   20   |       0       |          N           |      N      |                   |      Source item ID      |
|       5       | SOURCE_REPO_NAME  |  varchar  |  255   |       0       |          N           |      N      |                   | Source code library name |
|       6       |   SOURCE_BRANCH   |  varchar  |  255   |       0       |          N           |      N      |                   |      Source branch       |
|       7       | TARGET_PROJECT_ID |  bigint   |   20   |       0       |          Y           |      N      |                   |      Target item ID      |
|       8       | TARGET_REPO_NAME  |  varchar  |  255   |       0       |          Y           |      N      |                   | Object code library name |
|       9       |   TARGET_BRANCH   |  varchar  |  255   |       0       |          Y           |      N      |                   |      Target branch       |
|      10       |     BUILD_ID      |  varchar  |   34   |       0       |          N           |      N      |                   |         Build ID         |
|      11       |    CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Creation time       |

**Table name:** T_PROJECT_PIPELINE_CALLBACK

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                   description                   |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------------------------------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |                 Primary key ID                  |
|       2       |  PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |                     Item ID                     |
|       3       |    EVENTS    |  varchar  |  255   |       0       |          Y           |      N      |               |                      event                      |
|       4       | CALLBACK_URL |  varchar  |  255   |       0       |          N           |      N      |               |              Callback url address               |
|       5       |   CREATOR    |  varchar  |   64   |       0       |          N           |      N      |               |                     founder                     |
|       6       |   UPDATOR    |  varchar  |   64   |       0       |          N           |      N      |               |                     updater                     |
|       7       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |                  Creation time                  |
|       8       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |                   Update time                   |
|       9       | SECRET_TOKEN |   text    | 65535  |       0       |          Y           |      N      |               | Sendtoyourwithhttpheader:X-DEVOPS-WEBHOOK-TOKEN |
|      10       |    ENABLE    |    bit    |   1    |       0       |          N           |      N      |     B '1'     |                     enable                      |

**Table name:** T_PROJECT_PIPELINE_CALLBACK_HISTORY

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       |   PROJECT_ID   |  varchar  |   64   |       0       |          N           |      N      |               |       Item ID        |
|       3       |     EVENTS     |  varchar  |  255   |       0       |          Y           |      N      |               |        event         |
|       4       |  CALLBACK_URL  |  varchar  |  255   |       0       |          N           |      N      |               | Callback url address |
|       5       |     STATUS     |  varchar  |   20   |       0       |          N           |      N      |               |        state         |
|       6       |   ERROR_MSG    |   text    | 65535  |       0       |          Y           |      N      |               |    misdescription    |
|       7       | REQUEST_HEADER |   text    | 65535  |       0       |          Y           |      N      |               |    Request header    |
|       8       |  REQUEST_BODY  |   text    | 65535  |       0       |          N           |      N      |               |     Request body     |
|       9       | RESPONSE_CODE  |    int    |   10   |       0       |          Y           |      N      |               |    Response code     |
|      10       | RESPONSE_BODY  |   text    | 65535  |       0       |          Y           |      N      |               |    Response body     |
|      11       |   START_TIME   | datetime  |   19   |       0       |          N           |      N      |               |      Start time      |
|      12       |    END_TIME    | datetime  |   19   |       0       |          N           |      N      |               |       End time       |
|      13       |  CREATED_TIME  | datetime  |   19   |       0       |          N           |      Y      |               |    Creation time     |

**Table name:** T_REPORT

Pipeline product table

**Data column:**

| Serial number |    name     | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |   bigint   |    20    |       0       |          N           |      Y      |               | Primary key ID |
|       2       | PROJECT_ID  |  varchar   |    32    |       0       |          N           |      N      |               |    Item ID     |
|       3       | PIPELINE_ID |  varchar   |    34    |       0       |          N           |      N      |               |  Pipeline ID   |
|       4       |  BUILD_ID   |  varchar   |    34    |       0       |          N           |      N      |               |    Build ID    |
|       5       | ELEMENT_ID  |  varchar   |    34    |       0       |          N           |      N      |               |   Atomic ID    |
|       6       |    TYPE     |  varchar   |    32    |       0       |          N           |      N      |   INTERNAL    |      type      |
|       7       | INDEX_FILE  | mediumtext | 16777215 |       0       |          N           |      N      |               |   Entry file   |
|       8       |    NAME     |    text    |  65535   |       0       |          N           |      N      |               |      name      |
|       9       | CREATE_TIME |  datetime  |    19    |       0       |          N           |      N      |               | Creation time  |
|      10       | UPDATE_TIME |  datetime  |    19    |       0       |          N           |      N      |               |  Update time   |

**Table name:** T_TEMPLATE

Pipeline template information table

**Data column:**

| Serial number |      name       | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |                 description                 |
| :-----------: | :-------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------------------: |
|       1       |     VERSION     |   bigint   |    20    |       0       |          N           |      Y      |               |               Primary key ID                |
|       2       |       ID        |  varchar   |    32    |       0       |          N           |      N      |               |               Primary key ID                |
|       3       |  TEMPLATE_NAME  |  varchar   |    64    |       0       |          N           |      N      |               |                Template name                |
|       4       |   PROJECT_ID    |  varchar   |    34    |       0       |          N           |      N      |               |                   Item ID                   |
|       5       |  VERSION_NAME   |  varchar   |    64    |       0       |          N           |      N      |               |                Version name                 |
|       6       |     CREATOR     |  varchar   |    64    |       0       |          N           |      N      |               |                   founder                   |
|       7       |  CREATED_TIME   |  datetime  |    19    |       0       |          Y           |      N      |               |                Creation time                |
|       8       |    TEMPLATE     | mediumtext | 16777215 |       0       |          Y           |      N      |               |                  template                   |
|       9       |      TYPE       |  varchar   |    32    |       0       |          N           |      N      |   CUSTOMIZE   |                    type                     |
|      10       |    CATEGORY     |  varchar   |   128    |       0       |          Y           |      N      |               |            Application category             |
|      11       |    LOGO_URL     |  varchar   |   512    |       0       |          Y           |      N      |               |               LOGOURL address               |
|      12       | SRC_TEMPLATE_ID |  varchar   |    32    |       0       |          Y           |      N      |               |          ID of the source template          |
|      13       |   STORE_FLAG    |    bit     |    1     |       0       |          Y           |      N      |     B '0'     | Whether it has been associated with a store |
|      14       |     WEIGHT      |    int     |    10    |       0       |          Y           |      N      |       0       |                   weight                    |

**Table name:** T_TEMPLATE_INSTANCE_BASE

Template real list basic information table

**Data column:**

| Serial number |            name            | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |           description            |
| :-----------: | :------------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :------------------------------: |
|       1       |             ID             |  varchar  |   32   |       0       |          N           |      Y      |                      |          Primary key ID          |
|       2       |        TEMPLATE_ID         |  varchar  |   32   |       0       |          Y           |      N      |                      |           Template ID            |
|       3       |      TEMPLATE_VERSION      |  varchar  |   32   |       0       |          N           |      N      |                      |         Template version         |
|       4       | USE_TEMPLATE_SETTINGS_FLAG |    bit    |   1    |       0       |          N           |      N      |                      |    Whether to use a template     |
|       5       |         PROJECT_ID         |  varchar  |   64   |       0       |          N           |      N      |                      |             Item ID              |
|       6       |       TOTAL_ITEM_NUM       |    int    |   10   |       0       |          N           |      N      |          0           |    Total number of instances     |
|       7       |      SUCCESS_ITEM_NUM      |    int    |   10   |       0       |          N           |      N      |          0           |  Number of successful instances  |
|       8       |       FAIL_ITEM_NUM        |    int    |   10   |       0       |          N           |      N      |          0           | Number of instantiation failures |
|       9       |           STATUS           |  varchar  |   32   |       0       |          N           |      N      |                      |              state               |
|      10       |          CREATOR           |  varchar  |   50   |       0       |          N           |      N      |        system        |             founder              |
|      11       |          MODIFIER          |  varchar  |   50   |       0       |          N           |      N      |        system        |             modifier             |
|      12       |        UPDATE_TIME         | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |        Modification time         |
|      13       |        CREATE_TIME         | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |          Creation time           |

**Table name:** T_TEMPLATE_INSTANCE_ITEM

Template real list item information table

**Data column:**

| Serial number |     name      | Data type  |  length  | Decimal place | Allowable null value | Primary key |    Default value     |              description               |
| :-----------: | :-----------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :------------------: | :------------------------------------: |
|       1       |      ID       |  varchar   |    32    |       0       |          N           |      Y      |                      |             Primary key ID             |
|       2       |  PROJECT_ID   |  varchar   |    64    |       0       |          N           |      N      |                      |                Item ID                 |
|       3       |  PIPELINE_ID  |  varchar   |    34    |       0       |          N           |      N      |                      |              Pipeline ID               |
|       4       | PIPELINE_NAME |  varchar   |   255    |       0       |          N           |      N      |                      |             Pipeline name              |
|       5       | BUILD_NO_INFO |  varchar   |   512    |       0       |          Y           |      N      |                      |        Build number information        |
|       6       |    STATUS     |  varchar   |    32    |       0       |          N           |      N      |                      |                 state                  |
|       7       |    BASE_ID    |  varchar   |    32    |       0       |          N           |      N      |                      | ID of the actualized basic information |
|       8       |     PARAM     | mediumtext | 16777215 |       0       |          Y           |      N      |                      |               parameter                |
|       9       |    CREATOR    |  varchar   |    50    |       0       |          N           |      N      |        system        |                founder                 |
|      10       |   MODIFIER    |  varchar   |    50    |       0       |          N           |      N      |        system        |                modifier                |
|      11       |  UPDATE_TIME  |  datetime  |    23    |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |           Modification time            |
|      12       |  CREATE_TIME  |  datetime  |    23    |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |             Creation time              |

**Table name:** T_TEMPLATE_PIPELINE

Pipeline template - instance mapping table

**Data column:**

| Serial number |       name       | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :--------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |    PROJECT_ID    |  varchar   |    64    |       0       |          N           |      N      |               |                           Item ID                            |
|       2       |   PIPELINE_ID    |  varchar   |    34    |       0       |          N           |      Y      |               |                         Pipeline ID                          |
|       3       |  INSTANCE_TYPE   |  varchar   |    32    |       0       |          N           |      N      |  CONSTRAINT   | Instantiation type: FREEDOM Free mode CONSTRAINT Constraint mode |
|       4       | ROOT_TEMPLATE_ID |  varchar   |    32    |       0       |          Y           |      N      |               |                      Source template ID                      |
|       5       |     VERSION      |   bigint   |    20    |       0       |          N           |      N      |               |                        Version number                        |
|       6       |   VERSION_NAME   |  varchar   |    64    |       0       |          N           |      N      |               |                         Version name                         |
|       7       |   TEMPLATE_ID    |  varchar   |    32    |       0       |          N           |      N      |               |                         Template ID                          |
|       8       |     CREATOR      |  varchar   |    64    |       0       |          N           |      N      |               |                           founder                            |
|       9       |     UPDATOR      |  varchar   |    64    |       0       |          N           |      N      |               |                           updater                            |
|      10       |   CREATED_TIME   |  datetime  |    19    |       0       |          N           |      N      |               |                        Creation time                         |
|      11       |   UPDATED_TIME   |  datetime  |    19    |       0       |          N           |      N      |               |                         Update time                          |
|      12       |     BUILD_NO     |    text    |  65535   |       0       |          Y           |      N      |               |                         Build number                         |
|      13       |      PARAM       | mediumtext | 16777215 |       0       |          Y           |      N      |               |                          parameter                           |
|      14       |     DELETED      |    bit     |    1     |       0       |          Y           |      N      |     B '0'     |               Pipelining has been soft deleted               |

|      |      |      |      |      |      |      |      |      |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
