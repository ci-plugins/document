# devops_ci_notify

**Database name:** devops_ci_notify

**Issue:** 1.0.0

**Document description:** Database document of devops_ci_notify

|                      Table name                      |          description          |
| :--------------------------------------------------: | :---------------------------: |
| [T_COMMON_NOTIFY_MESSAGE_TEMPLATE](broken-reference) |      Base template table      |
| [T_EMAILS_NOTIFY_MESSAGE_TEMPLATE](broken-reference) |     email template table      |
|          [T_NOTIFY_EMAIL](broken-reference)          |                               |
|           [T_NOTIFY_RTX](broken-reference)           |        rtx flow chart         |
|           [T_NOTIFY_SMS](broken-reference)           |                               |
|         [T_NOTIFY_WECHAT](broken-reference)          |      Wechat water table       |
|         [T_NOTIFY_WEWORK](broken-reference)          | Enterprise wechat water table |
|  [T_RTX_NOTIFY_MESSAGE_TEMPLATE](broken-reference)   |      rtx template table       |
| [T_WECHAT_NOTIFY_MESSAGE_TEMPLATE](broken-reference) |     wechat template table     |
| [T_WEWORK_NOTIFY_MESSAGE_TEMPLATE](broken-reference) |     wework template table     |

**Table name:** T_COMMON_NOTIFY_MESSAGE_TEMPLATE

Basic template table

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |        ID         |  varchar  |   32   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |   TEMPLATE_CODE   |  varchar  |   64   |       0       |          N           |      N      |               |                        Template code                         |
|       3       |   TEMPLATE_NAME   |  varchar  |  128   |       0       |          N           |      N      |               |                        Template name                         |
|       4       | NOTIFY_TYPE_SCOPE |  varchar  |   64   |       0       |          N           |      N      |               | Applicable notification types (EMAIL: Mail RTX: enterprise WECHAT: wechat: SMS: Short message) |
|       5       |     PRIORITY      |  tinyint  |   4    |       0       |          N           |      N      |               |                           priority                           |
|       6       |      SOURCE       |  tinyint  |   4    |       0       |          N           |      N      |               |                        Source of mail                        |

**Table name:** T_EMAILS_NOTIFY_MESSAGE_TEMPLATE

**Note:** email template table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |                  description                  |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :-------------------------------------------: |
|       1       |         ID         |  varchar   |    32    |       0       |          N           |      Y      |                   |                Primary key ID                 |
|       2       | COMMON_TEMPLATE_ID |  varchar   |    32    |       0       |          N           |      N      |                   |                  Template ID                  |
|       3       |      CREATOR       |  varchar   |    50    |       0       |          N           |      N      |                   |                    founder                    |
|       4       |      MODIFIOR      |  varchar   |    50    |       0       |          N           |      N      |                   |                   modifier                    |
|       5       |       SENDER       |  varchar   |   128    |       0       |          N           |      N      |      DevOps       |                  Mail sender                  |
|       6       |       TITLE        |  varchar   |   256    |       0       |          Y           |      N      |                   |              Subject of message               |
|       7       |        BODY        | mediumtext | 16777215 |       0       |          N           |      N      |                   |                 Email content                 |
|       8       |    BODY_FORMAT     |  tinyint   |    4     |       0       |          N           |      N      |                   |     Mail Format (0: text 1:html web page)     |
|       9       |     EMAIL_TYPE     |  tinyint   |    4     |       0       |          N           |      N      |                   | Mail type (0: external mail 1: internal mail) |
|      10       |    CREATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |                 Creation time                 |
|      11       |    UPDATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |                  Update time                  |

**Table name:** T_NOTIFY_EMAIL

**Explanation:**

**Data column:**

