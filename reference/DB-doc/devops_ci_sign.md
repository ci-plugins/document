# devops_ci_sign

**Database name:** devops_ci_sign

**Issue:** 1.0.0

**Documentation description:** Database documentation for devops_ci_sign

|              Table name               |           description            |
| :-----------------------------------: | :------------------------------: |
|  [T_SIGN_HISTORY](broken-reference)   |     Signature history sheet      |
|  [T_SIGN_IPA_INFO](broken-reference)  | Signature task information table |
| [T_SIGN_IPA_UPLOAD](broken-reference) |  Signature packet upload record  |

**Table name:** T_SIGN_HISTORY

**Note:** Signature history table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |          description          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------: |
|       1       |      RESIGN_ID      |  varchar  |   64   |       0       |          N           |      Y      |                   |         Signature ID          |
|       2       |       USER_ID       |  varchar  |   64   |       0       |          N           |      N      |      system       |            User ID            |
|       3       |     PROJECT_ID      |  varchar  |   64   |       0       |          Y           |      N      |                   |            Item ID            |
|       4       |     PIPELINE_ID     |  varchar  |   64   |       0       |          Y           |      N      |                   |          Pipeline ID          |
|       5       |      BUILD_ID       |  varchar  |   64   |       0       |          Y           |      N      |                   |           Build ID            |
|       6       |       TASK_ID       |  varchar  |   64   |       0       |          Y           |      N      |                   |            Task ID            |
|       7       | TASK_EXECUTE_COUNT  |    int    |   10   |       0       |          Y           |      N      |                   |     Task execution count      |
|       8       |    ARCHIVE_TYPE     |  varchar  |   32   |       0       |          Y           |      N      |                   |        Archiving type         |
|       9       |    ARCHIVE_PATH     |   text    | 65535  |       0       |          Y           |      N      |                   |         Archive path          |
|      10       |      FILE_MD5       |  varchar  |   64   |       0       |          Y           |      N      |                   |           File MD5            |
|      11       |       STATUS        |  varchar  |   32   |       0       |          Y           |      N      |                   |             state             |
|      12       |     CREATE_TIME     | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |         Creation time         |
|      13       |      END_TIME       | timestamp |   19   |       0       |          Y           |      N      |                   |           End time            |
|      14       |   RESULT_FILE_MD5   |  varchar  |   64   |       0       |          Y           |      N      |                   |           File MD5            |
|      15       |  RESULT_FILE_NAME   |  varchar  |  512   |       0       |          Y           |      N      |                   |           File name           |
|      16       | UPLOAD_FINISH_TIME  | timestamp |   19   |       0       |          Y           |      N      |                   |    Upload completion time     |
|      17       |  UNZIP_FINISH_TIME  | timestamp |   19   |       0       |          Y           |      N      |                   | Decompression completion time |
|      18       | RESIGN_FINISH_TIME  | timestamp |   19   |       0       |          Y           |      N      |                   |   Signature completion time   |
|      19       |   ZIP_FINISH_TIME   | timestamp |   19   |       0       |          Y           |      N      |                   |    Packing completion time    |
|      20       | ARCHIVE_FINISH_TIME | timestamp |   19   |       0       |          Y           |      N      |                   |    Filing completion time     |
|      21       |    ERROR_MESSAGE    |   text    | 65535  |       0       |          Y           |      N      |                   |         Error message         |

**Table name:** T_SIGN_IPA_INFO

**Note:** Sign the task information table

**Data column:**

| Serial number |          name          | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :--------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |       RESIGN_ID        |  varchar  |   64   |       0       |          N           |      Y      |                   |                         Signature ID                         |
|       2       |        USER_ID         |  varchar  |   64   |       0       |          N           |      N      |                   |                           User ID                            |
|       3       |        WILDCARD        |    bit    |   1    |       0       |          N           |      N      |                   |            Whether to re-sign wildcard characters            |
|       4       |        CERT_ID         |  varchar  |  128   |       0       |          Y           |      N      |                   |                        Certificate ID                        |
|       5       |       PROJECT_ID       |  varchar  |   64   |       0       |          Y           |      N      |                   |                           Item ID                            |
|       6       |      PIPELINE_ID       |  varchar  |   64   |       0       |          Y           |      N      |                   |                         Pipeline ID                          |
|       7       |        BUILD_ID        |  varchar  |   64   |       0       |          Y           |      N      |                   |                           Build ID                           |
|       8       |        TASK_ID         |  varchar  |   64   |       0       |          Y           |      N      |                   |                           Task ID                            |
|       9       |      ARCHIVE_TYPE      |  varchar  |   32   |       0       |          Y           |      N      |                   |                        Archiving type                        |
|      10       |      ARCHIVE_PATH      |   text    | 65535  |       0       |          Y           |      N      |                   |                         Archive path                         |
|      11       |  MOBILE_PROVISION_ID   |  varchar  |  128   |       0       |          Y           |      N      |                   |                       Mobile device ID                       |
|      12       |    UNIVERSAL_LINKS     |   text    | 65535  |       0       |          Y           |      N      |                   |                     UniversalLink setup                      |
|      13       | KEYCHAIN_ACCESS_GROUPS |   text    | 65535  |       0       |          Y           |      N      |                   |                    Keystring access group                    |
|      14       |     REPLACE_BUNDLE     |    bit    |   1    |       0       |          Y           |      N      |                   |                 Whether to replace bundleId                  |
|      15       |    APPEX_SIGN_INFO     |   text    | 65535  |       0       |          Y           |      N      |                   | Extension application name and corresponding description file ID |
|      16       |        FILENAME        |   text    | 65535  |       0       |          Y           |      N      |                   |                          File name                           |
|      17       |       FILE_SIZE        |  bigint   |   20   |       0       |          Y           |      N      |                   |                          File size                           |
|      18       |        FILE_MD5        |  varchar  |   64   |       0       |          Y           |      N      |                   |                           File MD5                           |
|      19       |    REQUEST_CONTENT     |   text    | 65535  |       0       |          N           |      N      |                   |                        Event content                         |
|      20       |      CREATE_TIME       | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |

**Table name:** T_SIGN_IPA_UPLOAD

**Note:** Signature packet upload record

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description  |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------: |
|       1       | UPLOAD_TOKEN |  varchar  |   64   |       0       |          N           |      Y      |                   |     token     |
|       2       |   USER_ID    |  varchar  |   64   |       0       |          N           |      N      |                   |    User ID    |
|       3       |  PROJECT_ID  |  varchar  |   64   |       0       |          N           |      N      |                   |    Item ID    |
|       4       | PIPELINE_ID  |  varchar  |   64   |       0       |          N           |      N      |                   |  Pipeline ID  |
|       5       |   BUILD_ID   |  varchar  |   64   |       0       |          N           |      N      |                   |   Build ID    |
|       6       | CREATE_TIME  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time |
|       7       |  RESIGN_ID   |  varchar  |   64   |       0       |          Y           |      N      |                   | Signature ID  |
