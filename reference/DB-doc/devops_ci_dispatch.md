# devops_ci_dispatch

**Database name:** devops_ci_dispatch

**Issue:** 1.0.0

**Documentation Description:** Database documentation for devops_ci_dispatch

|                         Table name                         |                     description                     |
| :--------------------------------------------------------: | :-------------------------------------------------: |
|           [T_DISPATCH_MACHINE](broken-reference)           |                                                     |
|       [T_DISPATCH_PIPELINE_BUILD](broken-reference)        |                                                     |
|    [T_DISPATCH_PIPELINE_DOCKER_BUILD](broken-reference)    |                                                     |
|    [T_DISPATCH_PIPELINE_DOCKER_DEBUG](broken-reference)    |                                                     |
|   [T_DISPATCH_PIPELINE_DOCKER_ENABLE](broken-reference)    |                                                     |
|    [T_DISPATCH_PIPELINE_DOCKER_HOST](broken-reference)     |                                                     |
|  [T_DISPATCH_PIPELINE_DOCKER_HOST_ZONE](broken-reference)  |                                                     |
|   [T_DISPATCH_PIPELINE_DOCKER_IP_INFO](broken-reference)   |              DOCKER builder load table              |
|    [T_DISPATCH_PIPELINE_DOCKER_POOL](broken-reference)     |      DOCKER Concurrent build pool status table      |
|    [T_DISPATCH_PIPELINE_DOCKER_TASK](broken-reference)     |                                                     |
| [T_DISPATCH_PIPELINE_DOCKER_TASK_DRIFT](broken-reference)  |       DOCKER builds a task drift record table       |
| [T_DISPATCH_PIPELINE_DOCKER_TASK_SIMPLE](broken-reference) |            DOCKER builds the task table             |
|  [T_DISPATCH_PIPELINE_DOCKER_TEMPLATE](broken-reference)   |                                                     |
|         [T_DISPATCH_PIPELINE_VM](broken-reference)         |                                                     |
|         [T_DISPATCH_PRIVATE_VM](broken-reference)          |                                                     |
|      [T_DISPATCH_PROJECT_RUN_TIME](broken-reference)       | The amount used in the current month of the project |
|      [T_DISPATCH_PROJECT_SNAPSHOT](broken-reference)       |                                                     |
|        [T_DISPATCH_QUOTA_PROJECT](broken-reference)        |                    Project quota                    |
|        [T_DISPATCH_QUOTA_SYSTEM](broken-reference)         |                    System quota                     |
|        [T_DISPATCH_RUNNING_JOBS](broken-reference)         |                     Running JOB                     |
|   [T_DISPATCH_THIRDPARTY_AGENT_BUILD](broken-reference)    |                                                     |
|             [T_DISPATCH_VM](broken-reference)              |                                                     |
|           [T_DISPATCH_VM_TYPE](broken-reference)           |                                                     |
|       [T_DOCKER_RESOURCE_OPTIONS](broken-reference)        |               docker base quota table               |

**Table name:** T_DISPATCH_MACHINE

**Explanation:**

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |             description             |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------------------------: |
|       1       |      MACHINE_ID      |    int    |   10   |       0       |          N           |      Y      |               |             Machine ID              |
|       2       |      MACHINE_IP      |  varchar  |  128   |       0       |          N           |      N      |               |         Machine ip address          |
|       3       |     MACHINE_NAME     |  varchar  |  128   |       0       |          N           |      N      |               |            Machine name             |
|       4       |   MACHINE_USERNAME   |  varchar  |  128   |       0       |          N           |      N      |               |          Machine user name          |
|       5       |   MACHINE_PASSWORD   |  varchar  |  128   |       0       |          N           |      N      |               |           Machine cipher            |
|       6       | MACHINE_CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |        Machine creation time        |
|       7       | MACHINE_UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |      Machine modification time      |
|       8       |    CURRENT_VM_RUN    |    int    |   10   |       0       |          N           |      N      |       0       | Indicates the number of running VMS |
|       9       |      MAX_VM_RUN      |    int    |   10   |       0       |          N           |      N      |       1       |    Maximum number of VMS allowed    |

