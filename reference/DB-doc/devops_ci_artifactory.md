# devops_ci_artifactory

**Database name:** devops_ci_artifactory

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_artifactory

|              Table name               |           description           |
| :-----------------------------------: | :-----------------------------: |
|    [T_FILE_INFO](broken-reference)    |     File information table      |
| [T_FILE_PROPS_INFO](broken-reference) | File metadata information table |
|    [T_FILE_TASK](broken-reference)    |     File hosting task table     |
|      [T_TOKEN](broken-reference)      |                                 |

**Table name:** T_FILE_INFO

File information table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                 description                 |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------------------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |               Primary key ID                |
|       2       | PROJECT_CODE |  varchar  |   64   |       0       |          Y           |      N      |                   | The project to which the user group belongs |
|       3       |  FILE_TYPE   |  varchar  |   32   |       0       |          N           |      N      |                   |                  File type                  |
|       4       |  FILE_PATH   |  varchar  |  1024  |       0       |          Y           |      N      |                   |                  File path                  |
|       5       |  FILE_NAME   |  varchar  |  128   |       0       |          N           |      N      |                   |                  File name                  |
|       6       |  FILE_SIZE   |  bigint   |   20   |       0       |          N           |      N      |                   |                  File size                  |
|       7       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |                   founder                   |
|       8       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                  modifier                   |
|       9       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                Creation time                |
|      10       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                 Update time                 |

**Table name:** T_FILE_PROPS_INFO

File metadata information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |    Primary key ID     |
|       2       |  PROPS_KEY  |  varchar  |   64   |       0       |          Y           |      N      |                   |  Property field key   |
|       3       | PROPS_VALUE |  varchar  |  256   |       0       |          Y           |      N      |                   | Attribute field value |
|       4       |   FILE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |        File ID        |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder        |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |       modifier        |
|       7       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time     |
|       8       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time      |

**Table name:** T_FILE_TASK

File hosting task table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |   TASK_ID   |  varchar  |   64   |       0       |          N           |      Y      |               |      Task ID       |
|       2       |  FILE_TYPE  |  varchar  |   32   |       0       |          Y           |      N      |               |     File type      |
|       3       |  FILE_PATH  |   text    | 65535  |       0       |          Y           |      N      |               |     File path      |
|       4       | MACHINE_IP  |  varchar  |   32   |       0       |          Y           |      N      |               | Machine ip address |
|       5       | LOCAL_PATH  |   text    | 65535  |       0       |          Y           |      N      |               |     Local path     |
|       6       |   STATUS    | smallint  |   6    |       0       |          Y           |      N      |               |       state        |
|       7       |   USER_ID   |  varchar  |   32   |       0       |          Y           |      N      |               |      User ID       |
|       8       | PROJECT_ID  |  varchar  |   64   |       0       |          Y           |      N      |               |      Item ID       |
|       9       | PIPELINE_ID |  varchar  |   34   |       0       |          Y           |      N      |               |    Pipeline ID     |
|      10       |  BUILD_ID   |  varchar  |   34   |       0       |          Y           |      N      |               |      Build ID      |
|      11       | CREATE_TIME | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time    |
|      12       | UPDATE_TIME | datetime  |   19   |       0       |          Y           |      N      |               | Modification time  |

**Table name:** T_TOKEN

**Explanation:**

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |        description        |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |                   |      Primary key ID       |
|       2       |     USER_ID      |  varchar  |   64   |       0       |          N           |      N      |                   |          User ID          |
|       3       |    PROJECT_ID    |  varchar  |   32   |       0       |          N           |      N      |                   |          Item ID          |
|       4       | ARTIFACTORY_TYPE |  varchar  |   32   |       0       |          N           |      N      |                   | Type of archive warehouse |
|       5       |       PATH       |   text    | 65535  |       0       |          N           |      N      |                   |           path            |
|       6       |      TOKEN       |  varchar  |   64   |       0       |          N           |      N      |                   |           TOKEN           |
|       7       |   EXPIRE_TIME    | datetime  |   19   |       0       |          N           |      N      |                   |      Expiration time      |
|       8       |   CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      |                   |       Creation time       |
|       9       |   UPDATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |        Update time        |
