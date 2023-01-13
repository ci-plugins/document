# devops_ci_project

**Database name:** devops_ci_project

**Issue:** 1.0.0

**Documentation Description:** Database documentation for devops_ci_project

|                      Table name                       |           description           |
| :---------------------------------------------------: | :-----------------------------: |
|            [T_ACTIVITY](broken-reference)             |                                 |
|            [T_FAVORITE](broken-reference)             |         Favorites list          |
|            [T_GRAY_TEST](broken-reference)            |                                 |
|       [T_MESSAGE_CODE_DETAIL](broken-reference)       | code Indicates the code details |
|             [T_NOTICE](broken-reference)              |                                 |
|             [T_PROJECT](broken-reference)             |     Item information table      |
|          [T_PROJECT_LABEL](broken-reference)          |                                 |
|        [T_PROJECT_LABEL_REL](broken-reference)        |                                 |
|             [T_SERVICE](broken-reference)             |    Service information table    |
|          [T_SERVICE_TYPE](broken-reference)           |       Service type table        |
|              [T_USER](broken-reference)               |           User table            |
| [T_USER_DAILY_FIRST_AND_LAST_LOGIN](broken-reference) |                                 |
|        [T_USER_DAILY_LOGIN](broken-reference)         |                                 |

**Table name:** T_ACTIVITY

**Explanation:**

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |      ID      |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key ID |
|       2       |     TYPE     |  varchar  |   32   |       0       |          N           |      N      |               |      type      |
|       3       |     NAME     |  varchar  |  128   |       0       |          N           |      N      |               |      name      |
|       4       | ENGLISH_NAME |  varchar  |  128   |       0       |          Y           |      N      |               |  English name  |
|       5       |     LINK     |  varchar  |  1024  |       0       |          N           |      N      |               |   Jump link    |
|       6       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      |               | Creation time  |
|       7       |    STATUS    |  varchar  |   32   |       0       |          N           |      N      |               |     state      |
|       8       |   CREATOR    |  varchar  |   32   |       0       |          N           |      N      |               |    founder     |

**Table name:** T_FAVORITE

Pay attention to the collection table

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     id     |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key id |
|       2       | service_id |  bigint   |   20   |       0       |          Y           |      N      |               |   Service id   |
|       3       |  username  |  varchar  |   64   |       0       |          Y           |      N      |               |      user      |

**Table name:** T_GRAY_TEST

**Explanation:**

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |  description   |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------: |
|       1       |     id     |  bigint   |   20   |       0       |          N           |      Y      |               | Primary key id |
|       2       | service_id |  bigint   |   20   |       0       |          Y           |      N      |               |   Service id   |
|       3       |  username  |  varchar  |   64   |       0       |          Y           |      N      |               |      user      |
|       4       |   status   |  varchar  |   64   |       0       |          Y           |      N      |               | Service status |

**Table name:** T_MESSAGE_CODE_DETAIL

code code details table

**Data column:**

| Serial number |         name         | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                      description                       |
| :-----------: | :------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------: |
|       1       |          ID          |  varchar  |   32   |       0       |          N           |      Y      |               |                      Primary key                       |
|       2       |     MESSAGE_CODE     |  varchar  |  128   |       0       |          N           |      N      |               |                       code code                        |
|       3       |     MODULE_CODE      |   char    |   2    |       0       |          N           |      N      |               |                      Module code                       |
|       4       | MESSAGE_DETAIL_ZH_CN |  varchar  |  500   |       0       |          N           |      N      |               |           Description in simplified Chinese            |
|       5       | MESSAGE_DETAIL_ZH_TW |  varchar  |  500   |       0       |          Y           |      N      |               | Describe information in traditional Chinese characters |
|       6       |  MESSAGE_DETAIL_EN   |  varchar  |  500   |       0       |          Y           |      N      |               |            English description information             |

**Table name:** T_NOTICE

**Explanation:**

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |          description          |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------------------: |
|       1       |       ID       |  bigint   |   20   |       0       |          N           |      Y      |                   |        Primary key ID         |
|       2       |  NOTICE_TITLE  |  varchar  |  100   |       0       |          N           |      N      |                   |     Title of announcement     |
|       3       |  EFFECT_DATE   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |        Effective date         |
|       4       |  INVALID_DATE  | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |        Expiration date        |
|       5       |  CREATE_DATE   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |         Creation date         |
|       6       |  UPDATE_DATE   | timestamp |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |          Update date          |
|       7       | NOTICE_CONTENT |   text    | 65535  |       0       |          N           |      N      |                   |     Announcement content      |
|       8       |  REDIRECT_URL  |  varchar  |  200   |       0       |          Y           |      N      |                   |         Jump address          |
|       9       |  NOTICE_TYPE   |  tinyint  |   4    |       0       |          N           |      N      |         0         | Message type :0. Pop-up box 1 |