**Table name:** T_DISPATCH_PIPELINE_BUILD

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |    Primary key ID     |
|       2       |  PROJECT_ID  |  varchar  |   32   |       0       |          N           |      N      |               |        Item ID        |
|       3       | PIPELINE_ID  |  varchar  |   34   |       0       |          N           |      N      |               |      Pipeline ID      |
|       4       |   BUILD_ID   |  varchar  |   34   |       0       |          N           |      N      |               |       Build ID        |
|       5       |  VM_SEQ_ID   |  varchar  |   34   |       0       |          N           |      N      |               | Build sequence number |
|       6       |    VM_ID     |  bigint   |   20   |       0       |          N           |      N      |               |         Vm ID         |
|       7       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |     Creation time     |
|       8       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |      Update time      |
|       9       |    STATUS    |    int    |   10   |       0       |          N           |      N      |               |         state         |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_BUILD

**Explanation:**

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |             description              |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |               |            Primary key ID            |
|       2       |     BUILD_ID     |  varchar  |   64   |       0       |          N           |      N      |               |               Build ID               |
|       3       |    VM_SEQ_ID     |    int    |   10   |       0       |          N           |      N      |               |        Build sequence number         |
|       4       |    SECRET_KEY    |  varchar  |   64   |       0       |          N           |      N      |               |                 key                  |
|       5       |      STATUS      |    int    |   10   |       0       |          N           |      N      |               |                state                 |
|       6       |   CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |            Creation time             |
|       7       |   UPDATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |             Update time              |
|       8       |       ZONE       |  varchar  |  128   |       0       |          Y           |      N      |               |          Builder territory           |
|       9       |    PROJECT_ID    |  varchar  |   34   |       0       |          Y           |      N      |               |               Item ID                |
|      10       |   PIPELINE_ID    |  varchar  |   34   |       0       |          Y           |      N      |               |             Pipeline ID              |
|      11       | DISPATCH_MESSAGE |  varchar  |  4096  |       0       |          Y           |      N      |               |            Send a message            |
|      12       | STARTUP_MESSAGE  |   text    | 65535  |       0       |          Y           |      N      |               |          Start information           |
|      13       |    ROUTE_KEY     |  varchar  |   64   |       0       |          Y           |      N      |               | The routing KEY of the message queue |
|      14       |  DOCKER_INST_ID  |  bigint   |   20   |       0       |          Y           |      N      |               |                                      |
|      15       |    VERSION_ID    |    int    |   10   |       0       |          Y           |      N      |               |              Version ID              |
|      16       |   TEMPLATE_ID    |    int    |   10   |       0       |          Y           |      N      |               |             Template ID              |
|      17       |   NAMESPACE_ID   |  bigint   |   20   |       0       |          Y           |      N      |               |             Namespace ID             |
|      18       |    DOCKER_IP     |  varchar  |   64   |       0       |          Y           |      N      |               |              Builder IP              |
|      19       |   CONTAINER_ID   |  varchar  |  128   |       0       |          Y           |      N      |               |          Build container ID          |
|      20       |     POOL_NO      |    int    |   10   |       0       |          Y           |      N      |       0       |     Build container pool number      |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_DEBUG

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                       description                       |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------------------------------: |
|       1       |        ID         |  bigint   |   20   |       0       |          N           |      Y      |               |                     Primary key ID                      |
|       2       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |               |                         Item ID                         |
|       3       |    PIPELINE_ID    |  varchar  |   34   |       0       |          N           |      N      |               |                       Pipeline ID                       |
|       4       |     VM_SEQ_ID     |  varchar  |   34   |       0       |          N           |      N      |               |                  Build sequence number                  |
|       5       |      POOL_NO      |    int    |   10   |       0       |          N           |      N      |       0       |                    Build pool number                    |
|       6       |      STATUS       |    int    |   10   |       0       |          N           |      N      |               |                          state                          |
|       7       |       TOKEN       |  varchar  |  128   |       0       |          Y           |      N      |               |                          TOKEN                          |
|       8       |    IMAGE_NAME     |  varchar  |  1024  |       0       |          N           |      N      |               |                       Image name                        |
|       9       |     HOST_TAG      |  varchar  |  128   |       0       |          Y           |      N      |               |                       Host label                        |
|      10       |   CONTAINER_ID    |  varchar  |  128   |       0       |          Y           |      N      |               |                   Build container ID                    |
|      11       |   CREATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |                      Creation time                      |
|      12       |   UPDATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |                    Modification time                    |
|      13       |       ZONE        |  varchar  |  128   |       0       |          Y           |      N      |               |                    Builder territory                    |
|      14       |     BUILD_ENV     |  varchar  |  4096  |       0       |          Y           |      N      |               |              Builder environment variables              |
|      15       |   REGISTRY_USER   |  varchar  |  128   |       0       |          Y           |      N      |               |                  Registered user name                   |
|      16       |   REGISTRY_PWD    |  varchar  |  128   |       0       |          Y           |      N      |               |                Registered user password                 |
|      17       |    IMAGE_TYPE     |  varchar  |  128   |       0       |          Y           |      N      |               |                       Mirror type                       |
|      18       | IMAGE_PUBLIC_FLAG |    bit    |   1    |       0       |          Y           |      N      |               |    Whether the mirror is a public mirror: 0 No 1 Yes    |
|      19       |   IMAGE_RD_TYPE   |    bit    |   1    |       0       |          Y           |      N      |               | Image development source: 0 self-research 1 third party |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_ENABLE

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       | PIPELINE_ID |  varchar  |   64   |       0       |          N           |      Y      |               |      Pipeline ID      |
|       2       |   ENABLE    |    bit    |   1    |       0       |          N           |      N      |       0       |     Enable or not     |
|       3       |  VM_SEQ_ID  |    int    |   10   |       0       |          N           |      Y      |      - 1      | Build sequence number |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_HOST

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                 description                 |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------------------: |
|       1       | PROJECT_CODE |  varchar  |  128   |       0       |          N           |      Y      |               | The project to which the user group belongs |
|       2       |   HOST_IP    |  varchar  |  128   |       0       |          N           |      Y      |               |                   Host ip                   |
|       3       |    REMARK    |  varchar  |  1024  |       0       |          Y           |      N      |               |                   comment                   |
|       4       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |                Creation time                |
|       5       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |                 Update time                 |
|       6       |     TYPE     |    int    |   10   |       0       |          N           |      N      |       0       |                    type                     |
|       7       |  ROUTE_KEY   |  varchar  |   45   |       0       |          Y           |      N      |               |    The routing KEY of the message queue     |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_HOST_ZONE

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |             description              |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------: |
|       1       |   HOST_IP    |  varchar  |  128   |       0       |          N           |      Y      |               |               Host ip                |
|       2       |     ZONE     |  varchar  |  128   |       0       |          N           |      N      |               |          Builder territory           |
|       3       |    ENABLE    |    bit    |   1    |       0       |          Y           |      N      |       1       |            Enable or not             |
|       4       |    REMARK    |  varchar  |  1024  |       0       |          Y           |      N      |               |               comment                |
|       5       | CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |            Creation time             |
|       6       | UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |             Update time              |
|       7       |     TYPE     |    int    |   10   |       0       |          N           |      N      |       0       |                 type                 |
|       8       |  ROUTE_KEY   |  varchar  |   45   |       0       |          Y           |      N      |               | The routing KEY of the message queue |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_IP_INFO

