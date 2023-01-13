# devops_ci_repository

**Database name:** devops_ci_repository

**Issue:** 1.0.0

**Documentation Description:** devops_ci_repository database documentation

|                  Table name                   |            description             |
| :-------------------------------------------: | :--------------------------------: |
|       [T_REPOSITORY](broken-reference)        |          Code base table           |
|   [T_REPOSITORY_CODE_GIT](broken-reference)   | Worker bee code base specification |
| [T_REPOSITORY_CODE_GITLAB](broken-reference)  |   gitlab code base specification   |
|   [T_REPOSITORY_CODE_SVN](broken-reference)   |    svn code base specification     |
|    [T_REPOSITORY_COMMIT](broken-reference)    |        Code base change log        |
|    [T_REPOSITORY_GITHUB](broken-reference)    |   github code base specification   |
| [T_REPOSITORY_GITHUB_TOKEN](broken-reference) |       githuboauthtoken table       |
|  [T_REPOSITORY_GIT_CHECK](broken-reference)   |  oauthtoken table of worker bees   |
|  [T_REPOSITORY_GIT_TOKEN](broken-reference)   | commitchecker table of worker bees |

**Table name:** T_REPOSITORY

Code base table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |               description               |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :-------------------------------------: |
|       1       | REPOSITORY_ID |  bigint   |   20   |       0       |          N           |      Y      |                     |             Primary key ID              |
|       2       |  PROJECT_ID   |  varchar  |   32   |       0       |          N           |      N      |                     |                 Item ID                 |
|       3       |    USER_ID    |  varchar  |   64   |       0       |          N           |      N      |                     |                 User ID                 |
|       4       |  ALIAS_NAME   |  varchar  |  255   |       0       |          N           |      N      |                     |                  alias                  |
|       5       |      URL      |  varchar  |  255   |       0       |          N           |      N      |                     |               url address               |
|       6       |     TYPE      |  varchar  |   20   |       0       |          N           |      N      |                     |                  type                   |
|       7       | CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |              Creation time              |
|       8       | UPDATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |            Modification time            |
|       9       |  IS_DELETED   |    bit    |   1    |       0       |          N           |      N      |                     | Whether to delete 0 can be deleted by 1 |

**Table name:** T_REPOSITORY_CODE_GIT

**Specification** of worker bee code base

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |     description     |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :-----------------: |
|       1       | REPOSITORY_ID |  bigint   |   20   |       0       |          N           |      Y      |                     |    Warehouse ID     |
|       2       | PROJECT_NAME  |  varchar  |  255   |       0       |          N           |      N      |                     |    Project name     |
|       3       |   USER_NAME   |  varchar  |   64   |       0       |          N           |      N      |                     |      User name      |
|       4       | CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |    Creation time    |
|       5       | UPDATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |  Modification time  |
|       6       | CREDENTIAL_ID |  varchar  |   64   |       0       |          N           |      N      |                     |    Credential ID    |
|       7       |   AUTH_TYPE   |  varchar  |   8    |       0       |          Y           |      N      |                     | Authentication mode |

**Table name:** T_REPOSITORY_CODE_GITLAB

**gitlab** code base list

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |    description    |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :---------------: |
|       1       | REPOSITORY_ID |  bigint   |   20   |       0       |          N           |      Y      |                     |   Warehouse ID    |
|       2       | PROJECT_NAME  |  varchar  |  255   |       0       |          N           |      N      |                     |   Project name    |
|       3       | CREDENTIAL_ID |  varchar  |   64   |       0       |          N           |      N      |                     |   Credential ID   |
|       4       | CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |   Creation time   |
|       5       | UPDATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 | Modification time |
|       6       |   USER_NAME   |  varchar  |   64   |       0       |          N           |      N      |                     |     User name     |

**Table name:** T_REPOSITORY_CODE_SVN

**Note:** svn code base details

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |    description    |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :---------------: |
|       1       | REPOSITORY_ID |  bigint   |   20   |       0       |          N           |      Y      |                     |   Warehouse ID    |
|       2       |    REGION     |  varchar  |  255   |       0       |          N           |      N      |                     |       area        |
|       3       | PROJECT_NAME  |  varchar  |  255   |       0       |          N           |      N      |                     |   Project name    |
|       4       |   USER_NAME   |  varchar  |   64   |       0       |          N           |      N      |                     |     User name     |
|       5       | CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |   Creation time   |
|       6       | UPDATED_TIME  | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 | Modification time |
|       7       | CREDENTIAL_ID |  varchar  |   64   |       0       |          N           |      N      |                     |   Credential ID   |
|       8       |   SVN_TYPE    |  varchar  |   32   |       0       |          Y           |      N      |                     |  Warehouse type   |