**Table name:** T_PROJECT

Project information table

**Data column:**

| Serial number |         name          | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :-------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |          ID           |  bigint   |   20   |       0       |          N           |      Y      |               |                        Primary key ID                        |
|       2       |      created_at       | timestamp |   19   |       0       |          Y           |      N      |               |                        Creation time                         |
|       3       |      updated_at       | timestamp |   19   |       0       |          Y           |      N      |               |                         Update time                          |
|       4       |      deleted_at       | timestamp |   19   |       0       |          Y           |      N      |               |                        Deletion time                         |
|       5       |         extra         |   text    | 65535  |       0       |          Y           |      N      |               |                    Additional information                    |
|       6       |        creator        |  varchar  |   32   |       0       |          Y           |      N      |               |                           founder                            |
|       7       |      description      |   text    | 65535  |       0       |          Y           |      N      |               |                         description                          |
|       8       |         kind          |    int    |   10   |       0       |          Y           |      N      |               |                        Container type                        |
|       9       |       cc_app_id       |  bigint   |   20   |       0       |          Y           |      N      |               |                        Application ID                        |
|      10       |      cc_app_name      |  varchar  |   64   |       0       |          Y           |      N      |               |                       Application name                       |
|      11       |      is_offlined      |    bit    |   1    |       0       |          Y           |      N      |     B '0'     |                      Deactivate or not                       |
|      12       |      PROJECT_ID       |  varchar  |   32   |       0       |          N           |      N      |               |                           Item ID                            |
|      13       |     project_name      |  varchar  |   64   |       0       |          N           |      N      |               |                         Project name                         |
|      14       |     english_name      |  varchar  |   64   |       0       |          N           |      N      |               |                         English name                         |
|      15       |        updator        |  varchar  |   32   |       0       |          Y           |      N      |               |                           updater                            |
|      16       |     project_type      |    int    |   10   |       0       |          Y           |      N      |               |                          Item type                           |
|      17       |        use_bk         |    bit    |   1    |       0       |          Y           |      N      |     B '1'     |                 Whether to use a blue whale                  |
|      18       |      deploy_type      |   text    | 65535  |       0       |          Y           |      N      |               |                       Deployment type                        |
|      19       |         bg_id         |  bigint   |   20   |       0       |          Y           |      N      |               |                      Business group ID                       |
|      20       |        bg_name        |  varchar  |  255   |       0       |          Y           |      N      |               |                     Business group name                      |
|      21       |        dept_id        |  bigint   |   20   |       0       |          Y           |      N      |               |     The project belongs to the secondary organization ID     |
|      22       |       dept_name       |  varchar  |  255   |       0       |          Y           |      N      |               | Name of the secondary organization to which the project belongs |
|      23       |       center_id       |  bigint   |   20   |       0       |          Y           |      N      |               |                          Center ID                           |
|      24       |      center_name      |  varchar  |  255   |       0       |          Y           |      N      |               |                         Central name                         |
|      25       |        data_id        |  bigint   |   20   |       0       |          Y           |      N      |               |                           Data ID                            |
|      26       |      is_secrecy       |    bit    |   1    |       0       |          Y           |      N      |     B '0'     |                    Confidentiality or not                    |
|      27       | is_helm_chart_enabled |    bit    |   1    |       0       |          Y           |      N      |     B '0'     |              Whether to enable chart activation              |
|      28       |    approval_status    |    int    |   10   |       0       |          Y           |      N      |       1       |                         Audit status                         |
|      29       |       logo_addr       |   text    | 65535  |       0       |          Y           |      N      |               |                         logo address                         |
|      30       |       approver        |  varchar  |   32   |       0       |          Y           |      N      |               |                           approver                           |
|      31       |        remark         |   text    | 65535  |       0       |          Y           |      N      |               |                           comment                            |
|      32       |     approval_time     | timestamp |   19   |       0       |          Y           |      N      |               |                        Approval time                         |
|      33       |    creator_bg_name    |  varchar  |  128   |       0       |          Y           |      N      |               |                 Creator business group name                  |
|      34       |   creator_dept_name   |  varchar  |  128   |       0       |          Y           |      N      |               | Creator Name of the secondary organization to which the project belongs |
|      35       |  creator_center_name  |  varchar  |  128   |       0       |          Y           |      N      |               |                     Creator center name                      |
|      36       |   hybrid_cc_app_id    |  bigint   |   20   |       0       |          Y           |      N      |               |                        Application ID                        |
|      37       |    enable_external    |    bit    |   1    |       0       |          Y           |      N      |               |         Whether the builder can access the Internet          |
|      38       |      enable_idc       |    bit    |   1    |       0       |          Y           |      N      |               |             Whether the IDC builder is supported             |
|      39       |        enabled        |    bit    |   1    |       0       |          Y           |      N      |               |                        Enable or not                         |
|      40       |        CHANNEL        |  varchar  |   32   |       0       |          N           |      N      |      BS       |                       Project channel                        |
|      41       |    pipeline_limit     |    int    |   10   |       0       |          Y           |      N      |      500      |               Upper limit of pipeline quantity               |
|      42       |      router_tag       |  varchar  |   32   |       0       |          Y           |      N      |               |                      Gateway route tags                      |
|      43       |      relation_id      |  varchar  |   32   |       0       |          Y           |      N      |               |                Extended system association ID                |