**DOCKER** builder load table

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                  description                  |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------------------------------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |                   |                  Primary key                  |
|       2       |    DOCKER_IP     |  varchar  |   64   |       0       |          N           |      N      |                   |                   DOCKERIP                    |
|       3       | DOCKER_HOST_PORT |    int    |   10   |       0       |          N           |      N      |        80         |                  DOCKERPORT                   |
|       4       |     CAPACITY     |    int    |   10   |       0       |          N           |      N      |         0         |       Total capacity of node containers       |
|       5       |     USED_NUM     |    int    |   10   |       0       |          N           |      N      |         0         |       Used capacity of a node container       |
|       6       |     CPU_LOAD     |    int    |   10   |       0       |          N           |      N      |         0         |            Node container CPU load            |
|       7       |     MEM_LOAD     |    int    |   10   |       0       |          N           |      N      |         0         |            Node container MEM load            |
|       8       |    DISK_LOAD     |    int    |   10   |       0       |          N           |      N      |         0         |           Node container DISK load            |
|       9       |   DISK_IO_LOAD   |    int    |   10   |       0       |          N           |      N      |         0         |          Node container DISKIO load           |
|      10       |      ENABLE      |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |         Whether the node is available         |
|      11       |    SPECIAL_ON    |    bit    |   1    |       0       |          Y           |      N      |       B '0'       | Whether the node is used as a private machine |
|      12       |     GRAY_ENV     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |           Whether it is a gray node           |
|      13       |   CLUSTER_NAME   |  varchar  |   64   |       0       |          Y           |      N      |      COMMON       |              Build cluster type               |
|      14       |    GMT_CREATE    | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |                 Creation time                 |
|      15       |   GMT_MODIFIED   | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |               Modification time               |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_POOL