| Serial number |      name       | Data type  |  length  | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       ID        |  varchar   |    32    |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |     SUCCESS     |    bit     |    1     |       0       |          N           |      N      |               |                        Success or not                        |
|       3       |     SOURCE      |  varchar   |   255    |       0       |          N           |      N      |               |                        Source of mail                        |
|       4       |     SENDER      |  varchar   |   255    |       0       |          N           |      N      |               |                         Mail sender                          |
|       5       |       TO        |    text    |  65535   |       0       |          N           |      N      |               |                        Mail recipient                        |
|       6       |      TITLE      |  varchar   |   255    |       0       |          N           |      N      |               |                      Subject of message                      |
|       7       |      BODY       | mediumtext | 16777215 |       0       |          N           |      N      |               |                        Email content                         |
|       8       |    PRIORITY     |    int     |    10    |       0       |          N           |      N      |               |                           priority                           |
|       9       |   RETRY_COUNT   |    int     |    10    |       0       |          N           |      N      |               |                         Retry times                          |
|      10       |   LAST_ERROR    |    text    |  65535   |       0       |          Y           |      N      |               |                      Last error content                      |
|      11       |  CREATED_TIME   |  datetime  |    19    |       0       |          N           |      N      |               |                        Creation time                         |
|      12       |  UPDATED_TIME   |  datetime  |    19    |       0       |          N           |      N      |               |                         Update time                          |
|      13       |       CC        |    text    |  65535   |       0       |          Y           |      N      |               |                Cc the recipient of the email                 |
|      14       |       BCC       |    text    |  65535   |       0       |          Y           |      N      |               |               The mail is BCC to the recipient               |
|      15       |     FORMAT      |    int     |    10    |       0       |          N           |      N      |               |                            format                            |
|      16       |      TYPE       |    int     |    10    |       0       |          N           |      N      |               |                             type                             |
|      17       |   CONTENT_MD5   |  varchar   |    32    |       0       |          N           |      N      |               | Content md5 value, calculated by title and body, used when frequency is limited |
|      18       | FREQUENCY_LIMIT |    int     |    10    |       0       |          Y           |      N      |               | Frequency limit duration (unit minute) : No message is resold within n minutes |
|      19       |   TOF_SYS_ID    |  varchar   |    20    |       0       |          Y           |      N      |               |                        tof System id                         |
|      20       |   FROM_SYS_ID   |  varchar   |    20    |       0       |          Y           |      N      |               |            id of the system that sent the message            |
|      21       |  DelaySeconds   |    int     |    10    |       0       |          Y           |      N      |               |               The delay in sending, in seconds               |

**Table name:** T_NOTIFY_RTX

rtx water table

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       ID        |  varchar  |   32   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |    BATCH_ID     |  varchar  |   32   |       0       |          N           |      N      |               |        RTX Indicates the ID of the notification batch        |
|       3       |     SUCCESS     |    bit    |   1    |       0       |          N           |      N      |               |                        Success or not                        |
|       4       |     SOURCE      |  varchar  |  255   |       0       |          N           |      N      |               |                        Source of mail                        |
|       5       |     SENDER      |  varchar  |  255   |       0       |          N           |      N      |               |                         Mail sender                          |
|       6       |    RECEIVERS    |   text    | 65535  |       0       |          N           |      N      |               |                       Notify receiver                        |
|       7       |      TITLE      |  varchar  |  255   |       0       |          N           |      N      |               |                      Subject of message                      |
|       8       |      BODY       |   text    | 65535  |       0       |          N           |      N      |               |                        Email content                         |
|       9       |    PRIORITY     |    int    |   10   |       0       |          N           |      N      |               |                           priority                           |
|      10       |   RETRY_COUNT   |    int    |   10   |       0       |          N           |      N      |               |                         Retry times                          |
|      11       |   LAST_ERROR    |   text    | 65535  |       0       |          Y           |      N      |               |                      Last error content                      |
|      12       |  CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                        Creation time                         |
|      13       |  UPDATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                         Update time                          |
|      14       |   CONTENT_MD5   |  varchar  |   32   |       0       |          N           |      N      |               | Content md5 value, calculated by title and body, used when frequency is limited |
|      15       | FREQUENCY_LIMIT |    int    |   10   |       0       |          Y           |      N      |               | Frequency limit duration (unit minute) : No message is resold within n minutes |
|      16       |   TOF_SYS_id    |  varchar  |   20   |       0       |          Y           |      N      |               |                        tof System id                         |
|      17       |   FROM_SYS_ID   |  varchar  |   20   |       0       |          Y           |      N      |               |            id of the system that sent the message            |
|      18       |  DelaySeconds   |    int    |   10   |       0       |          Y           |      N      |               |               The delay in sending, in seconds               |