**Table name:** T_PROJECT_LABEL

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |  Primary key ID   |
|       2       | LABEL_NAME  |  varchar  |   45   |       0       |          N           |      N      |                   |    Label name     |
|       3       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time   |
|       4       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Modification time |

**Table name:** T_PROJECT_LABEL_REL

**Explanation:**

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |  Primary key ID   |
|       2       |  LABEL_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |      Tag ID       |
|       3       | PROJECT_ID  |  varchar  |   32   |       0       |          N           |      N      |                   |      Item ID      |
|       4       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time   |
|       5       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Modification time |

**Table name:** T_SERVICE

Service information table

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key | Default value |            description            |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :-------------------------------: |
|       1       |        id         |  bigint   |   20   |       0       |          N           |      Y      |               |                id                 |
|       2       |       name        |  varchar  |   64   |       0       |          Y           |      N      |               |               name                |
|       3       |   english_name    |  varchar  |   64   |       0       |          Y           |      N      |               |           English name            |
|       4       |  service_type_id  |  bigint   |   20   |       0       |          Y           |      N      |               |          Service type ID          |
|       5       |       link        |  varchar  |  255   |       0       |          Y           |      N      |               |             Jump link             |
|       6       |     link_new      |  varchar  |  255   |       0       |          Y           |      N      |               |           New jump link           |
|       7       |    inject_type    |  varchar  |   64   |       0       |          Y           |      N      |               |          Injection type           |
|       8       |    iframe_url     |  varchar  |  255   |       0       |          Y           |      N      |               |         iframeUrl address         |
|       9       |      css_url      |  varchar  |  255   |       0       |          Y           |      N      |               |          cssUrl address           |
|      10       |      js_url       |  varchar  |  255   |       0       |          Y           |      N      |               |           jsUrl address           |
|      11       | show_project_list |    bit    |   1    |       0       |          Y           |      N      |               | Whether to display it on the page |
|      12       |     show_nav      |    bit    |   1    |       0       |          Y           |      N      |               |              showNav              |
|      13       |  project_id_type  |  varchar  |   64   |       0       |          Y           |      N      |               |           Item ID type            |
|      14       |      status       |  varchar  |   64   |       0       |          Y           |      N      |               |               state               |
|      15       |   created_user    |  varchar  |   64   |       0       |          Y           |      N      |               |              founder              |
|      16       |   created_time    | datetime  |   19   |       0       |          Y           |      N      |               |           Creation time           |
|      17       |   updated_user    |  varchar  |   64   |       0       |          Y           |      N      |               |             modifier              |
|      18       |   updated_time    | datetime  |   19   |       0       |          Y           |      N      |               |         Modification time         |
|      19       |      deleted      |    bit    |   1    |       0       |          Y           |      N      |               |           Delete or not           |
|      20       |   gray_css_url    |  varchar  |  255   |       0       |          Y           |      N      |               |     Grayscale cssUrl address      |
|      21       |    gray_js_url    |  varchar  |  255   |       0       |          Y           |      N      |               |      Grayscale jsUrl address      |
|      22       |     logo_url      |  varchar  |  256   |       0       |          Y           |      N      |               |           logo address            |
|      23       |    web_socket     |   text    | 65535  |       0       |          Y           |      N      |               |      webSocket support page       |
|      24       |      weight       |    int    |   10   |       0       |          Y           |      N      |               |              weight               |
|      25       |  gray_iframe_url  |  varchar  |  255   |       0       |          Y           |      N      |               |    Grayscale iframeUrl address    |
|      26       |    new_window     |    bit    |   1    |       0       |          Y           |      N      |     B '0'     |     Whether to open a new TAB     |
|      27       |   new_windowUrl   |  varchar  |  200   |       0       |          Y           |      N      |               |          New TAB address          |