**DOCKER** concurrent build pool status table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description      |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |                   |      Primary key      |
|       2       | PIPELINE_ID  |  varchar  |   64   |       0       |          N           |      N      |                   |      Pipeline ID      |
|       3       |    VM_SEQ    |  varchar  |   64   |       0       |          N           |      N      |                   | Builder serial number |
|       4       |   POOL_NO    |    int    |   10   |       0       |          N           |      N      |         0         |   Build pool number   |
|       5       |    STATUS    |    int    |   10   |       0       |          N           |      N      |         0         |   Build pool state    |
|       6       |  GMT_CREATE  | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |     Creation time     |
|       7       | GMT_MODIFIED | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |   Modification time   |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_TASK

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                       description                       |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------------------------------: |
|       1       |        ID         |  bigint   |   20   |       0       |          N           |      Y      |               |                     Primary key ID                      |
|       2       |    PROJECT_ID     |  varchar  |   64   |       0       |          N           |      N      |               |                         Item ID                         |
|       3       |     AGENT_ID      |  varchar  |   32   |       0       |          N           |      N      |               |                       Builder ID                        |
|       4       |    PIPELINE_ID    |  varchar  |   34   |       0       |          N           |      N      |               |                       Pipeline ID                       |
|       5       |     BUILD_ID      |  varchar  |   34   |       0       |          N           |      N      |               |                        Build ID                         |
|       6       |     VM_SEQ_ID     |    int    |   10   |       0       |          N           |      N      |               |                  Build sequence number                  |
|       7       |      STATUS       |    int    |   10   |       0       |          N           |      N      |               |                          state                          |
|       8       |    SECRET_KEY     |  varchar  |  128   |       0       |          N           |      N      |               |                           key                           |
|       9       |    IMAGE_NAME     |  varchar  |  1024  |       0       |          N           |      N      |               |                       Image name                        |
|      10       |   CHANNEL_CODE    |  varchar  |  128   |       0       |          Y           |      N      |               |         Channel number. The default value is DS         |
|      11       |     HOST_TAG      |  varchar  |  128   |       0       |          Y           |      N      |               |                       Host label                        |
|      12       |   CONTAINER_ID    |  varchar  |  128   |       0       |          Y           |      N      |               |                   Build container ID                    |
|      13       |   CREATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |                      Creation time                      |
|      14       |   UPDATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |                       Update time                       |
|      15       |       ZONE        |  varchar  |  128   |       0       |          Y           |      N      |               |                    Builder territory                    |
|      16       |   REGISTRY_USER   |  varchar  |  128   |       0       |          Y           |      N      |               |                  Registered user name                   |
|      17       |   REGISTRY_PWD    |  varchar  |  128   |       0       |          Y           |      N      |               |                Registered user password                 |
|      18       |    IMAGE_TYPE     |  varchar  |  128   |       0       |          Y           |      N      |               |                       Mirror type                       |
|      19       | CONTAINER_HASH_ID |  varchar  |  128   |       0       |          Y           |      N      |               |             Build Job unique identification             |
|      20       | IMAGE_PUBLIC_FLAG |    bit    |   1    |       0       |          Y           |      N      |               |    Whether the mirror is a public mirror: 0 No 1 Yes    |
|      21       |   IMAGE_RD_TYPE   |    bit    |   1    |       0       |          Y           |      N      |               | Image development source: 0 self-research 1 third party |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_TASK_DRIFT

