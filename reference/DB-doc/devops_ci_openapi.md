# devops_ci_openapi

**Database name:** devops_ci_openapi

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_openapi

|               Table name               |                    description                     |
| :------------------------------------: | :------------------------------------------------: |
|  [T_APP_CODE_GROUP](broken-reference)  | Organizational structure corresponding to app_code |
| [T_APP_CODE_PROJECT](broken-reference) |  app_code corresponds to the BKCI project   |
|  [T_APP_USER_INFO](broken-reference)   |    The administrator corresponding to app_code     |

**Table name:** T_APP_CODE_GROUP

**Note:** app_code corresponds to the organizational structure

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |  APP_CODE   |  varchar  |  255   |       0       |          N           |      N      |               |                          APP coding                          |
|       3       |    BG_ID    |    int    |   10   |       0       |          Y           |      N      |               |                      Business group ID                       |
|       4       |   BG_NAME   |  varchar  |  255   |       0       |          Y           |      N      |               |                     Business group name                      |
|       5       |   DEPT_ID   |    int    |   10   |       0       |          Y           |      N      |               |     The project belongs to the secondary organization ID     |
|       6       |  DEPT_NAME  |  varchar  |  255   |       0       |          Y           |      N      |               | Name of the secondary organization to which the project belongs |
|       7       |  CENTER_ID  |    int    |   10   |       0       |          Y           |      N      |               |                          Center ID                           |
|       8       | CENTER_NAME |  varchar  |  255   |       0       |          Y           |      N      |               |                         Central name                         |
|       9       |   CREATOR   |  varchar  |  255   |       0       |          Y           |      N      |               |                           founder                            |
|      10       | create_time | datetime  |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|      11       |   UPDATER   |  varchar  |  255   |       0       |          Y           |      N      |               |                         With the new                         |
|      12       | UPDATE_TIME | datetime  |   19   |       0       |          Y           |      N      |               |                      Modification time                       |

**Table name:** T_APP_CODE_PROJECT

**Note:** app_code corresponds to the BKCI project

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |  APP_CODE   |  varchar  |  255   |       0       |          N           |      N      |               |   APP coding   |
|       3       | PROJECT_ID  |  varchar  |  255   |       0       |          N           |      N      |               |    Item ID     |
|       4       |   CREATOR   |  varchar  |  255   |       0       |          Y           |      N      |               |    founder     |
|       5       | create_time | datetime  |   19   |       0       |          Y           |      N      |               | Creation time  |

**Table name:** T_APP_USER_INFO

**Note:** Administrator corresponding to app_code

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       |  APP_CODE   |  varchar  |   64   |       0       |          N           |      N      |               |      APP coding      |
|       3       | MANAGER_ID  |  varchar  |   64   |       0       |          N           |      N      |               | APP administrator ID |
|       4       |  IS_DELETE  |    bit    |   1    |       0       |          N           |      N      |               |    Delete or not     |
|       5       | CREATE_USER |  varchar  |   64   |       0       |          N           |      N      |               |    Add personnel     |
|       6       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      |               |       Add time       |
