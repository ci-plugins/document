# devops_ci_auth

**Database name:** devops_ci_auth

**Issue:** 1.0.0

**Documentation Description:** Database documentation for devops_ci_auth

|                   Table name                    |                     description                      |
| :---------------------------------------------: | :--------------------------------------------------: |
|      [T_AUTH_GROUP_INFO](broken-reference)      |             User group information table             |
|    [T_AUTH_GROUP_PERSSION](broken-reference)    |                                                      |
|      [T_AUTH_GROUP_USER](broken-reference)      |                                                      |
|     [T_AUTH_IAM_CALLBACK](broken-reference)     |                 IAM callback address                 |
|       [T_AUTH_MANAGER](broken-reference)        |              Administrator policy table              |
|     [T_AUTH_MANAGER_USER](broken-reference)     |     Administrator user table (valid users only)      |
| [T_AUTH_MANAGER_USER_HISTORY](broken-reference) |           Administrator user history table           |
|  [T_AUTH_MANAGER_WHITELIST](broken-reference)   | List of administrator self-service application forms |
|       [T_AUTH_STRATEGY](broken-reference)       |               Permission policy table                |

**Table name:** T_AUTH_GROUP_INFO

**Note:** User group information table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                     description                     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------------------------: |
|       1       |      ID      |    int    |   10   |       0       |          N           |      Y      |               |                     Primary ID                      |
|       2       |  GROUP_NAME  |  varchar  |   32   |       0       |          N           |      N      |      ""       |                   User group name                   |
|       3       |  GROUP_CODE  |  varchar  |   32   |       0       |          N           |      N      |               | User Group ID The default user group ID is the same |
|       4       |  GROUP_TYPE  |    bit    |   1    |       0       |          N           |      N      |               |           User group Type 0 Default group           |
|       5       | PROJECT_CODE |  varchar  |   64   |       0       |          N           |      N      |      ""       |     The project to which the user group belongs     |
|       6       |  IS_DELETE   |    bit    |   1    |       0       |          N           |      N      |     B '0'     |       Whether to delete 0 can be deleted by 1       |
|       7       | CREATE_USER  |  varchar  |   64   |       0       |          N           |      N      |      ""       |                     Add person                      |
|       8       | UPDATE_USER  |  varchar  |   64   |       0       |          Y           |      N      |               |                      modifier                       |
|       9       | CREATE_TIME  | datetime  |   23   |       0       |          N           |      N      |               |                    Creation time                    |
|      10       | UPDATE_TIME  | datetime  |   23   |       0       |          Y           |      N      |               |                  Modification time                  |
|      11       | DISPLAY_NAME |  varchar  |   32   |       0       |          Y           |      N      |               |                   User group name                   |
|      12       | RELATION_ID  |  varchar  |   32   |       0       |          Y           |      N      |               |                Associated system ID                 |

**Table name:** T_AUTH_GROUP_PERSSION

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |     ID      |  varchar  |   64   |       0       |          N           |      Y      |               |                          Primary ID                          |
|       2       | AUTH_ACTION |  varchar  |   64   |       0       |          N           |      N      |      ""       |                      Permission action                       |
|       3       | GROUP_CODE  |  varchar  |   64   |       0       |          N           |      N      |      ""       | User group number The default number of the seven built-in groups is fixed. The user-defined group number is random |
|       4       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |      ""       |                           founder                            |
|       5       | UPDATE_USER |  varchar  |   64   |       0       |          Y           |      N      |               |                           modifier                           |
|       6       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      |               |                        Creation time                         |
|       7       | UPDATE_TIME | datetime  |   23   |       0       |          Y           |      N      |               |                      Modification time                       |

**Table name:** T_AUTH_GROUP_USER

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  varchar  |   64   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |   USER_ID   |  varchar  |   64   |       0       |          N           |      N      |      ""       |    User ID     |
|       3       |  GROUP_ID   |  varchar  |   64   |       0       |          N           |      N      |      ""       | User group ID  |
|       4       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |      ""       |   Add a user   |
|       5       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      |               |    Add time    |

**Table name:** T_AUTH_IAM_CALLBACK

**Note:** IAM callback address

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |              description              |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------------------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |               |            Primary key ID             |
|       2       |   GATEWAY   |  varchar  |  255   |       0       |          N           |      N      |      ""       |        Target service gateway         |
|       3       |    PATH     |  varchar  |  1024  |       0       |          N           |      N      |      ""       |         Target interface path         |
|       4       | DELETE_FLAG |    bit    |   1    |       0       |          Y           |      N      |     B '0'     | Whether to delete true- Yes false- No |
|       5       |  RESOURCE   |  varchar  |   32   |       0       |          N           |      N      |      ""       |             Resource type             |
|       6       |   SYSTEM    |  varchar  |   32   |       0       |          N           |      N      |      ""       |             Access system             |

