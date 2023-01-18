# devops_ci_environment

**Database name:** devops_ci_environment

**Issue:** 1.0.0

**Documentation Description:** Database documentation for devops_ci_environment

|                          Table name                          |                 description                 |
| :----------------------------------------------------------: | :-----------------------------------------: |
|       [T_AGENT_FAILURE_NOTIFY_USER](broken-reference)        |                                             |
|           [T_AGENT_PIPELINE_REF](broken-reference)           |                                             |
|                  [T_ENV](broken-reference)                   |       Environmental information table       |
|       [T_ENVIRONMENT_AGENT_PIPELINE](broken-reference)       |                                             |
|       [T_ENVIRONMENT_SLAVE_GATEWAY](broken-reference)        |                                             |
|      [T_ENVIRONMENT_THIRDPARTY_AGENT](broken-reference)      | Third-party builder agent information table |
|  [T_ENVIRONMENT_THIRDPARTY_AGENT_ACTION](broken-reference)   |                                             |
| [T_ENVIRONMENT_THIRDPARTY_ENABLE_PROJECTS](broken-reference) |                                             |
|                [T_ENV_NODE](broken-reference)                |      Environment - Node mapping table       |
|           [T_ENV_SHARE_PROJECT](broken-reference)            |                                             |
|                  [T_NODE](broken-reference)                  |           Node information table            |
|             [T_PROJECT_CONFIG](broken-reference)             |                                             |

**Table name:** T_AGENT_FAILURE_NOTIFY_USER

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |   USER_ID    |  varchar  |   32   |       0       |          Y           |      N      |               |      User ID      |
|       3       | NOTIFY_TYPES |  varchar  |   32   |       0       |          Y           |      N      |               | Notification type |

**Table name:** T_AGENT_PIPELINE_REF

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       |       ID        |  bigint   |   20   |       0       |          N           |      Y      |               |    Primary key ID     |
|       2       |     NODE_ID     |  bigint   |   20   |       0       |          N           |      N      |               |        Node ID        |
|       3       |    AGENT_ID     |  bigint   |   20   |       0       |          N           |      N      |               |      Builder ID       |
|       4       |   PROJECT_ID    |  varchar  |   64   |       0       |          N           |      N      |               |        Item ID        |
|       5       |   PIPELINE_ID   |  varchar  |   34   |       0       |          N           |      N      |               |      Pipeline ID      |
|       6       |  PIEPLINE_NAME  |  varchar  |  255   |       0       |          N           |      N      |               |     Pipeline name     |
|       7       |    VM_SEQ_ID    |  varchar  |   34   |       0       |          Y           |      N      |               | Build sequence number |
|       8       |     JOB_ID      |  varchar  |   34   |       0       |          Y           |      N      |               |         JOBID         |
|       9       |    JOB_NAME     |  varchar  |  255   |       0       |          N           |      N      |               |        JOBNAME        |
|      10       | LAST_BUILD_TIME | datetime  |   19   |       0       |          N           |      N      |               |    Last build time    |

**Table name:** T_ENV