**DOCKER** construct task drift record table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |               description               |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------------------------------: |
|       1       |         ID         |  bigint   |   20   |       0       |          N           |      Y      |                   |               Primary key               |
|       2       |    PIPELINE_ID     |  varchar  |   64   |       0       |          N           |      N      |                   |               Pipeline ID               |
|       3       |      BUILD_ID      |  varchar  |   64   |       0       |          N           |      N      |                   |                Build ID                 |
|       4       |       VM_SEQ       |  varchar  |   64   |       0       |          N           |      N      |                   |          Builder serial number          |
|       5       |   OLD_DOCKER_IP    |  varchar  |   64   |       0       |          N           |      N      |                   |      IP of the old build container      |
|       6       |   NEW_DOCKER_IP    |  varchar  |   64   |       0       |          N           |      N      |                   | IP address of the newly built container |
|       7       | OLD_DOCKER_IP_INFO |  varchar  |  1024  |       0       |          N           |      N      |                   |          Old container IP load          |
|       8       |     GMT_CREATE     | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |              Creation time              |
|       9       |    GMT_MODIFIED    | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |            Modification time            |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_TASK_SIMPLE

**DOCKER** builds the task table

**Data column:**

| Serial number |          name          | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |        description        |
| :-----------: | :--------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------: |
|       1       |           ID           |  bigint   |   20   |       0       |          N           |      Y      |                   |        Primary key        |
|       2       |      PIPELINE_ID       |  varchar  |   64   |       0       |          N           |      N      |                   |        Pipeline ID        |
|       3       |         VM_SEQ         |  varchar  |   64   |       0       |          N           |      N      |                   |   Builder serial number   |
|       4       |       DOCKER_IP        |  varchar  |   64   |       0       |          N           |      N      |                   |    Build container IP     |
|       5       | DOCKER_RESOURCE_OPTION |    int    |   10   |       0       |          N           |      N      |         0         | Build resource allocation |
|       6       |       GMT_CREATE       | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |       Creation time       |
|       7       |      GMT_MODIFIED      | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |     Modification time     |

**Table name:** T_DISPATCH_PIPELINE_DOCKER_TEMPLATE

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description   |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------: |
|       1       |        ID         |    int    |   10   |       0       |          N           |      Y      |               | Primary key ID  |
|       2       |    VERSION_ID     |    int    |   10   |       0       |          N           |      N      |               |   Version ID    |
|       3       |  SHOW_VERSION_ID  |    int    |   10   |       0       |          N           |      N      |               |                 |
|       4       | SHOW_VERSION_NAME |  varchar  |   64   |       0       |          N           |      N      |               |  Version name   |
|       5       |   DEPLOYMENT_ID   |    int    |   10   |       0       |          N           |      N      |               |  Deployment ID  |
|       6       |  DEPLOYMENT_NAME  |  varchar  |   64   |       0       |          N           |      N      |               | Deployment name |
|       7       |     CC_APP_ID     |  bigint   |   20   |       0       |          N           |      N      |               | Application ID  |
|       8       |  BCS_PROJECT_ID   |  varchar  |   64   |       0       |          N           |      N      |               |                 |
|       9       |    CLUSTER_ID     |  varchar  |   64   |       0       |          N           |      N      |               |   Cluster ID    |
|      10       |   CREATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |  Creation time  |