**Table name:** T_NOTIFY_SMS

**Explanation:**

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       ID        |  varchar  |   32   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |     SUCCESS     |    bit    |   1    |       0       |          N           |      N      |               |                        Success or not                        |
|       3       |     SOURCE      |  varchar  |  255   |       0       |          N           |      N      |               |                        Source of mail                        |
|       4       |     SENDER      |  varchar  |  255   |       0       |          N           |      N      |               |                         Mail sender                          |
|       5       |    RECEIVERS    |   text    | 65535  |       0       |          N           |      N      |               |                       Notify receiver                        |
|       6       |      BODY       |   text    | 65535  |       0       |          N           |      N      |               |                        Email content                         |
|       7       |    PRIORITY     |    int    |   10   |       0       |          N           |      N      |               |                           priority                           |
|       8       |   RETRY_COUNT   |    int    |   10   |       0       |          N           |      N      |               |                         Retry times                          |
|       9       |   LAST_ERROR    |   text    | 65535  |       0       |          Y           |      N      |               |                      Last error content                      |
|      10       |  CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                        Creation time                         |
|      11       |  UPDATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                         Update time                          |
|      12       |    BATCH_ID     |  varchar  |   32   |       0       |          N           |      N      |               |                    Notification batch ID                     |
|      13       | T_NOTIFY_SMScol |  varchar  |   45   |       0       |          Y           |      N      |               |                                                              |
|      14       |   CONTENT_MD5   |  varchar  |   32   |       0       |          N           |      N      |               | Content md5 value, calculated by title and body, used when frequency is limited |
|      15       | FREQUENCY_LIMIT |    int    |   10   |       0       |          Y           |      N      |               | Frequency limit duration (unit minute) : No message is resold within n minutes |
|      16       |   TOF_SYS_ID    |  varchar  |   20   |       0       |          Y           |      N      |               |                        tof System id                         |
|      17       |   FROM_SYS_ID   |  varchar  |   20   |       0       |          Y           |      N      |               |            id of the system that sent the message            |
|      18       |  DelaySeconds   |    int    |   10   |       0       |          Y           |      N      |               |               The delay in sending, in seconds               |

**Table name:** T_NOTIFY_WECHAT

Wechat water table

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |       ID        |  varchar  |   32   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |     SUCCESS     |    bit    |   1    |       0       |          N           |      N      |               |                        Success or not                        |
|       3       |     SOURCE      |  varchar  |  255   |       0       |          N           |      N      |               |                        Source of mail                        |
|       4       |     SENDER      |  varchar  |  255   |       0       |          N           |      N      |               |                         Mail sender                          |
|       5       |    RECEIVERS    |   text    | 65535  |       0       |          N           |      N      |               |                       Notify receiver                        |
|       6       |      BODY       |   text    | 65535  |       0       |          N           |      N      |               |                        Email content                         |
|       7       |    PRIORITY     |    int    |   10   |       0       |          N           |      N      |               |                           priority                           |
|       8       |   RETRY_COUNT   |    int    |   10   |       0       |          N           |      N      |               |                         Retry times                          |
|       9       |   LAST_ERROR    |   text    | 65535  |       0       |          Y           |      N      |               |                      Last error content                      |
|      10       |  CREATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                        Creation time                         |
|      11       |  UPDATED_TIME   | datetime  |   19   |       0       |          N           |      N      |               |                         Update time                          |
|      12       |   CONTENT_MD5   |  varchar  |   32   |       0       |          N           |      N      |               | Content md5 value, calculated by title and body, used when frequency is limited |
|      13       | FREQUENCY_LIMIT |    int    |   10   |       0       |          Y           |      N      |               | Frequency limit duration (unit minute) : No message is resold within n minutes |
|      14       |   TOF_SYS_ID    |  varchar  |   20   |       0       |          Y           |      N      |               |                        tof System id                         |
|      15       |   FROM_SYS_ID   |  varchar  |   20   |       0       |          Y           |      N      |               |            id of the system that sent the message            |
|      16       |  DelaySeconds   |    int    |   10   |       0       |          Y           |      N      |               |               The delay in sending, in seconds               |

**Table name:** T_NOTIFY_WEWORK