**Table name:** T_SERVICE_TYPE

Service type table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |     description      |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :------------------: |
|       1       |      ID       |  bigint   |   20   |       0       |          N           |      Y      |               |    Primary key ID    |
|       2       |     title     |  varchar  |   64   |       0       |          Y           |      N      |               |  Subject of message  |
|       3       | english_title |  varchar  |   64   |       0       |          Y           |      N      |               | English mail subject |
|       4       | created_user  |  varchar  |   64   |       0       |          Y           |      N      |               |       founder        |
|       5       | created_time  | datetime  |   19   |       0       |          Y           |      N      |               |    Creation time     |
|       6       | updated_user  |  varchar  |   64   |       0       |          Y           |      N      |               |       modifier       |
|       7       | updated_time  | datetime  |   19   |       0       |          Y           |      N      |               |  Modification time   |
|       8       |    deleted    |    bit    |   1    |       0       |          Y           |      N      |               |    Delete or not     |
|       9       |    weight     |    int    |   10   |       0       |          Y           |      N      |               |        weight        |

**Table name:** T_USER

User table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |   USER_ID   |  varchar  |   64   |       0       |          N           |      Y      |                   |                           User ID                            |
|       2       |    NAME     |  varchar  |   64   |       0       |          N           |      N      |                   |                             name                             |
|       3       |    BG_ID    |    int    |   10   |       0       |          N           |      N      |                   |                      Business group ID                       |
|       4       |   BG_NAME   |  varchar  |  256   |       0       |          N           |      N      |                   |                     Business group name                      |
|       5       |   DEPT_ID   |    int    |   10   |       0       |          Y           |      N      |                   |     The project belongs to the secondary organization ID     |
|       6       |  DEPT_NAME  |  varchar  |  256   |       0       |          Y           |      N      |                   | Name of the secondary organization to which the project belongs |
|       7       |  CENTER_ID  |    int    |   10   |       0       |          Y           |      N      |                   |                          Center ID                           |
|       8       | CENTER_NAME |  varchar  |  256   |       0       |          Y           |      N      |                   |                         Central name                         |
|       9       |  GROYP_ID   |    int    |   10   |       0       |          Y           |      N      |                   |                        User group ID                         |
|      10       | GROUP_NAME  |  varchar  |  256   |       0       |          Y           |      N      |                   |                       User group name                        |
|      11       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      |                   |                        Creation time                         |
|      12       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_USER_DAILY_FIRST_AND_LAST_LOGIN

**Explanation:**

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       |        ID        |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID  |
|       2       |     USER_ID      |  varchar  |   64   |       0       |          N           |      N      |               |     User ID      |
|       3       |       DATE       |   date    |   10   |       0       |          N           |      N      |               |       date       |
|       4       | FIRST_LOGIN_TIME | datetime  |   19   |       0       |          N           |      N      |               | First login time |
|       5       | LAST_LOGIN_TIME  | datetime  |   19   |       0       |          N           |      N      |               | Last login time  |

**Table name:** T_USER_DAILY_LOGIN

**Explanation:**

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       |     ID     |  bigint   |   20   |       0       |          N           |      Y      |               |  Primary key ID  |
|       2       |  USER_ID   |  varchar  |   64   |       0       |          N           |      N      |               |     User ID      |
|       3       |    DATE    |   date    |   10   |       0       |          N           |      N      |               |       date       |
|       4       | LOGIN_TIME | datetime  |   19   |       0       |          N           |      N      |               |    Login time    |
|       5       |     OS     |  varchar  |   32   |       0       |          N           |      N      |               | Operating system |
|       6       |     IP     |  varchar  |   32   |       0       |          N           |      N      |               |    ip address    |