**Table name:** T_DISPATCH_PIPELINE_VM

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       | PIPELINE_ID |  varchar  |   64   |       0       |          N           |      Y      |               |      Pipeline ID      |
|       2       |  VM_NAMES   |   text    | 65535  |       0       |          N           |      N      |               |        VM name        |
|       3       |  VM_SEQ_ID  |    int    |   10   |       0       |          N           |      Y      |      - 1      | Build sequence number |

**Table name:** T_DISPATCH_PRIVATE_VM

**Explanation:**

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value | description |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------: |
|       1       |   VM_ID    |    int    |   10   |       0       |          N           |      Y      |               |    VMID     |
|       2       | PROJECT_ID |  varchar  |   64   |       0       |          N           |      N      |               |   Item ID   |

**Table name:** T_DISPATCH_PROJECT_RUN_TIME

**Description:** The amount used in the current month of the project

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value | description  |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------: |
|       1       | PROJECT_ID  |  varchar  |  128   |       0       |          N           |      Y      |               |   Item ID    |
|       2       |   VM_TYPE   |  varchar  |  128   |       0       |          N           |      Y      |               |   VM type    |
|       3       |  RUN_TIME   |  bigint   |   20   |       0       |          N           |      N      |               | Running time |
|       4       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      |               | Update time  |

**Table name:** T_DISPATCH_PROJECT_SNAPSHOT

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description     |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------: |
|       1       |     PROJECT_ID      |  varchar  |   64   |       0       |          N           |      Y      |               |       Item ID       |
|       2       | VM_STARTUP_SNAPSHOT |  varchar  |   64   |       0       |          N           |      N      |               | VM startup snapshot |

**Table name:** T_DISPATCH_QUOTA_PROJECT

**Description:** Project quota

**Data column:**

| Serial number |           name           | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                   description                    |
| :-----------: | :----------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------: |
|       1       |        PROJECT_ID        |  varchar  |  128   |       0       |          N           |      Y      |               |                     Item ID                      |
|       2       |         VM_TYPE          |  varchar  |  128   |       0       |          N           |      Y      |               |                     VM type                      |
|       3       |     RUNNING_JOBS_MAX     |    int    |   10   |       0       |          N           |      N      |               | Maximum number of concurrent jobs of the project |
|       4       |   RUNNING_TIME_JOB_MAX   |    int    |   10   |       0       |          N           |      N      |               |     Maximum execution time of a project JOB      |
|       5       | RUNNING_TIME_PROJECT_MAX |    int    |   10   |       0       |          N           |      N      |               |    Maximum execution time of all project jobs    |
|       6       |       CREATED_TIME       | datetime  |   19   |       0       |          N           |      N      |               |                  Creation time                   |
|       7       |       UPDATED_TIME       | datetime  |   19   |       0       |          N           |      N      |               |                   Update time                    |
|       8       |         OPERATOR         |  varchar  |  128   |       0       |          N           |      N      |               |                     operator                     |

**Table name:** T_DISPATCH_QUOTA_SYSTEM

**Note:** System quota

**Data column:**

