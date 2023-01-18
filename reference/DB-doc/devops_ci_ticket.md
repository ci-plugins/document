# devops_ci_ticket

**Database name:** devops_ci_ticket

**Issue:** 1.0.0

**Document description:** Database document of devops_ci_ticket

|              Table name               |         description          |
| :-----------------------------------: | :--------------------------: |
|      [T_CERT](broken-reference)       | Credential information table |
| [T_CERT_ENTERPRISE](broken-reference) | Enterprise certificate form  |
|    [T_CERT_TLS](broken-reference)     |    TLS certificate table     |
|   [T_CREDENTIAL](broken-reference)    |       Credential table       |

**Table name:** T_CERT

Certificate information table

**Data column:**

| Serial number |             name             | Data type | length | Decimal place | Allowable null value | Primary key | Default value |             description              |
| :-----------: | :--------------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------: |
|       1       |          PROJECT_ID          |  varchar  |   64   |       0       |          N           |      Y      |               |               Item ID                |
|       2       |           CERT_ID            |  varchar  |  128   |       0       |          N           |      Y      |               |            Certificate ID            |
|       3       |         CERT_USER_ID         |  varchar  |   64   |       0       |          N           |      N      |               |         Certificate user ID          |
|       4       |          CERT_TYPE           |  varchar  |   32   |       0       |          N           |      N      |               |           Certificate type           |
|       5       |         CERT_REMARK          |  varchar  |  128   |       0       |          N           |      N      |               |         Certificate remarks          |
|       6       |      CERT_P12_FILE_NAME      |  varchar  |  128   |       0       |          N           |      N      |               |      Certificate p12 file name       |
|       7       |    CERT_P12_FILE_CONTENT     |   blob    | 65535  |       0       |          N           |      N      |               | Contents of the certificate p12 file |
|       8       |      CERT_MP_FILE_NAME       |  varchar  |  128   |       0       |          N           |      N      |               |   Name of the certificate mp file    |
|       9       |     CERT_MP_FILE_CONTENT     |   blob    | 65535  |       0       |          N           |      N      |               | Contents of the certificate mp file  |
|      10       |      CERT_JKS_FILE_NAME      |  varchar  |  128   |       0       |          N           |      N      |               |   Certificate Name of the jks file   |
|      11       |    CERT_JKS_FILE_CONTENT     |   blob    | 65535  |       0       |          N           |      N      |               | Contents of the certificate jsk file |
|      12       |        CERT_JKS_ALIAS        |  varchar  |  128   |       0       |          Y           |      N      |               |        Certificate jsk alias         |
|      13       | CERT_JKS_ALIAS_CREDENTIAL_ID |  varchar  |   64   |       0       |          Y           |      N      |               |    Certificate jks Credential ID     |
|      14       |     CERT_DEVELOPER_NAME      |  varchar  |  128   |       0       |          N           |      N      |               |      Certificate developer name      |
|      15       |        CERT_TEAM_NAME        |  varchar  |  128   |       0       |          N           |      N      |               |        Certificate team name         |
|      16       |          CERT_UUID           |  varchar  |   64   |       0       |          N           |      N      |               |           Certificate uuid           |
|      17       |       CERT_EXPIRE_DATE       | datetime  |   19   |       0       |          Y           |      N      |               |     Certificate expiration time      |
|      18       |       CERT_CREATE_TIME       | datetime  |   19   |       0       |          Y           |      N      |               |      Certificate creation time       |
|      19       |       CERT_UPDATE_TIME       | datetime  |   19   |       0       |          Y           |      N      |               |       Certificate renewal time       |
|      20       |        CREDENTIAL_ID         |  varchar  |   64   |       0       |          Y           |      N      |               |            Credential ID             |

**Table name:** T_CERT_ENTERPRISE

Enterprise certificate table

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |             description             |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :---------------------------------: |
|       1       |      PROJECT_ID      |  varchar  |   64   |       0       |          N           |      Y      |                     |               Item ID               |
|       2       |       CERT_ID        |  varchar  |   32   |       0       |          N           |      Y      |                     |           Certificate ID            |
|       3       |  CERT_MP_FILE_NAME   |  varchar  |  128   |       0       |          N           |      N      |                     |   Name of the certificate mp file   |
|       4       | CERT_MP_FILE_CONTENT |   blob    | 65535  |       0       |          N           |      N      |                     | Contents of the certificate mp file |
|       5       | CERT_DEVELOPER_NAME  |  varchar  |  128   |       0       |          N           |      N      |                     |     Certificate developer name      |
|       6       |    CERT_TEAM_NAME    |  varchar  |  128   |       0       |          N           |      N      |                     |        Certificate team name        |
|       7       |      CERT_UUID       |  varchar  |   64   |       0       |          N           |      N      |                     |          Certificate uuid           |
|       8       |   CERT_UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      |  CURRENT_TIMESTAMP  |             Update time             |
|       9       |   CERT_EXPIRE_DATE   | datetime  |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |     Certificate expiration time     |
|      10       |   CERT_CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |      Certificate creation time      |