**Table name:** T_REPOSITORY_COMMIT

Code base change record

**Data column:**

| Serial number |    name     | Data type |   length   | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :---------: | :-------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |     ID      |  bigint   |     20     |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       |  BUILD_ID   |  varchar  |     34     |       0       |          Y           |      N      |               |       Build ID       |
|       3       | PIPELINE_ID |  varchar  |     34     |       0       |          Y           |      N      |               |     Pipeline ID      |
|       4       |   REPO_ID   |  bigint   |     20     |       0       |          Y           |      N      |               |     Code base ID     |
|       5       |    TYPE     | smallint  |     6      |       0       |          Y           |      N      |               | 1-svn,2-git,3-gitlab |
|       6       |   COMMIT    |  varchar  |     64     |       0       |          Y           |      N      |               |        submit        |
|       7       |  COMMITTER  |  varchar  |     32     |       0       |          Y           |      N      |               |      submitter       |
|       8       | COMMIT_TIME | datetime  |     19     |       0       |          Y           |      N      |               |   Submission time    |
|       9       |   COMMENT   | longtext  | 2147483647 |       0       |          Y           |      N      |               |       comment        |
|      10       | ELEMENT_ID  |  varchar  |     34     |       0       |          Y           |      N      |               |      Atomic ID       |
|      11       |  REPO_NAME  |  varchar  |    128     |       0       |          Y           |      N      |               |   Code base alias    |

**Table name:** T_REPOSITORY_GITHUB

**Description:** github code base list

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       | REPOSITORY_ID |  bigint   |   20   |       0       |          N           |      Y      |                   |   Warehouse ID    |
|       2       | CREDENTIAL_ID |  varchar  |  128   |       0       |          Y           |      N      |                   |   Credential ID   |
|       3       | PROJECT_NAME  |  varchar  |  255   |       0       |          N           |      N      |                   |   Project name    |
|       4       |   USER_NAME   |  varchar  |   64   |       0       |          N           |      N      |                   |     User name     |
|       5       | CREATED_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time   |
|       6       | UPDATED_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Modification time |

**Table name:** T_REPOSITORY_GITHUB_TOKEN

**githuboauthtoken** table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID  |
|       2       |   USER_ID    |  varchar  |   64   |       0       |          N           |      N      |               |     User ID      |
|       3       | ACCESS_TOKEN |  varchar  |   96   |       0       |          N           |      N      |               | Permission Token |
|       4       |  TOKEN_TYPE  |  varchar  |   64   |       0       |          N           |      N      |               |    token type    |
|       5       |    SCOPE     |   text    | 65535  |       0       |          N           |      N      |               | Effective scope  |
|       6       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |  Creation time   |
|       7       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |   Update time    |

**Table name:** T_REPOSITORY_GIT_CHECK

Worker bee oauthtoken table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               |   Primary key ID   |
|       2       | PIPELINE_ID  |  varchar  |   64   |       0       |          N           |      N      |               |    Pipeline ID     |
|       3       | BUILD_NUMBER |    int    |   10   |       0       |          N           |      N      |               |    Build number    |
|       4       |   REPO_ID    |  varchar  |   64   |       0       |          Y           |      N      |               |    Code base ID    |
|       5       |  COMMIT_ID   |  varchar  |   64   |       0       |          N           |      N      |               | Code submission ID |
|       6       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |   Creation time    |
|       7       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               |    Update time     |
|       8       |  REPO_NAME   |  varchar  |  128   |       0       |          Y           |      N      |               |  Code base alias   |
|       9       |   CONTEXT    |  varchar  |  255   |       0       |          Y           |      N      |               |      content       |
|      10       |    SOURCE    |  varchar  |   64   |       0       |          N           |      N      |               |    Event source    |

**Table name:** T_REPOSITORY_GIT_TOKEN

commitchecker table of worker bees

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |        description         |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------------------: |
|       1       |      ID       |  bigint   |   20   |       0       |          N           |      Y      |                   |       Primary key ID       |
|       2       |    USER_ID    |  varchar  |   64   |       0       |          Y           |      N      |                   |          User ID           |
|       3       | ACCESS_TOKEN  |  varchar  |   96   |       0       |          Y           |      N      |                   |      Permission Token      |
|       4       | REFRESH_TOKEN |  varchar  |   96   |       0       |          Y           |      N      |                   |       Refresh token        |
|       5       |  TOKEN_TYPE   |  varchar  |   64   |       0       |          Y           |      N      |                   |         token type         |
|       6       |  EXPIRES_IN   |  bigint   |   20   |       0       |          Y           |      N      |                   |      Expiration time       |
|       7       |  CREATE_TIME  | datetime  |   19   |       0       |          Y           |      N      | CURRENT_TIMESTAMP | Creation time of the token |