**Table name:** T_AUTH_MANAGER

**Note:** Administrator policy table

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |     description      |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------------: |
|       1       |       ID        |    int    |   10   |       0       |          N           |      Y      |                   |    Primary key ID    |
|       2       |      NAME       |  varchar  |   32   |       0       |          N           |      N      |                   |         name         |
|       3       | ORGANIZATION_ID |    int    |   10   |       0       |          N           |      N      |                   |   Organization ID    |
|       4       |      LEVEL      |    int    |   10   |       0       |          N           |      N      |                   |     Hierarchy ID     |
|       5       |   STRATEGYID    |    int    |   10   |       0       |          N           |      N      |                   | Permission policy ID |
|       6       |    IS_DELETE    |    bit    |   1    |       0       |          N           |      N      |         0         |    Delete or not     |
|       7       |   CREATE_USER   |  varchar  |   11   |       0       |          N           |      N      |        ""         |    Create a user     |
|       8       |   UPDATE_USER   |  varchar  |   11   |       0       |          Y           |      N      |        ""         |     Modify user      |
|       9       |   CREATE_TIME   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Creation time     |
|      10       |   UPDATE_TIME   | timestamp |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |  Modification time   |

**Table name:** T_AUTH_MANAGER_USER

Administrator user table (only users within the validity period)

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                description                |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |                   |              Primary key ID               |
|       2       |   USER_ID   |  varchar  |   64   |       0       |          N           |      N      |                   |                  User ID                  |
|       3       | MANAGER_ID  |    int    |   10   |       0       |          N           |      N      |                   |        Administrator permission ID        |
|       4       | START_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Start time when permissions take effect  |
|       5       |  END_TIME   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | End time when the permission takes effect |
|       6       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |                   |               Create a user               |
|       7       | UPDATE_USER |  varchar  |   64   |       0       |          Y           |      N      |                   |                Modify user                |
|       8       | CREATE_TIME | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |               Creation time               |
|       9       | UPDATE_TIME | timestamp |   19   |       0       |          Y           |      N      |                   |             Modification time             |

**Table name:** T_AUTH_MANAGER_USER_HISTORY

**Note:** Administrator user history table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                description                |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |                   |              Primary key ID               |
|       2       |   USER_ID   |  varchar  |   64   |       0       |          N           |      N      |                   |                  User ID                  |
|       3       | MANAGER_ID  |    int    |   10   |       0       |          N           |      N      |                   |        Administrator permission ID        |
|       4       | START_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Start time when permissions take effect  |
|       5       |  END_TIME   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | End time when the permission takes effect |
|       6       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |                   |               Create a user               |
|       7       | UPDATE_USER |  varchar  |   64   |       0       |          Y           |      N      |                   |                Modify user                |
|       8       | CREATE_TIME | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |               Creation time               |
|       9       | UPDATE_TIME | timestamp |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |             Modification time             |

**Table name:** T_AUTH_MANAGER_WHITELIST

**Description:** The administrator self-service application list

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |     ID     |    int    |   10   |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       | MANAGER_ID |    int    |   10   |       0       |          N           |      N      |               | Management policy ID |
|       3       |  USER_ID   |  varchar  |   64   |       0       |          N           |      N      |               |       User ID        |

**Table name:** T_AUTH_STRATEGY

Permission policy table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |         description          |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------: |
|       1       |      ID       |    int    |   10   |       0       |          N           |      Y      |                   | ID of the policy primary key |
|       2       | STRATEGY_NAME |  varchar  |   32   |       0       |          N           |      N      |                   |         Policy name          |
|       3       | STRATEGY_BODY |  varchar  |  2000  |       0       |          N           |      N      |                   |        Policy content        |
|       4       |   IS_DELETE   |    bit    |   1    |       0       |          N           |      N      |         0         |  Delete No. 0 No. 1 Delete   |
|       5       |  CREATE_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |        Creation time         |
|       6       |  UPDATE_TIME  | timestamp |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP |      Modification time       |
|       7       |  CREATE_USER  |  varchar  |   32   |       0       |          N           |      N      |                   |           founder            |
|       8       |  UPDATE_USER  |  varchar  |   32   |       0       |          Y           |      N      |                   |           modifier           |