**Table name:** T_CERT_TLS

**Note:** TLS certificate list

**Data column:**

| Serial number |           name            | Data type | length | Decimal place | Allowable null value | Primary key |    Default value    |                   description                    |
| :-----------: | :-----------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------------: | :----------------------------------------------: |
|       1       |        PROJECT_ID         |  varchar  |   64   |       0       |          N           |      Y      |                     |                     Item ID                      |
|       2       |          CERT_ID          |  varchar  |   32   |       0       |          N           |      Y      |                     |                  Certificate ID                  |
|       3       | CERT_SERVER_CRT_FILE_NAME |  varchar  |  128   |       0       |          N           |      N      |                     | Specifies the name of the server crt certificate |
|       4       |   CERT_SERVER_CRT_FILE    |   blob    | 65535  |       0       |          N           |      N      |                     |   Base64 encoded encrypted certificate content   |
|       5       | CERT_SERVER_KEY_FILE_NAME |  varchar  |  128   |       0       |          N           |      N      |                     |    Server key Indicates the certificate name     |
|       6       |   CERT_SERVER_KEY_FILE    |   blob    | 65535  |       0       |          N           |      N      |                     |   Base64 encoded encrypted certificate content   |
|       7       | CERT_CLIENT_CRT_FILE_NAME |  varchar  |  128   |       0       |          Y           |      N      |                     |        Name of the client crt certificate        |
|       8       |   CERT_CLIENT_CRT_FILE    |   blob    | 65535  |       0       |          Y           |      N      |                     |   Base64 encoded encrypted certificate content   |
|       9       | CERT_CLIENT_KEY_FILE_NAME |  varchar  |  128   |       0       |          Y           |      N      |                     | Client key Indicates the name of the certificate |
|      10       |   CERT_CLIENT_KEY_FILE    |   blob    | 65535  |       0       |          Y           |      N      |                     |   Base64 encoded encrypted certificate content   |
|      11       |     CERT_CREATE_TIME      | timestamp |   19   |       0       |          N           |      N      | 2019-08-01 00:00:00 |            Certificate creation time             |
|      12       |     CERT_UPDATE_TIME      | timestamp |   19   |       0       |          N           |      N      |  CURRENT_TIMESTAMP  |             Certificate renewal time             |

**Table name:** T_CREDENTIAL

**Description:** Certificate table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |    description     |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------: |
|       1       |     PROJECT_ID     |  varchar  |   64   |       0       |          N           |      Y      |               |      Item ID       |
|       2       |   CREDENTIAL_ID    |  varchar  |   64   |       0       |          N           |      Y      |               |   Credential ID    |
|       3       |  CREDENTIAL_NAME   |  varchar  |   64   |       0       |          Y           |      N      |               |  Credential name   |
|       4       | CREDENTIAL_USER_ID |  varchar  |   64   |       0       |          N           |      N      |               | Credential user ID |
|       5       |  CREDENTIAL_TYPE   |  varchar  |   64   |       0       |          N           |      N      |               |  Credential type   |
|       6       | CREDENTIAL_REMARK  |   text    | 65535  |       0       |          Y           |      N      |               |  Credential note   |
|       7       |   CREDENTIAL_V1    |   text    | 65535  |       0       |          N           |      N      |               | Credential content |
|       8       |   CREDENTIAL_V2    |   text    | 65535  |       0       |          Y           |      N      |               | Credential content |
|       9       |   CREDENTIAL_V3    |   text    | 65535  |       0       |          Y           |      N      |               | Credential content |
|      10       |   CREDENTIAL_V4    |   text    | 65535  |       0       |          Y           |      N      |               | Credential content |
|      11       |    CREATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |   Creation time    |
|      12       |    UPDATED_TIME    | datetime  |   19   |       0       |          N           |      N      |               |    Update time     |
|      13       |    UPDATE_USER     |  varchar  |   64   |       0       |          Y           |      N      |               |      modifier      |