**Description:** Environment information table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                   description                   |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------------------------------------: |
|       1       |    ENV_ID    |  bigint   |   20   |       0       |          N           |      Y      |               |                 Primary key ID                  |
|       2       |  PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |                     Item ID                     |
|       3       |   ENV_NAME   |  varchar  |  128   |       0       |          N           |      N      |               |                Environment name                 |
|       4       |   ENV_DESC   |  varchar  |  128   |       0       |          N           |      N      |               |             Environment description             |
|       5       |   ENV_TYPE   |  varchar  |  128   |       0       |          N           |      N      |               | Environment type (development environment {DEV} |
|       6       |   ENV_VARS   |   text    | 65535  |       0       |          N           |      N      |               |              Environment variable               |
|       7       | CREATED_USER |  varchar  |   64   |       0       |          N           |      N      |               |                     founder                     |
|       8       | UPDATED_USER |  varchar  |   64   |       0       |          N           |      N      |               |                    modifier                     |
|       9       | CREATED_TIME | timestamp |   19   |       0       |          Y           |      N      |               |                  Creation time                  |
|      10       | UPDATED_TIME | timestamp |   19   |       0       |          Y           |      N      |               |                Modification time                |
|      11       |  IS_DELETED  |    bit    |   1    |       0       |          N           |      N      |               |                  Delete or not                  |

**Table name:** T_ENVIRONMENT_AGENT_PIPELINE

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |   AGENT_ID   |  bigint   |   20   |       0       |          N           |      N      |               |   Builder ID   |
|       3       |  PROJECT_ID  |  varchar  |   32   |       0       |          N           |      N      |               |    Item ID     |
|       4       |   USER_ID    |  varchar  |   32   |       0       |          N           |      N      |               |    User ID     |
|       5       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       6       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |
|       7       |    STATUS    |    int    |   10   |       0       |          N           |      N      |               |     state      |
|       8       |   PIPELINE   |  varchar  |  1024  |       0       |          N           |      N      |               |  PipelineType  |
|       9       |   RESPONSE   |   text    | 65535  |       0       |          Y           |      N      |               |                |

**Table name:** T_ENVIRONMENT_SLAVE_GATEWAY

**Explanation:**

**Data column:**

| Serial number |   name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description   |
| :-----------: | :-------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------: |
|       1       |    ID     |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID  |
|       2       |   NAME    |  varchar  |   32   |       0       |          N           |      N      |               |      name       |
|       3       | SHOW_NAME |  varchar  |   32   |       0       |          N           |      N      |               |  Display name   |
|       4       |  GATEWAY  |  varchar  |  127   |       0       |          Y           |      N      |               | Gateway address |

**Table name:** T_ENVIRONMENT_THIRDPARTY_AGENT

**Note:** third-party builder agent information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |        description         |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------------: |
|       1       |         ID          |  bigint   |   20   |       0       |          N           |      Y      |               |       Primary key ID       |
|       2       |       NODE_ID       |  bigint   |   20   |       0       |          Y           |      N      |               |          Node ID           |
|       3       |     PROJECT_ID      |  varchar  |   64   |       0       |          N           |      N      |               |          Item ID           |
|       4       |      HOSTNAME       |  varchar  |  128   |       0       |          Y           |      N      |               |         Host name          |
|       5       |         IP          |  varchar  |   64   |       0       |          Y           |      N      |               |         ip address         |
|       6       |         OS          |  varchar  |   16   |       0       |          N           |      N      |               |      Operating system      |
|       7       |      DETECT_OS      |  varchar  |  128   |       0       |          Y           |      N      |               | Detection operating system |
|       8       |       STATUS        |    int    |   10   |       0       |          N           |      N      |               |           state            |
|       9       |     SECRET_KEY      |  varchar  |  256   |       0       |          N           |      N      |               |            key             |
|      10       |    CREATED_USER     |  varchar  |   64   |       0       |          N           |      N      |               |          founder           |
|      11       |    CREATED_TIME     | datetime  |   19   |       0       |          N           |      N      |               |       Creation time        |
|      12       |   START_REMOTE_IP   |  varchar  |   64   |       0       |          Y           |      N      |               |          Host IP           |
|      13       |       GATEWAY       |  varchar  |  256   |       0       |          Y           |      N      |               |   Target service gateway   |
|      14       |       VERSION       |  varchar  |  128   |       0       |          Y           |      N      |               |       Version number       |
|      15       |   MASTER_VERSION    |  varchar  |  128   |       0       |          Y           |      N      |               |       Major version        |
|      16       | PARALLEL_TASK_COUNT |    int    |   10   |       0       |          Y           |      N      |               |   Parallel task counting   |
|      17       | AGENT_INSTALL_PATH  |  varchar  |  512   |       0       |          Y           |      N      |               | Builder installation path  |
|      18       |    STARTED_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |         initiator          |
|      19       |     AGENT_ENVS      |   text    | 65535  |       0       |          Y           |      N      |               |    Environment variable    |
|      20       |    FILE_GATEWAY     |  varchar  |  256   |       0       |          Y           |      N      |               |     File gateway path      |

**Table name:** T_ENVIRONMENT_THIRDPARTY_AGENT_ACTION

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |  AGENT_ID   |  bigint   |   20   |       0       |          N           |      N      |               |   Builder ID   |
|       3       | PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID     |
|       4       |   ACTION    |  varchar  |   64   |       0       |          N           |      N      |               |   operation    |
|       5       | ACTION_TIME | datetime  |   19   |       0       |          N           |      N      |               | Operating time |

**Table name:** T_ENVIRONMENT_THIRDPARTY_ENABLE_PROJECTS

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description  |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------: |
|       1       |  PROJECT_ID  |  varchar  |   64   |       0       |          N           |      Y      |               |    Item ID    |
|       2       |    ENALBE    |    bit    |   1    |       0       |          Y           |      N      |               | Enable or not |
|       3       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time |
|       4       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time  |

**Table name:** T_ENV_NODE

**Environment-node** mapping table

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |   ENV_ID   |  bigint   |   20   |       0       |          N           |      Y      |               | Environment ID |
|       2       |  NODE_ID   |  bigint   |   20   |       0       |          N           |      Y      |               |    Node ID     |
|       3       | PROJECT_ID |  varchar  |   64   |       0       |          N           |      N      |               |    Item ID     |

**Table name:** T_ENV_SHARE_PROJECT

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |         description          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------------: |
|       1       |       ENV_ID        |  bigint   |   20   |       0       |          N           |      Y      |               |        Environment ID        |
|       2       |      ENV_NAME       |  varchar  |  128   |       0       |          N           |      N      |               |       Environment name       |
|       3       |   MAIN_PROJECT_ID   |  varchar  |   64   |       0       |          N           |      Y      |               |       Main project ID        |
|       4       |  SHARED_PROJECT_ID  |  varchar  |   64   |       0       |          N           |      Y      |               | The shared target project ID |
|       5       | SHARED_PROJECT_NAME |  varchar  |  1024  |       0       |          Y           |      N      |               |     Target project name      |
|       6       |        TYPE         |  varchar  |   64   |       0       |          N           |      N      |               |             type             |
|       7       |       CREATOR       |  varchar  |   64   |       0       |          N           |      N      |               |           founder            |
|       8       |     CREATE_TIME     | timestamp |   19   |       0       |          Y           |      N      |               |        Creation time         |
|       9       |     UPDATE_TIME     | timestamp |   19   |       0       |          Y           |      N      |               |         Update time          |

**Table name:** T_NODE

**Note:** Node information table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |            description            |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------: |
|       1       |      NODE_ID       |  bigint   |   20   |       0       |          N           |      Y      |               |   Node ID ID of the primary key   |
|       2       |   NODE_STRING_ID   |  varchar  |   32   |       0       |          Y           |      N      |               |          Node ID string           |
|       3       |     PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |               |              Item ID              |
|       4       |      NODE_IP       |  varchar  |   64   |       0       |          N           |      N      |               |              Node IP              |
|       5       |     NODE_NAME      |  varchar  |   64   |       0       |          N           |      N      |               |             Node name             |
|       6       |    NODE_STATUS     |  varchar  |   64   |       0       |          N           |      N      |               |            Node state             |
|       7       |     NODE_TYPE      |  varchar  |   64   |       0       |          N           |      N      |               |             Node type             |
|       8       |  NODE_CLUSTER_ID   |  varchar  |  128   |       0       |          Y           |      N      |               |            Cluster ID             |
|       9       |   NODE_NAMESPACE   |  varchar  |  128   |       0       |          Y           |      N      |               |          Node namespace           |
|      10       |    CREATED_USER    |  varchar  |   64   |       0       |          N           |      N      |               |              founder              |
|      11       |    CREATED_TIME    | timestamp |   19   |       0       |          Y           |      N      |               |           Creation time           |
|      12       |    EXPIRE_TIME     | timestamp |   19   |       0       |          Y           |      N      |               |          Expiration time          |
|      13       |      OS_NAME       |  varchar  |  128   |       0       |          Y           |      N      |               |       Operating system name       |
|      14       |      OPERATOR      |  varchar  |  256   |       0       |          Y           |      N      |               |             operator              |
|      15       |    BAK_OPERATOR    |  varchar  |  256   |       0       |          Y           |      N      |               |           Backup owner            |
|      16       |    AGENT_STATUS    |    bit    |   1    |       0       |          Y           |      N      |               |           Builder state           |
|      17       |    DISPLAY_NAME    |  varchar  |  128   |       0       |          N           |      N      |               |               alias               |
|      18       |       IMAGE        |  varchar  |  512   |       0       |          Y           |      N      |               |           Mirror image            |
|      19       |      TASK_ID       |  bigint   |   20   |       0       |          Y           |      N      |               |              Task id              |
|      20       |  LAST_MODIFY_TIME  | timestamp |   19   |       0       |          Y           |      N      |               |        Last revision time         |
|      21       |  LAST_MODIFY_USER  |  varchar  |  512   |       0       |          Y           |      N      |               |          Recent modifier          |
|      22       |       BIZ_ID       |  bigint   |   20   |       0       |          Y           |      N      |               |       Subordinate business        |
|      23       | PIPELINE_REF_COUNT |    int    |   10   |       0       |          N           |      N      |       0       | Number of pipeline Job references |
|      24       |  LAST_BUILD_TIME   | datetime  |   19   |       0       |          Y           |      N      |               |          Last build time          |

**Table name:** T_PROJECT_CONFIG

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      Y      |               |      Item ID      |
|       2       |   UPDATED_USER    |  varchar  |   64   |       0       |          N           |      N      |               |     modifier      |
|       3       |   UPDATED_TIME    | timestamp |   19   |       0       |          Y           |      N      |               | Modification time |
|       4       |   BCSVM_ENALBED   |    bit    |   1    |       0       |          N           |      N      |     B '0'     |                   |
|       5       |    BCSVM_QUOTA    |    int    |   10   |       0       |          N           |      N      |       0       |                   |
|       6       |   IMPORT_QUOTA    |    int    |   10   |       0       |          N           |      N      |      30       |                   |
|       7       | DEV_CLOUD_ENALBED |    bit    |   1    |       0       |          N           |      N      |     B '0'     |                   |
|       8       |  DEV_CLOUD_QUOTA  |    int    |   10   |       0       |          N           |      N      |       0       |                   |
