# devops_ci_op

**Database name:** devops_ci_op

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_op

|                  Table name                   | description |
| :-------------------------------------------: | :---------: |
|         [dept_info](broken-reference)         |             |
|       [project_info](broken-reference)        |             |
|           [role](broken-reference)            |             |
|      [role_permission](broken-reference)      |             |
|      [schema_version](broken-reference)       |             |
|      [spring_session](broken-reference)       |             |
| [SPRING_SESSION_ATTRIBUTES](broken-reference) |             |
|       [t_user_token](broken-reference)        |             |
|        [url_action](broken-reference)         |             |
|           [user](broken-reference)            |             |
|      [user_permission](broken-reference)      |             |
|         [user_role](broken-reference)         |             |

**Table name:** dept_info

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       id       |    int    |   10   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |  create_time   | datetime  |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|       3       |    dept_id     |    int    |   10   |       0       |          N           |      N      |               |     The project belongs to the secondary organization ID     |
|       4       |   dept_name    |  varchar  |  100   |       0       |          N           |      N      |               | Name of the secondary organization to which the project belongs |
|       5       |     level      |    int    |   10   |       0       |          N           |      N      |               |                         Hierarchy ID                         |
|       6       | parent_dept_id |    int    |   10   |       0       |          Y           |      N      |               |                                                              |
|       7       |  UPDATE_TIME   | datetime  |   19   |       0       |          Y           |      N      |               |                         Update time                          |

**Table name:** project_info

**Explanation:**

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |         id          |    int    |   10   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |   approval_status   |    int    |   10   |       0       |          Y           |      N      |               |                         Audit status                         |
|       3       |    approval_time    | datetime  |   19   |       0       |          Y           |      N      |               |                        Approval time                         |
|       4       |      approver       |  varchar  |  100   |       0       |          Y           |      N      |               |                           approver                           |
|       5       |      cc_app_id      |    int    |   10   |       0       |          Y           |      N      |               |                        Application ID                        |
|       6       |     created_at      | datetime  |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|       7       |       creator       |  varchar  |  100   |       0       |          Y           |      N      |               |                           founder                            |
|       8       |   creator_bg_name   |  varchar  |  100   |       0       |          Y           |      N      |               |                 Creator business group name                  |
|       9       | creator_center_name |  varchar  |  100   |       0       |          Y           |      N      |               |                     Creator center name                      |
|      10       |  creator_dept_name  |  varchar  |  100   |       0       |          Y           |      N      |               | Creator Name of the secondary organization to which the project belongs |
|      11       |    english_name     |  varchar  |  255   |       0       |          Y           |      N      |               |                         English name                         |
|      12       |     is_offlined     |    bit    |   1    |       0       |          Y           |      N      |               |                      Deactivate or not                       |
|      13       |     is_secrecy      |    bit    |   1    |       0       |          Y           |      N      |               |                    Confidentiality or not                    |
|      14       |    project_bg_id    |    int    |   10   |       0       |          Y           |      N      |               |                      Business group ID                       |
|      15       |   project_bg_name   |  varchar  |  100   |       0       |          Y           |      N      |               |                     Business group name                      |
|      16       |  project_center_id  |  varchar  |   50   |       0       |          Y           |      N      |               |                          Center ID                           |
|      17       | project_center_name |  varchar  |  100   |       0       |          Y           |      N      |               |                         Central name                         |
|      18       |   project_dept_id   |    int    |   10   |       0       |          Y           |      N      |               |                         Mechanism ID                         |
|      19       |  project_dept_name  |  varchar  |  100   |       0       |          Y           |      N      |               | Name of the secondary organization to which the project belongs |
|      20       |     project_id      |  varchar  |  100   |       0       |          Y           |      N      |               |                           Item ID                            |
|      21       |    project_name     |  varchar  |  100   |       0       |          Y           |      N      |               |                         Project name                         |
|      22       |    project_type     |    int    |   10   |       0       |          Y           |      N      |               |                          Item type                           |
|      23       |       use_bk        |    bit    |   1    |       0       |          Y           |      N      |               |                 Whether to use a blue whale                  |

**Table name:** role

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |     id      |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       | description |  varchar  |  255   |       0       |          Y           |      N      |               |    description    |
|       3       |    name     |  varchar  |  255   |       0       |          N           |      N      |               |       name        |
|       4       |   ch_name   |  varchar  |  255   |       0       |          Y           |      N      |               |    Branch name    |
|       5       | create_time | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time   |
|       6       | modify_time | datetime  |   19   |       0       |          Y           |      N      |               | Modification time |

**Table name:** role_permission

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |      id       |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |  expire_time  | datetime  |   19   |       0       |          Y           |      N      |               |  Expiration time  |
|       3       |    role_id    |    int    |   10   |       0       |          Y           |      N      |               |      Role ID      |
|       4       | url_action_id |    int    |   10   |       0       |          Y           |      N      |               |                   |
|       5       |  create_time  | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time   |
|       6       |  modify_time  | datetime  |   19   |       0       |          Y           |      N      |               | Modification time |

