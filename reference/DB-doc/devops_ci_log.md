# devops_ci_log

**Database name:** devops_ci_log

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_log

|              Table name              |                      description                      |
| :----------------------------------: | :---------------------------------------------------: |
| [T_LOG_INDICES_V2](broken-reference) | Build log has been associated with the ES index table |
|   [T_LOG_STATUS](broken-reference)   |           Build the log print status table            |
|  [T_LOG_SUBTAGS](broken-reference)   |           Builds the sunchi child tag table           |

**Table name:** T_LOG_INDICES_V2

**Note:** The build log has been associated with the ES index table

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |        description        |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :-----------------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |                     |      Primary key ID       |
|       2       |     BUILD_ID     |  varchar  |   64   |       0       |          N           |      N      |                     |         Build ID          |
|       3       |    INDEX_NAME    |  varchar  |   20   |       0       |          N           |      N      |                     |                           |
|       4       |  LAST_LINE_NUM   |  bigint   |   20   |       0       |          N           |      N      |          1          |     Last line number      |
|       5       |   CREATED_TIME   | timestamp |   19   |       0       |          N           |      N      |  CURRENT_TIMESTAMP  |       Creation time       |
|       6       |   UPDATED_TIME   | timestamp |   19   |       0       |          N           |      N      | 2019-11-11 00:00:00 |     Modification time     |
|       7       |      ENABLE      |    bit    |   1    |       0       |          N           |      N      |        B '0'        |   buildisenablev2ornot    |
|       8       | LOG_CLUSTER_NAME |  varchar  |   64   |       0       |          N           |      N      |                     |   multieslogclustername   |
|       9       |   USE_CLUSTER    |    bit    |   1    |       0       |          N           |      N      |        B '0'        | usemultieslogclusterornot |

**Table name:** T_LOG_STATUS

Build log print status table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |     description      |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :------------------: |
|       1       |      ID       |  bigint   |   20   |       0       |          N           |      Y      |                      |    Primary key ID    |
|       2       |   BUILD_ID    |  varchar  |   64   |       0       |          N           |      N      |                      |       Build ID       |
|       3       |      TAG      |  varchar  |   64   |       0       |          Y           |      N      |                      |        label         |
|       4       |    SUB_TAG    |  varchar  |  256   |       0       |          Y           |      N      |                      |        subtag        |
|       5       |    JOB_ID     |  varchar  |   64   |       0       |          Y           |      N      |                      |        JOBID         |
|       6       |     MODE      |  varchar  |   32   |       0       |          Y           |      N      |                      |    LogStorageMode    |
|       7       | EXECUTE_COUNT |    int    |   10   |       0       |          N           |      N      |                      | Number of executions |
|       8       |   FINISHED    |    bit    |   1    |       0       |          N           |      N      |        B '0'         | buildisfinishedornot |
|       9       |  CREATE_TIME  | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |    Creation time     |

**Table name:** T_LOG_SUBTAGS

**Build** the sun Zhi child label table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :---------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |                      |  Primary key ID   |
|       2       |  BUILD_ID   |  varchar  |   64   |       0       |          N           |      N      |                      |     Build ID      |
|       3       |     TAG     |  varchar  |   64   |       0       |          N           |      N      |                      |    Plug-in tag    |
|       4       |  SUB_TAGS   |   text    | 65535  |       0       |          N           |      N      |                      | Plug-in child tag |
|       5       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |   Creation time   |