| Serial number |                name                | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :--------------------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |              VM_TYPE               |  varchar  |  128   |       0       |          N           |      Y      |               |                         Builder type                         |
|       2       |      RUNNING_JOBS_MAX_SYSTEM       |    int    |   10   |       0       |          N           |      N      |               |  Maximum number of concurrent jobs in a BKCI system   |
|       3       |      RUNNING_JOBS_MAX_PROJECT      |    int    |   10   |       0       |          N           |      N      |               | Default maximum number of concurrent jobs for a single project |
|       4       |        RUNNING_TIME_JOB_MAX        |    int    |   10   |       0       |          N           |      N      |               |    By default, the maximum execution time of a single JOB    |
|       5       |    RUNNING_TIME_JOB_MAX_PROJECT    |    int    |   10   |       0       |          N           |      N      |               |   Default maximum execution time of all jobs in a project    |
|       6       |   RUNNING_JOBS_MAX_GITCI_SYSTEM    |    int    |   10   |       0       |          N           |      N      |               | Total maximum number of concurrent jobs in the worker bee CI system |
|       7       |   RUNNING_JOBS_MAX_GITCI_PROJECT   |    int    |   10   |       0       |          N           |      N      |               | Worker bee CI Maximum number of concurrent jobs in a single project |
|       8       |     RUNNING_TIME_JOB_MAX_GITCI     |    int    |   10   |       0       |          N           |      N      |               |          CI Maximum execution time of a single JOB           |
|       9       | RUNNING_TIME_JOB_MAX_PROJECT_GITCI |    int    |   10   |       0       |          N           |      N      |               |  CI Maximum execution time of a single item for worker bees  |
|      10       |   PROJECT_RUNNING_JOB_THRESHOLD    |    int    |   10   |       0       |          N           |      N      |               |    Number of jobs executed indicates the alarm threshold     |
|      11       |   PROJECT_RUNNING_TIME_THRESHOLD   |    int    |   10   |       0       |          N           |      N      |               |             job time alarm threshold of the item             |
|      12       |    SYSTEM_RUNNING_JOB_THRESHOLD    |    int    |   10   |       0       |          N           |      N      |               | Number of jobs executed by the system specifies the alarm threshold |
|      13       |            CREATED_TIME            | datetime  |   19   |       0       |          N           |      N      |               |                        Creation time                         |
|      14       |            UPDATED_TIME            | datetime  |   19   |       0       |          N           |      N      |               |                         Update time                          |
|      15       |              OPERATOR              |  varchar  |  128   |       0       |          N           |      N      |               |                           operator                           |

**Table name:** T_DISPATCH_RUNNING_JOBS

**Description:** Running JOB

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |        description         |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------------: |
|       1       |        ID        |    int    |   10   |       0       |          N           |      Y      |               |       Primary key ID       |
|       2       |    PROJECT_ID    |  varchar  |  128   |       0       |          N           |      N      |               |          Item ID           |
|       3       |     VM_TYPE      |  varchar  |  128   |       0       |          N           |      N      |               |          VM type           |
|       4       |     BUILD_ID     |  varchar  |  128   |       0       |          N           |      N      |               |          Build ID          |
|       5       |    VM_SEQ_ID     |  varchar  |  128   |       0       |          N           |      N      |               |   Build sequence number    |
|       6       |  EXECUTE_COUNT   |    int    |   10   |       0       |          N           |      N      |               |    Number of executions    |
|       7       |   CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |       Creation time        |
|       8       | AGENT_START_TIME | datetime  |   19   |       0       |          Y           |      N      |               | Build machine startup time |

**Table name:** T_DISPATCH_THIRDPARTY_AGENT_BUILD

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description      |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------: |
|       1       |      ID       |  bigint   |   20   |       0       |          N           |      Y      |               |    Primary key ID     |
|       2       |  PROJECT_ID   |  varchar  |   64   |       0       |          N           |      N      |               |        Item ID        |
|       3       |   AGENT_ID    |  varchar  |   32   |       0       |          N           |      N      |               |      Builder ID       |
|       4       |  PIPELINE_ID  |  varchar  |   34   |       0       |          N           |      N      |               |      Pipeline ID      |
|       5       |   BUILD_ID    |  varchar  |   34   |       0       |          N           |      N      |               |       Build ID        |
|       6       |   VM_SEQ_ID   |  varchar  |   34   |       0       |          N           |      N      |               | Build sequence number |
|       7       |    STATUS     |    int    |   10   |       0       |          N           |      N      |               |         state         |
|       8       | CREATED_TIME  | datetime  |   19   |       0       |          N           |      N      |               |     Creation time     |
|       9       | UPDATED_TIME  | datetime  |   19   |       0       |          N           |      N      |               |      Update time      |
|      10       |   WORKSPACE   |  varchar  |  4096  |       0       |          Y           |      N      |               |      Work space       |
|      11       |   BUILD_NUM   |    int    |   10   |       0       |          Y           |      N      |       0       |   Number of builds    |
|      12       | PIPELINE_NAME |  varchar  |  255   |       0       |          Y           |      N      |               |     Pipeline name     |
|      13       |   TASK_NAME   |  varchar  |  255   |       0       |          Y           |      N      |               |       Task name       |