**Table name:** schema_version

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       | installed_rank |    int    |   10   |       0       |          N           |      Y      |                   |                   |
|       2       |    version     |  varchar  |   50   |       0       |          Y           |      N      |                   |  Version number   |
|       3       |  description   |  varchar  |  200   |       0       |          N           |      N      |                   |    description    |
|       4       |      type      |  varchar  |   20   |       0       |          N           |      N      |                   |       type        |
|       5       |     script     |  varchar  |  1000  |       0       |          N           |      N      |                   |  Package script   |
|       6       |    checksum    |    int    |   10   |       0       |          Y           |      N      |                   |     checksum      |
|       7       |  installed_by  |  varchar  |  100   |       0       |          N           |      N      |                   |     installer     |
|       8       |  installed_on  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Installation time |
|       9       | execution_time |    int    |   10   |       0       |          N           |      N      |                   |  Execution time   |
|      10       |    success     |    bit    |   1    |       0       |          N           |      N      |                   |  Success or not   |

**Table name:** spring_session

**Explanation:**

**Data column:**

| Serial number |         name          | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description  |
| :-----------: | :-------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-----------: |
|       1       |      SESSION_ID       |   char    |   36   |       0       |          N           |      Y      |               |   SESSIONID   |
|       2       |     CREATION_TIME     |  bigint   |   20   |       0       |          N           |      N      |               | Creation time |
|       3       |   LAST_ACCESS_TIME    |  bigint   |   20   |       0       |          N           |      N      |               |               |
|       4       | MAX_INACTIVE_INTERVAL |    int    |   10   |       0       |          N           |      N      |               |               |
|       5       |    PRINCIPAL_NAME     |  varchar  |  100   |       0       |          Y           |      N      |               |               |

**Table name:** SPRING_SESSION_ATTRIBUTES

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |   SESSION_ID    |   char    |   36   |       0       |          N           |      Y      |               |   SESSIONID    |
|       2       | ATTRIBUTE_NAME  |  varchar  |  200   |       0       |          N           |      Y      |               | Attribute name |
|       3       | ATTRIBUTE_BYTES |   blob    | 65535  |       0       |          Y           |      N      |               | Attribute byte |

**Table name:** t_user_token

**Explanation:**

**Data column:**

| Serial number |          name          | Data type | length | Decimal place | Allowable null value | Primary key | Default value |       description        |
| :-----------: | :--------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------: |
|       1       |        user_Id         |  varchar  |  255   |       0       |          N           |      Y      |               |         User ID          |
|       2       |      access_Token      |  varchar  |  255   |       0       |          Y           |      N      |               |     Permission Token     |
|       3       |   expire_Time_Mills    |  bigint   |   20   |       0       |          N           |      N      |               |     Expiration time      |
|       4       | last_Access_Time_Mills |  bigint   |   20   |       0       |          N           |      N      |               | Last authentication time |
|       5       |     refresh_Token      |  varchar  |  255   |       0       |          Y           |      N      |               |      Refresh token       |
|       6       |       user_Type        |  varchar  |  255   |       0       |          Y           |      N      |               |        User type         |

**Table name:** url_action

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |     id      |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |   action    |  varchar  |  255   |       0       |          N           |      N      |               |     operation     |
|       3       | description |  varchar  |  255   |       0       |          Y           |      N      |               |    description    |
|       4       |     url     |  varchar  |  255   |       0       |          N           |      N      |               |    url address    |
|       5       | create_time | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time   |
|       6       | modify_time | datetime  |   19   |       0       |          Y           |      N      |               | Modification time |

**Table name:** user

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description   |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------: |
|       1       |       id        |    int    |   10   |       0       |          N           |      Y      |               | Primary key ID  |
|       2       |     chname      |  varchar  |  255   |       0       |          Y           |      N      |               |                 |
|       3       |   create_time   | datetime  |   19   |       0       |          Y           |      N      |               |  Creation time  |
|       4       |      email      |  varchar  |  255   |       0       |          Y           |      N      |               |      email      |
|       5       |      lang       |  varchar  |  255   |       0       |          Y           |      N      |               |    language     |
|       6       | last_login_time | datetime  |   19   |       0       |          Y           |      N      |               | Last login time |
|       7       |      phone      |  varchar  |  255   |       0       |          Y           |      N      |               |    telephone    |
|       8       |    username     |  varchar  |  255   |       0       |          N           |      N      |               |    User name    |

**Table name:** user_permission

**Explanation:**

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |      id       |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |  expire_time  | datetime  |   19   |       0       |          Y           |      N      |               |  Expiration time  |
|       3       | url_action_id |    int    |   10   |       0       |          Y           |      N      |               |                   |
|       4       |    user_id    |    int    |   10   |       0       |          Y           |      N      |               |      User ID      |
|       5       |  create_time  | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time   |
|       6       |  modify_time  | datetime  |   19   |       0       |          Y           |      N      |               | Modification time |

**Table name:** user_role

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |     id      |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID   |
|       2       |   role_id   |    int    |   10   |       0       |          Y           |      N      |               |      Role ID      |
|       3       |   user_id   |    int    |   10   |       0       |          Y           |      N      |               |      User ID      |
|       4       | expire_time | datetime  |   19   |       0       |          Y           |      N      |               |  Expiration time  |
|       5       | create_time | datetime  |   19   |       0       |          Y           |      N      |               |   Creation time   |
|       6       | modify_time | datetime  |   19   |       0       |          Y           |      N      |               | Modification time |