Enterprise wechat water table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |    description     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :----------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |                      |   Primary key ID   |
|       2       |   SUCCESS    |    bit    |   1    |       0       |          N           |      N      |                      |   Success or not   |
|       3       |  RECEIVERS   |   text    | 65535  |       0       |          N           |      N      |                      |  Notify receiver   |
|       4       |     BODY     |   text    | 65535  |       0       |          N           |      N      |                      |   Email content    |
|       5       |  LAST_ERROR  |   text    | 65535  |       0       |          Y           |      N      |                      | Last error content |
|       6       | CREATED_TIME | datetime  |   26   |       0       |          Y           |      N      | CURRENT_TIMESTAMP(6) |   Creation time    |
|       7       | UPDATED_TIME | datetime  |   26   |       0       |          Y           |      N      | CURRENT_TIMESTAMP(6) |    Update time     |

**Table name:** T_RTX_NOTIFY_MESSAGE_TEMPLATE

rtx template table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |         ID         |  varchar   |    32    |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       | COMMON_TEMPLATE_ID |  varchar   |    32    |       0       |          N           |      N      |                   |    Template ID     |
|       3       |      CREATOR       |  varchar   |    50    |       0       |          N           |      N      |                   |      founder       |
|       4       |      MODIFIOR      |  varchar   |    50    |       0       |          N           |      N      |                   |      modifier      |
|       5       |       SENDER       |  varchar   |   128    |       0       |          N           |      N      |      DevOps       |    Mail sender     |
|       6       |       TITLE        |  varchar   |   256    |       0       |          Y           |      N      |                   | Subject of message |
|       7       |        BODY        | mediumtext | 16777215 |       0       |          N           |      N      |                   |   Email content    |
|       8       |    CREATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       9       |    UPDATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_WECHAT_NOTIFY_MESSAGE_TEMPLATE

wechat template table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |         ID         |  varchar   |    32    |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       | COMMON_TEMPLATE_ID |  varchar   |    32    |       0       |          N           |      N      |                   |    Template ID     |
|       3       |      CREATOR       |  varchar   |    50    |       0       |          N           |      N      |                   |      founder       |
|       4       |      MODIFIOR      |  varchar   |    50    |       0       |          N           |      N      |                   |      modifier      |
|       5       |       SENDER       |  varchar   |   128    |       0       |          N           |      N      |      DevOps       |    Mail sender     |
|       6       |       TITLE        |  varchar   |   256    |       0       |          Y           |      N      |                   | Subject of message |
|       7       |        BODY        | mediumtext | 16777215 |       0       |          N           |      N      |                   |   Email content    |
|       8       |    CREATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       9       |    UPDATE_TIME     |  datetime  |    19    |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_WEWORK_NOTIFY_MESSAGE_TEMPLATE

**wework** template table

**Data column:**

| Serial number |        name        | Data type  |  length  | Decimal place | Allowable null value | Primary key |    Default value     |    description     |
| :-----------: | :----------------: | :--------: | :------: | :-----------: | :------------------: | :---------: | :------------------: | :----------------: |
|       1       |         ID         |  varchar   |    32    |       0       |          N           |      Y      |                      |   Primary key ID   |
|       2       | COMMON_TEMPLATE_ID |  varchar   |    32    |       0       |          N           |      N      |                      |    Template ID     |
|       3       |      CREATOR       |  varchar   |    50    |       0       |          N           |      N      |                      |      founder       |
|       4       |      MODIFIOR      |  varchar   |    50    |       0       |          N           |      N      |                      |      modifier      |
|       5       |       SENDER       |  varchar   |   128    |       0       |          N           |      N      |        DevOps        |    Mail sender     |
|       6       |       TITLE        |  varchar   |   256    |       0       |          Y           |      N      |                      | Subject of message |
|       7       |        BODY        | mediumtext | 16777215 |       0       |          N           |      N      |                      |   Email content    |
|       8       |    CREATE_TIME     |  datetime  |    26    |       0       |          N           |      N      | CURRENT_TIMESTAMP(6) |   Creation time    |
|       9       |    UPDATE_TIME     |  datetime  |    26    |       0       |          Y           |      N      |                      |    Update time     |