**Table name:** T_DISPATCH_VM

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                description                 |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------: |
|       1       |        VM_ID        |  bigint   |   20   |       0       |          N           |      Y      |               |               Primary key ID               |
|       2       |    VM_MACHINE_ID    |    int    |   10   |       0       |          N           |      N      |               | VM indicates the ID of the parent computer |
|       3       |        VM_IP        |  varchar  |  128   |       0       |          N           |      N      |               |                VMIP address                |
|       4       |       VM_NAME       |  varchar  |  128   |       0       |          N           |      N      |               |                  VM name                   |
|       5       |        VM_OS        |  varchar  |   64   |       0       |          N           |      N      |               |           VM system information            |
|       6       |    VM_OS_VERSION    |  varchar  |   64   |       0       |          N           |      N      |               |       VM system information version        |
|       7       |       VM_CPU        |  varchar  |   64   |       0       |          N           |      N      |               |             VMCPU information              |
|       8       |      VM_MEMORY      |  varchar  |   64   |       0       |          N           |      N      |               |           VM memory information            |
|       9       |     VM_TYPE_ID      |    int    |   10   |       0       |          N           |      N      |               |                 VM type ID                 |
|      10       |     VM_MAINTAIN     |    bit    |   1    |       0       |          N           |      N      |       0       | Whether the VM is in the maintenance state |
|      11       | VM_MANAGER_USERNAME |  varchar  |  128   |       0       |          N           |      N      |               |         VM administrator username          |
|      12       |  VM_MANAGER_PASSWD  |  varchar  |  128   |       0       |          N           |      N      |               |         VM administrator password          |
|      13       |     VM_USERNAME     |  varchar  |  128   |       0       |          N           |      N      |               |       VM non-administrator user name       |
|      14       |      VM_PASSWD      |  varchar  |  128   |       0       |          N           |      N      |               |       VM non-administrator password        |
|      15       |   VM_CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |               Creation time                |
|      16       |   VM_UPDATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |             Modification time              |

**Table name:** T_DISPATCH_VM_TYPE

**Explanation:**

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |      TYPE_ID      |    int    |   10   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |     TYPE_NAME     |  varchar  |   64   |       0       |          N           |      N      |               |      name      |
|       3       | TYPE_CREATED_TIME | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       4       | TYPE_UPDATED_TIME | datetime  |   19   |       0       |          N           |      N      |               |  Update time   |

**Table name:** T_DOCKER_RESOURCE_OPTIONS

**docker** basic quota table

**Data column:**

| Serial number |          name          | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |          description          |
| :-----------: | :--------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------: |
|       1       |           ID           |  bigint   |   20   |       0       |          N           |      Y      |                   |          Primary key          |
|       2       |       CPU_PERIOD       |    int    |   10   |       0       |          N           |      N      |       10000       |       CPU configuration       |
|       3       |       CPU_QUOTA        |    int    |   10   |       0       |          N           |      N      |      160000       |       CPU configuration       |
|       4       |   MEMORY_LIMIT_BYTES   |  bigint   |   20   |       0       |          N           |      N      |    34359738368    |         Memory: 32GB          |
|       5       |          DISK          |    int    |   10   |       0       |          N           |      N      |        100        |          Disk: 100G           |
|       6       | BLKIO_DEVICE_WRITE_BPS |  bigint   |   20   |       0       |          N           |      N      |     125829120     | The disk write rate is 120m/s |
|       7       | BLKIO_DEVICE_READ_BPS  |  bigint   |   20   |       0       |          N           |      N      |     125829120     |    Disk read rate: 120m/s     |
|       8       |      DESCRIPTION       |  varchar  |  128   |       0       |          N           |      N      |                   |          description          |
|       9       |       GMT_CREATE       | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |         Creation time         |
|      10       |      GMT_MODIFIED      | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |       Modification time       |
