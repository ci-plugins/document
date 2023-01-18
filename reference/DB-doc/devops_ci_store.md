# devops_ci_store

**Database name:** devops_ci_store

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_store

|                   Table name                    |                         description                          |
| :---------------------------------------------: | :----------------------------------------------------------: |
|           [T_APPS](broken-reference)            |          Compile the environment information table           |
|          [T_APP_ENV](broken-reference)          |            Compile the environment variable table            |
|        [T_APP_VERSION](broken-reference)        |        Compile environment version information table         |
|           [T_ATOM](broken-reference)            |                     Pipelined atom table                     |
|     [T_ATOM_APPROVE_REL](broken-reference)      |               Plug-in audit association table                |
|    [T_ATOM_BUILD_APP_REL](broken-reference)     | Pipelined atoms build and compile environment association tables |
|      [T_ATOM_BUILD_INFO](broken-reference)      |            Pipelined atom build information table            |
| [T_ATOM_DEV_LANGUAGE_ENV_VAR](broken-reference) |        Plug-in environment variable information table        |
|       [T_ATOM_ENV_INFO](broken-reference)       |   Pipelined atomic execution environment information table   |
|       [T_ATOM_FEATURE](broken-reference)        |          Atomic plug-in property information table           |
|      [T_ATOM_LABEL_REL](broken-reference)       |               Atom and label association table               |
|       [T_ATOM_OFFLINE](broken-reference)        |                   Atom off the shelf table                   |
|     [T_ATOM_OPERATE_LOG](broken-reference)      |             Pipelined atomic operation log table             |
|  [T_ATOM_PIPELINE_BUILD_REL](broken-reference)  |          Pipelining atoms build association tables           |
|     [T_ATOM_PIPELINE_REL](broken-reference)     |        Pipeline atoms and pipeline association table         |
|     [T_ATOM_VERSION_LOG](broken-reference)      |              Pipelined atomic version log table              |
|      [T_BUILD_RESOURCE](broken-reference)       |         Pipelined builds resource information tables         |
|      [T_BUSINESS_CONFIG](broken-reference)      |              store service configuration table               |
|         [T_CATEGORY](broken-reference)          |                  Category information table                  |
|         [T_CLASSIFY](broken-reference)          |       Pipeline atomic classification information table       |
|         [T_CONTAINER](broken-reference)         | Pipelined container table (here container is not the same concept as Docker, but an element of the pipelined model) |
|  [T_CONTAINER_RESOURCE_REL](broken-reference)   |   Pipelined container and build resource association table   |
|           [T_IMAGE](broken-reference)           |                   Mirror information table                   |
|     [T_IMAGE_AGENT_TYPE](broken-reference)      |           Image and machine type association table           |
|    [T_IMAGE_CATEGORY_REL](broken-reference)     |     Mirror image and category association relation table     |
|       [T_IMAGE_FEATURE](broken-reference)       |                 Mirror characteristic table                  |
|      [T_IMAGE_LABEL_REL](broken-reference)      |              Image and label association table               |
|     [T_IMAGE_VERSION_LOG](broken-reference)     |                 Mirror the version log table                 |
|           [T_LABEL](broken-reference)           |                Atomic label information table                |
|           [T_LOGO](broken-reference)            |                 Store logo information sheet                 |
|          [T_REASON](broken-reference)           |                    Cause definition table                    |
|        [T_REASON_REL](broken-reference)         |               Cause and component association                |
|       [T_STORE_APPROVE](broken-reference)       |                          Audit form                          |
|    [T_STORE_BUILD_APP_REL](broken-reference)    | store builds the relational tables associated with the build environment |
|     [T_STORE_BUILD_INFO](broken-reference)      |           store component build information table            |
|       [T_STORE_COMMENT](broken-reference)       |           store component review information sheet           |
|   [T_STORE_COMMENT_PRAISE](broken-reference)    |        store component review like information table         |
|    [T_STORE_COMMENT_REPLY](broken-reference)    |        store component review reply information sheet        |
|      [T_STORE_DEPT_REL](broken-reference)       |   Store component and association table with organization    |
|       [T_STORE_ENV_VAR](broken-reference)       |            Environment variable information table            |
|     [T_STORE_MEDIA_INFO](broken-reference)      |                   Media information table                    |
|       [T_STORE_MEMBER](broken-reference)        |           store component member information table           |
|       [T_STORE_OPT_LOG](broken-reference)       |                  store operation log table                   |
| [T_STORE_PIPELINE_BUILD_REL](broken-reference)  |       The store component builds the association table       |
|    [T_STORE_PIPELINE_REL](broken-reference)     | Store component and relationship table associated with pipeline |
|     [T_STORE_PROJECT_REL](broken-reference)     | The store component is associated with the item in a relational table |
|       [T_STORE_RELEASE](broken-reference)       |     store component publishes upgrade information table      |
|    [T_STORE_SENSITIVE_API](broken-reference)    |          Sensitive API interface information table           |
|   [T_STORE_SENSITIVE_CONF](broken-reference)    |              store private configuration table               |
|     [T_STORE_STATISTICS](broken-reference)      |                    store statistics table                    |
|  [T_STORE_STATISTICS_DAILY](broken-reference)   |                 store Daily statistics table                 |
|  [T_STORE_STATISTICS_TOTAL](broken-reference)   |                 store Full statistics table                  |
|         [T_TEMPLATE](broken-reference)          |                  Template information table                  |
|   [T_TEMPLATE_CATEGORY_REL](broken-reference)   |       Template and category association relation table       |
|    [T_TEMPLATE_LABEL_REL](broken-reference)     |             Template and label association table             |

**Table name:** T_APPS

Compile environment information table

**Data column:**

| Serial number |   name   | Data type | length | Decimal place | Allowable null value | Primary key | Default value |   description    |
| :-----------: | :------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------: |
|       1       |    ID    |    int    |   10   |       0       |          N           |      Y      |               |  Primary key ID  |
|       2       |   NAME   |  varchar  |   64   |       0       |          N           |      N      |               |       name       |
|       3       |    OS    |  varchar  |   32   |       0       |          N           |      N      |               | Operating system |
|       4       | BIN_PATH |  varchar  |   64   |       0       |          Y           |      N      |               |  Execution path  |

**Table name:** T_APP_ENV

Compile environment variable table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |     ID      |    int    |   10   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       |   APP_ID    |    int    |   10   |       0       |          N           |      N      |               | Compile environment ID |
|       3       |    PATH     |  varchar  |   32   |       0       |          N           |      N      |               |          path          |
|       4       |    NAME     |  varchar  |   32   |       0       |          N           |      N      |               |          name          |
|       5       | DESCRIPTION |  varchar  |   64   |       0       |          N           |      N      |               |      description       |

**Table name:** T_APP_VERSION

Compile environment version information table

**Data column:**

| Serial number |  name   | Data type | length | Decimal place | Allowable null value | Primary key | Default value |      description       |
| :-----------: | :-----: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :--------------------: |
|       1       |   ID    |    int    |   10   |       0       |          N           |      Y      |               |     Primary key ID     |
|       2       | APP_ID  |    int    |   10   |       0       |          N           |      N      |               | Compile environment ID |
|       3       | VERSION |  varchar  |   32   |       0       |          Y           |      N      |               |     Version number     |

**Table name:** T_ATOM

Pipeline atomic table

**Data column:**

| Serial number |         name          | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-------------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |          ID           |  varchar  |   32   |       0       |          N           |      Y      |                   |                        Primary key ID                        |
|       2       |         NAME          |  varchar  |   64   |       0       |          N           |      N      |                   |                             name                             |
|       3       |       ATOM_CODE       |  varchar  |   64   |       0       |          N           |      N      |                   |              The unique identity of the plug-in              |
|       4       |      CLASS_TYPE       |  varchar  |   64   |       0       |          N           |      N      |                   |                        Plug-in class                         |
|       5       |     SERVICE_SCOPE     |  varchar  |  256   |       0       |          N           |      N      |                   |                       Effective scope                        |
|       6       |       JOB_TYPE        |  varchar  |   20   |       0       |          Y           |      N      |                   | Job type: AGENT: compilation environment, AGENT_LESS: no compilation environment |
|       7       |          OS           |  varchar  |  100   |       0       |          N           |      N      |                   |                       Operating system                       |
|       8       |      CLASSIFY_ID      |  varchar  |   32   |       0       |          N           |      N      |                   |                         Category ID                          |
|       9       |       DOCS_LINK       |  varchar  |  256   |       0       |          Y           |      N      |                   |                      Document jump link                      |
|      10       |       ATOM_TYPE       |  tinyint  |   4    |       0       |          N           |      N      |         1         |                         Atomic type                          |
|      11       |      ATOM_STATUS      |  tinyint  |   4    |       0       |          N           |      N      |                   |                         Atomic state                         |
|      12       |    ATOM_STATUS_MSG    |  varchar  |  1024  |       0       |          Y           |      N      |                   |                  Plug-in status information                  |
|      13       |        SUMMARY        |  varchar  |  256   |       0       |          Y           |      N      |                   |                         introduction                         |
|      14       |      DESCRIPTION      |   text    | 65535  |       0       |          Y           |      N      |                   |                         description                          |
|      15       |       CATEGROY        |  tinyint  |   4    |       0       |          N           |      N      |         1         |                           category                           |
|      16       |        VERSION        |  varchar  |   20   |       0       |          N           |      N      |                   |                        Version number                        |
|      17       |       LOGO_URL        |  varchar  |  256   |       0       |          Y           |      N      |                   |                       LOGOURL address                        |
|      18       |         ICON          |   text    | 65535  |       0       |          Y           |      N      |                   |                         Plug-in icon                         |
|      19       |     DEFAULT_FLAG      |    bit    |   1    |       0       |          N           |      N      |       B '0'       |                Whether it is the default atom                |
|      20       |      LATEST_FLAG      |    bit    |   1    |       0       |          N           |      N      |                   |            Whether it is the latest version atom             |
|      21       |  BUILD_LESS_RUN_FLAG  |    bit    |   1    |       0       |          Y           |      N      |                   | No build environment Indicates whether an atom can run in a build environment |
|      22       |  REPOSITORY_HASH_ID   |  varchar  |   64   |       0       |          Y           |      N      |                   |                      Code base hash ID                       |
|      23       |       CODE_SRC        |  varchar  |  256   |       0       |          Y           |      N      |                   |                        Code base link                        |
|      24       |       PAY_FLAG        |    bit    |   1    |       0       |          Y           |      N      |       B '1'       |                  Whether it is free or not                   |
|      25       | HTML_TEMPLATE_VERSION |  varchar  |   10   |       0       |          N           |      N      |        1.1        |             Front-end rendering template version             |
|      26       |         PROPS         |   text    | 65535  |       0       |          Y           |      N      |                   | Customize the JSON string of the extension container's front end form property fields |
|      27       |         DATA          |   text    | 65535  |       0       |          Y           |      N      |                   |                        Reserved field                        |
|      28       |       PUBLISHER       |  varchar  |   50   |       0       |          N           |      N      |      system       |                       Atomic publisher                       |
|      29       |        WEIGHT         |    int    |   10   |       0       |          Y           |      N      |                   |                            weight                            |
|      30       |        CREATOR        |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|      31       |       MODIFIER        |  varchar  |   50   |       0       |          N           |      N      |      system       |                           modifier                           |
|      32       |      CREATE_TIME      | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      33       |      UPDATE_TIME      | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|      34       |   VISIBILITY_LEVEL    |    int    |   10   |       0       |          N           |      N      |         0         |                        Visible range                         |
|      35       |       PUB_TIME        | datetime  |   19   |       0       |          Y           |      N      |                   |                         Release time                         |
|      36       |    PRIVATE_REASON     |  varchar  |  256   |       0       |          Y           |      N      |                   |             Plug-in codebase is not open source              |
|      37       |      DELETE_FLAG      |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |                        Delete or not                         |

**Table name:** T_ATOM_APPROVE_REL

Plug-in audit association table

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |            description             |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------------: |
|       1       |        ID         |  varchar  |   32   |       0       |          N           |      Y      |                   |           Primary key ID           |
|       2       |     ATOM_CODE     |  varchar  |   64   |       0       |          N           |      N      |                   | The unique identity of the plug-in |
|       3       | TEST_PROJECT_CODE |  varchar  |   32   |       0       |          N           |      N      |                   |         Debug item coding          |
|       4       |    APPROVE_ID     |  varchar  |   32   |       0       |          N           |      N      |                   |            Approval ID             |
|       5       |      CREATOR      |  varchar  |   50   |       0       |          N           |      N      |      system       |              founder               |
|       6       |     MODIFIER      |  varchar  |   50   |       0       |          N           |      N      |      system       |           Recent reviser           |
|       7       |    CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |           Creation time            |
|       8       |    UPDATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |            Update time             |

**Table name:** T_ATOM_BUILD_APP_REL

Pipeline atomic construction and compilation environment association table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |       ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |                        Primary key ID                        |
|       2       | BUILD_INFO_ID  |  varchar  |   32   |       0       |          N           |      N      |                   |                     Build information Id                     |
|       3       | APP_VERSION_ID |    int    |   10   |       0       |          Y           |      N      |                   | Build environment version Id(corresponding to T_APP_VERSION primary key) |
|       4       |    CREATOR     |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       5       |    MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |                           modifier                           |
|       6       |  CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|       7       |  UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_ATOM_BUILD_INFO

Pipeline atomic build information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |             description              |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |            Primary key ID            |
|       2       |      LANGUAGE       |  varchar  |   64   |       0       |          Y           |      N      |                   |               language               |
|       3       |       SCRIPT        |   text    | 65535  |       0       |          N           |      N      |                   |            Package script            |
|       4       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |               founder                |
|       5       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |               modifier               |
|       6       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |            Creation time             |
|       7       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |             Update time              |
|       8       |   REPOSITORY_PATH   |  varchar  |  500   |       0       |          Y           |      N      |                   |          Code storage path           |
|       9       | SAMPLE_PROJECT_PATH |  varchar  |  500   |       0       |          N           |      N      |                   |         Sample project path          |
|      10       |       ENABLE        |    bit    |   1    |       0       |          N           |      N      |       B '1'       | Enable or disable 1 Enable 0 Disable |

**Table name:** T_ATOM_DEV_LANGUAGE_ENV_VAR

Plug-in environment variable information table

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |       ID        |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |    LANGUAGE     |  varchar  |   64   |       0       |          N           |      N      |                   |                 Plug-in development language                 |
|       3       |     ENV_KEY     |  varchar  |   64   |       0       |          N           |      N      |                   |                Environment variable key value                |
|       4       |    ENV_VALUE    |  varchar  |  256   |       0       |          N           |      N      |                   |    value Indicates the value of the environment variable     |
|       5       | BUILD_HOST_TYPE |  varchar  |   32   |       0       |          N           |      N      |                   | Applicable construction machine type PUBLIC: public construction machine, THIRD: third-party construction machine, ALL: all |
|       6       |  BUILD_HOST_OS  |  varchar  |   32   |       0       |          N           |      N      |                   | Applicable to the builder operating systems WINDOWS:windows builder, LINUX:linux builder, MAC_OS:mac builder, ALL: all |
|       7       |     CREATOR     |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       8       |    MODIFIER     |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|       9       |   CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      10       |   UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_ATOM_ENV_INFO

Pipeline atomic execution environment information table

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |        ID        |  varchar  |   32   |       0       |          N           |      Y      |                   |                        Primary key ID                        |
|       2       |     ATOM_ID      |  varchar  |   32   |       0       |          N           |      N      |                   |                          Plug-in Id                          |
|       3       |     PKG_PATH     |  varchar  |  1024  |       0       |          N           |      N      |                   |                  Installation package path                   |
|       4       |     LANGUAGE     |  varchar  |   64   |       0       |          Y           |      N      |                   |                           language                           |
|       5       |   MIN_VERSION    |  varchar  |   20   |       0       |          Y           |      N      |                   | Support for the minimum version of the plug-in development language |
|       6       |      TARGET      |  varchar  |  256   |       0       |          N           |      N      |                   |                   Plug-in execution entry                    |
|       7       |   SHA_CONTENT    |  varchar  |  1024  |       0       |          Y           |      N      |                   |               The plug-in SHA signature string               |
|       8       |     PRE_CMD      |   text    | 65535  |       0       |          Y           |      N      |                   |              The plug-in runs the front command              |
|       9       |     CREATOR      |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|      10       |     MODIFIER     |  varchar  |   50   |       0       |          N           |      N      |      system       |                           modifier                           |
|      11       |   CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      12       |   UPDATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|      13       |     PKG_NAME     |  varchar  |  256   |       0       |          Y           |      N      |                   |                     Plug-in package name                     |
|      14       | POST_ENTRY_PARAM |  varchar  |   64   |       0       |          Y           |      N      |                   |                       Entry parameter                        |
|      15       |  POST_CONDITION  |  varchar  |  1024  |       0       |          Y           |      N      |                   |                     Execution condition                      |

**Table name:** T_ATOM_FEATURE

Atomic plug-in feature information table

**Data column:**

| Serial number |       name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |              description               |
| :-----------: | :--------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------------------------------: |
|       1       |        ID        |  varchar  |   32   |       0       |          N           |      Y      |                   |             Primary key ID             |
|       2       |    ATOM_CODE     |  varchar  |   64   |       0       |          N           |      N      |                   |   The unique identity of the plug-in   |
|       3       | VISIBILITY_LEVEL |    int    |   10   |       0       |          N           |      N      |         0         |             Visible range              |
|       4       |     CREATOR      |  varchar  |   50   |       0       |          N           |      N      |      system       |                founder                 |
|       5       |     MODIFIER     |  varchar  |   50   |       0       |          N           |      N      |      system       |                modifier                |
|       6       |   CREATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |             Creation time              |
|       7       |   UPDATE_TIME    | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |              Update time               |
|       8       |  RECOMMEND_FLAG  |    bit    |   1    |       0       |          Y           |      N      |       B '1'       |          Whether to recommend          |
|       9       |  PRIVATE_REASON  |  varchar  |  256   |       0       |          Y           |      N      |                   |  Plug-in codebase is not open source   |
|      10       |   DELETE_FLAG    |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |             Delete or not              |
|      11       |    YAML_FLAG     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |        yaml available identity         |
|      12       |   QUALITY_FLAG   |    bit    |   1    |       0       |          Y           |      N      |       B '0'       | The quality red line can be identified |

**Table name:** T_ATOM_LABEL_REL

Atom and label association table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       |  LABEL_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |     Tag ID     |
|       3       |   ATOM_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |   Plug-in Id   |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |    founder     |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier    |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time   |

**Table name:** T_ATOM_OFFLINE

Atom off the shelf table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |            description             |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |           Primary key ID           |
|       2       |  ATOM_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | The unique identity of the plug-in |
|       3       | BUFFER_DAY  |  tinyint  |   4    |       0       |          N           |      N      |                   |                                    |
|       4       | EXPIRE_TIME | datetime  |   19   |       0       |          N           |      N      |                   |          Expiration time           |
|       5       |   STATUS    |  tinyint  |   4    |       0       |          N           |      N      |                   |               state                |
|       6       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |              founder               |
|       7       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |              modifier              |
|       8       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |           Creation time            |
|       9       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |            Update time             |

**Table name:** T_ATOM_OPERATE_LOG

Pipeline atomic operation log table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       |   ATOM_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |   Plug-in Id   |
|       3       |   CONTENT   |   text    | 65535  |       0       |          N           |      N      |                   |  Log content   |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |    founder     |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier    |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time   |

**Table name:** T_ATOM_PIPELINE_BUILD_REL

Pipelined atoms build association tables

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       |   ATOM_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |   Plug-in Id   |
|       3       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |                   |  Pipeline ID   |
|       4       |  BUILD_ID   |  varchar  |   34   |       0       |          N           |      N      |                   |    Build ID    |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |    founder     |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier    |
|       7       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |
|       8       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time   |

**Table name:** T_ATOM_PIPELINE_REL

**Pipeline** atom and pipeline correlation table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |            description             |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |           Primary key ID           |
|       2       |  ATOM_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | The unique identity of the plug-in |
|       3       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |                   |            Pipeline ID             |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |              founder               |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |              modifier              |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |           Creation time            |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |            Update time             |

**Table name:** T_ATOM_VERSION_LOG

**Pipeline** atomic version log table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |   description    |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |  Primary key ID  |
|       2       |   ATOM_ID    |  varchar  |   32   |       0       |          N           |      N      |                   |    Plug-in Id    |
|       3       | RELEASE_TYPE |  tinyint  |   4    |       0       |          N           |      N      |                   | Publication type |
|       4       |   CONTENT    |   text    | 65535  |       0       |          N           |      N      |                   |   Log content    |
|       5       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |     founder      |
|       6       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |     modifier     |
|       7       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Creation time   |
|       8       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Update time    |

**Table name:** T_BUILD_RESOURCE

**Pipeline** construction resource information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |          description           |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |         Primary key ID         |
|       2       | BUILD_RESOURCE_CODE |  varchar  |   30   |       0       |          N           |      N      |                   |      Build resource code       |
|       3       | BUILD_RESOURCE_NAME |  varchar  |   45   |       0       |          N           |      N      |                   |      Build resource name       |
|       4       |    DEFAULT_FLAG     |    bit    |   1    |       0       |          N           |      N      |       B '0'       | Whether it is the default atom |
|       5       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |            founder             |
|       6       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |            modifier            |
|       7       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |         Creation time          |
|       8       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |          Update time           |

**Table name:** T_BUSINESS_CONFIG

**Note:** store service configuration table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key | Default value |             description              |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------: |
|       1       |    BUSINESS    |  varchar  |   64   |       0       |          N           |      N      |               |            Business name             |
|       2       |    FEATURE     |  varchar  |   64   |       0       |          N           |      N      |               | Functional features to be controlled |
|       3       | BUSINESS_VALUE |  varchar  |  255   |       0       |          N           |      N      |               |            Service value             |
|       4       |  CONFIG_VALUE  |   text    | 65535  |       0       |          N           |      N      |               |         Configuration value          |
|       5       |  DESCRIPTION   |  varchar  |  255   |       0       |          Y           |      N      |               |      Configuration description       |
|       6       |       ID       |    int    |   10   |       0       |          N           |      Y      |               |            Primary key ID            |

**Table name:** T_CATEGORY

Category information table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |      ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       | CATEGORY_CODE |  varchar  |   32   |       0       |          N           |      N      |                   |   Category code    |
|       3       | CATEGORY_NAME |  varchar  |   32   |       0       |          N           |      N      |                   |   Category name    |
|       4       |   ICON_URL    |  varchar  |  256   |       0       |          Y           |      N      |                   | Category icon link |
|       5       |     TYPE      |  tinyint  |   4    |       0       |          N           |      N      |         0         |        type        |
|       6       |    CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       7       |   MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |      modifier      |
|       8       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       9       |  UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_CLASSIFY

**Pipeline** atomic classification information table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |           description           |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------------: |
|       1       |      ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |         Primary key ID          |
|       2       | CLASSIFY_CODE |  varchar  |   32   |       0       |          N           |      N      |                   |     Owning image class code     |
|       3       | CLASSIFY_NAME |  varchar  |   32   |       0       |          N           |      N      |                   | Name of the owning mirror class |
|       4       |    WEIGHT     |    int    |   10   |       0       |          Y           |      N      |                   |             weight              |
|       5       |    CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |             founder             |
|       6       |   MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |            modifier             |
|       7       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |          Creation time          |
|       8       |  UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |           Update time           |
|       9       |     TYPE      |  tinyint  |   4    |       0       |          N           |      N      |         0         |              type               |

**Table name:** T_CONTAINER

**Description:** Pipeline builds container table (here container and Docker are not the same concept, but an element of pipeline model)

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |                        Primary key ID                        |
|       2       |        NAME         |  varchar  |   45   |       0       |          N           |      N      |                   |                             name                             |
|       3       |        TYPE         |  varchar  |   20   |       0       |          N           |      N      |                   |                             type                             |
|       4       |         OS          |  varchar  |   15   |       0       |          N           |      N      |                   |                       Operating system                       |
|       5       |      REQUIRED       |  tinyint  |   4    |       0       |          N           |      N      |         0         |                   Whether it is necessary                    |
|       6       |  MAX_QUEUE_MINUTES  |    int    |   10   |       0       |          Y           |      N      |        60         |                     Maximum queuing time                     |
|       7       | MAX_RUNNING_MINUTES |    int    |   10   |       0       |          Y           |      N      |        600        |                     Maximum running time                     |
|       8       |        PROPS        |   text    | 65535  |       0       |          Y           |      N      |                   | Customize the JSON string of the extension container's front end form property fields |
|       9       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|      10       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |                           modifier                           |
|      11       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      12       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_CONTAINER_RESOURCE_REL

**Pipeline** container and build resource association table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       | CONTAINER_ID |  varchar  |   32   |       0       |          N           |      N      |                   | Build container ID |
|       3       | RESOURCE_ID  |  varchar  |   32   |       0       |          N           |      N      |                   |    Resource ID     |
|       4       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       5       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |      modifier      |
|       6       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       7       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_IMAGE

**Note:** Mirror information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |     IMAGE_NAME      |  varchar  |   64   |       0       |          N           |      N      |                   |                          Image name                          |
|       3       |     IMAGE_CODE      |  varchar  |   64   |       0       |          N           |      N      |                   |                         Mirror code                          |
|       4       |     CLASSIFY_ID     |  varchar  |   32   |       0       |          N           |      N      |                   |                         Category ID                          |
|       5       |       VERSION       |  varchar  |   20   |       0       |          N           |      N      |                   |                        Version number                        |
|       6       |  IMAGE_SOURCE_TYPE  |  varchar  |   20   |       0       |          N           |      N      |     bkdevops      | Mirror source, bkdevops: BKCI source third: third party source |
|       7       |   IMAGE_REPO_URL    |  varchar  |  256   |       0       |          Y           |      N      |                   |                   Mirror warehouse address                   |
|       8       |   IMAGE_REPO_NAME   |  varchar  |  256   |       0       |          N           |      N      |                   |                   Mirror in warehouse name                   |
|       9       |      TICKET_ID      |  varchar  |  256   |       0       |          Y           |      N      |                   |                          ticket ID                           |
|      10       |    IMAGE_STATUS     |  tinyint  |   4    |       0       |          N           |      N      |                   |               Mirror status: 0: initialization               |
|      11       |  IMAGE_STATUS_MSG   |  varchar  |  1024  |       0       |          Y           |      N      |                   | Description corresponding to the status, such as the reason for the shelving failure |
|      12       |     IMAGE_SIZE      |  varchar  |   20   |       0       |          N           |      N      |                   |                         Mirror size                          |
|      13       |      IMAGE_TAG      |  varchar  |  256   |       0       |          Y           |      N      |                   |                          Mirror tag                          |
|      14       |      LOGO_URL       |  varchar  |  256   |       0       |          Y           |      N      |                   |                         logo address                         |
|      15       |        ICON         |   text    | 65535  |       0       |          Y           |      N      |                   |                  Image icon (BASE64 string)                  |
|      16       |       SUMMARY       |  varchar  |  256   |       0       |          Y           |      N      |                   |                     Mirror introduction                      |
|      17       |     DESCRIPTION     |   text    | 65535  |       0       |          Y           |      N      |                   |                      Image description                       |
|      18       |      PUBLISHER      |  varchar  |   50   |       0       |          N           |      N      |      system       |                       Mirror publisher                       |
|      19       |      PUB_TIME       | datetime  |   19   |       0       |          Y           |      N      |                   |                         Release time                         |
|      20       |     LATEST_FLAG     |    bit    |   1    |       0       |          N           |      N      |                   | The value is the latest version. TRUE: the latest version. FALSE: the version is not the latest version |
|      21       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|      22       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|      23       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      24       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|      25       |  AGENT_TYPE_SCOPE   |  varchar  |   64   |       0       |          N           |      N      |        []         |             Supported build machine environment              |
|      26       |     DELETE_FLAG     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |          Delete the true: yes, false: no identifier          |
|      27       |  DOCKER_FILE_TYPE   |  varchar  |   32   |       0       |          N           |      N      |       INPUT       |     dockerFile type (INPUT: manual input, *_LINK: link)      |
|      28       | DOCKER_FILE_CONTENT |   text    | 65535  |       0       |          Y           |      N      |                   |                     dockerFile contents                      |

**Table name:** T_IMAGE_AGENT_TYPE

Mirror and machine type associated table

**Data column:**

| Serial number |    name    | Data type | length | Decimal place | Allowable null value | Primary key | Default value |                         description                          |
| :-----------: | :--------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :-----------: | :----------------------------------------------------------: |
|       1       |     ID     |  varchar  |   32   |       0       |          N           |      Y      |               |                         Primary key                          |
|       2       | IMAGE_CODE |  varchar  |   64   |       0       |          N           |      N      |               |                         Mirror code                          |
|       3       | AGENT_TYPE |  varchar  |   32   |       0       |          N           |      N      |               | The machine type is PUBLIC_DEVNET, PUBLIC_IDC, PUBLIC_DEVCLOUD |

**Table name:** T_IMAGE_CATEGORY_REL

Mirror and category correlation table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |    Primary key     |
|       2       | CATEGORY_ID |  varchar  |   32   |       0       |          N           |      N      |                   | Mirror category ID |
|       3       |  IMAGE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |      Image ID      |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |   Recent reviser   |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_IMAGE_FEATURE

**Note:** Mirror feature table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                     description                      |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------------------------------: |
|       1       |         ID         |  varchar  |   32   |       0       |          N           |      Y      |                   |                     Primary key                      |
|       2       |     IMAGE_CODE     |  varchar  |  256   |       0       |          N           |      N      |                   |                     Mirror code                      |
|       3       |    PUBLIC_FLAG     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |  Whether it is a public mirror. TRUE: yes FALSE: no  |
|       4       |   RECOMMEND_FLAG   |    bit    |   1    |       0       |          Y           |      N      |       B '1'       |                 TRUE: yes FALSE: No                  |
|       5       |      CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |                       founder                        |
|       6       |      MODIFIER      |  varchar  |   50   |       0       |          N           |      N      |      system       |                    Recent reviser                    |
|       7       |    CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                    Creation time                     |
|       8       |    UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                     Update time                      |
|       9       | CERTIFICATION_FLAG |    bit    |   1    |       0       |          Y           |      N      |       B '0'       | Official authentication or not: TRUE: yes FALSE: no  |
|      10       |       WEIGHT       |    int    |   10   |       0       |          Y           |      N      |                   | Weight (the larger the value, the higher the weight) |
|      11       |     IMAGE_TYPE     |  tinyint  |   4    |       0       |          N           |      N      |         1         | Mirror type: 0: BK official, 1: third party  |
|      12       |    DELETE_FLAG     |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |      Delete the true: yes, false: no identifier      |

**Table name:** T_IMAGE_LABEL_REL

Mirror and label association table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |   description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |   Primary key   |
|       2       |  LABEL_ID   |  varchar  |   32   |       0       |          N           |      N      |                   | Template tag ID |
|       3       |  IMAGE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |    Image ID     |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |     founder     |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       | Recent reviser  |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Creation time  |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Update time   |

**Table name:** T_IMAGE_VERSION_LOG

**Note:** Mirror the version log table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |   IMAGE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |                           Image ID                           |
|       3       | RELEASE_TYPE |  tinyint  |   4    |       0       |          N           |      N      |                   | Release type: 0: new on the shelf 1: incompatible upgrade 2: compatibility feature update 3: compatibility problem correction |
|       4       |   CONTENT    |   text    | 65535  |       0       |          N           |      N      |                   |                     Version log content                      |
|       5       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       6       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|       7       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|       8       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_LABEL

Atomic label information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |   description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID  |
|       2       | LABEL_CODE  |  varchar  |   32   |       0       |          N           |      N      |                   | Mirror tag code |
|       3       | LABEL_NAME  |  varchar  |   32   |       0       |          N           |      N      |                   |   Label name    |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |     founder     |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier     |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Creation time  |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Update time   |
|       8       |    TYPE     |  tinyint  |   4    |       0       |          N           |      N      |         0         |      type       |

**Table name:** T_LOGO

**Description:** Store logo information sheet

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :---------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |  Primary key ID   |
|       2       |    TYPE     |  varchar  |   16   |       0       |          N           |      N      |                   |       type        |
|       3       |  LOGO_URL   |  varchar  |  512   |       0       |          N           |      N      |                   |  LOGOURL address  |
|       4       |    LINK     |  varchar  |  512   |       0       |          Y           |      N      |                   |     Jump link     |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder      |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |     modifier      |
|       7       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time   |
|       8       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Modification time |
|       9       |    ORDER    |    int    |   10   |       0       |          N           |      N      |         0         | Display sequence  |

**Table name:** T_REASON

**Description:** Cause definition table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |   description    |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |   Primary key    |
|       2       |    TYPE     |  varchar  |   32   |       0       |          N           |      N      |                   |       type       |
|       3       |   CONTENT   |  varchar  |  512   |       0       |          N           |      N      |                   |   Log content    |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |     founder      |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |  Recent reviser  |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Creation time   |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Update time    |
|       8       |   ENABLE    |    bit    |   1    |       0       |          N           |      N      |       B '1'       |  Enable or not   |
|       9       |    ORDER    |    int    |   10   |       0       |          N           |      N      |         0         | Display sequence |

**Table name:** T_REASON_REL

**Description:** Cause and component association relationship

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |      Primary key       |
|       2       |    TYPE     |  varchar  |   32   |       0       |          N           |      N      |                   |          type          |
|       3       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       4       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |
|       5       |  REASON_ID  |  varchar  |   32   |       0       |          N           |      N      |                   |        Cause ID        |
|       6       |    NOTE     |   text    | 65535  |       0       |          Y           |      N      |                   |  Explanation of cause  |
|       7       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|       8       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |

**Table name:** T_STORE_APPROVE

**Description:** Audit form

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       3       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |
|       4       |   CONTENT   |   text    | 65535  |       0       |          N           |      N      |                   |      Log content       |
|       5       |  APPLICANT  |  varchar  |   50   |       0       |          N           |      N      |                   |       applicant        |
|       6       |    TYPE     |  varchar  |   64   |       0       |          Y           |      N      |                   |          type          |
|       7       |   STATUS    |  varchar  |   64   |       0       |          Y           |      N      |                   |         state          |
|       8       |  APPROVER   |  varchar  |   50   |       0       |          Y           |      N      |                   |        approver        |
|       9       | APPROVE_MSG |  varchar  |  256   |       0       |          Y           |      N      |                   |  Approval information  |
|      10       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|      11       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |     Recent reviser     |
|      12       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |
|      13       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time       |

**Table name:** T_STORE_BUILD_APP_REL

store build and compile environment association table

**Data column:**

| Serial number |      name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |       ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       | BUILD_INFO_ID  |  varchar  |   32   |       0       |          N           |      N      |                   | Build information Id(corresponding to T_STORE_BUILD_INFO primary key) |
|       3       | APP_VERSION_ID |    int    |   10   |       0       |          Y           |      N      |                   | Build environment version Id(corresponding to T_APP_VERSION primary key) |
|       4       |    CREATOR     |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       5       |    MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|       6       |  CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|       7       |  UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_STORE_BUILD_INFO

store component build information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |      LANGUAGE       |  varchar  |   64   |       0       |          Y           |      N      |                   |                     Development language                     |
|       3       |       SCRIPT        |   text    | 65535  |       0       |          N           |      N      |                   |                        Package script                        |
|       4       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       5       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|       6       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|       7       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|       8       |   REPOSITORY_PATH   |  varchar  |  500   |       0       |          Y           |      N      |                   |                      Code storage path                       |
|       9       |       ENABLE        |    bit    |   1    |       0       |          N           |      N      |       B '1'       |             Enable or disable 1 Enable 0 Disable             |
|      10       | SAMPLE_PROJECT_PATH |  varchar  |  500   |       0       |          N           |      N      |                   |                     Sample project path                      |
|      11       |     STORE_TYPE      |  tinyint  |   4    |       0       |          N           |      N      |         0         | store component type 0: plug-in 1: template 2: image 3: IDE plug-in 4: micro extension |

**Table name:** T_STORE_COMMENT

store component review information table

**Data column:**

| Serial number |      name       | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |             description              |
| :-----------: | :-------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------: |
|       1       |       ID        |  varchar  |   32   |       0       |          N           |      Y      |                   |            Primary key ID            |
|       2       |    STORE_ID     |  varchar  |   32   |       0       |          N           |      N      |                   |          Store component ID          |
|       3       |   STORE_CODE    |  varchar  |   64   |       0       |          N           |      N      |                   |        store component coding        |
|       4       | COMMENT_CONTENT |   text    | 65535  |       0       |          N           |      N      |                   |           Comment content            |
|       5       | COMMENTER_DEPT  |  varchar  |  200   |       0       |          N           |      N      |                   | Commenter organizational information |
|       6       |      SCORE      |    int    |   10   |       0       |          N           |      N      |                   |                score                 |
|       7       |  PRAISE_COUNT   |    int    |   10   |       0       |          Y           |      N      |         0         |           Number of likes            |
|       8       |   PROFILE_URL   |  varchar  |  256   |       0       |          Y           |      N      |                   |  The url of the commenter's avatar   |
|       9       |   STORE_TYPE    |  tinyint  |   4    |       0       |          N           |      N      |         0         |         store component type         |
|      10       |     CREATOR     |  varchar  |   50   |       0       |          N           |      N      |      system       |               founder                |
|      11       |    MODIFIER     |  varchar  |   50   |       0       |          N           |      N      |      system       |               modifier               |
|      12       |   CREATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |            Creation time             |
|      13       |   UPDATE_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |             Update time              |

**Table name:** T_STORE_COMMENT_PRAISE

store component comment like information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       | COMMENT_ID  |  varchar  |   32   |       0       |          N           |      N      |                   |   Comment ID   |
|       3       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |    founder     |
|       4       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier    |
|       5       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |
|       6       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time   |

**Table name:** T_STORE_COMMENT_REPLY

store component review reply information table

**Data column:**

| Serial number |     name      | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                  description                   |
| :-----------: | :-----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------------------------------: |
|       1       |      ID       |  varchar  |   32   |       0       |          N           |      Y      |                   |                 Primary key ID                 |
|       2       |  COMMENT_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |                   Comment ID                   |
|       3       | REPLY_CONTENT |   text    | 65535  |       0       |          Y           |      N      |                   |                 Reply content                  |
|       4       |  PROFILE_URL  |  varchar  |  256   |       0       |          Y           |      N      |                   |       The url of the commenter's avatar        |
|       5       | REPLY_TO_USER |  varchar  |   50   |       0       |          Y           |      N      |                   |                   responder                    |
|       6       | REPLYER_DEPT  |  varchar  |  200   |       0       |          N           |      N      |                   | Responder organizational structure information |
|       7       |    CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |                    founder                     |
|       8       |   MODIFIER    |  varchar  |   50   |       0       |          N           |      N      |      system       |                    modifier                    |
|       9       |  CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                 Creation time                  |
|      10       |  UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                  Update time                   |

**Table name:** T_STORE_DEPT_REL

**Description:** Store components and associations with institutions table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |                        Primary key ID                        |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   |                    store component coding                    |
|       3       |   DEPT_ID   |    int    |   10   |       0       |          N           |      N      |                   |     The project belongs to the secondary organization ID     |
|       4       |  DEPT_NAME  |  varchar  |  1024  |       0       |          N           |      N      |                   | Name of the secondary organization to which the project belongs |
|       5       |   STATUS    |  tinyint  |   4    |       0       |          N           |      N      |         0         |                            state                             |
|       6       |   COMMENT   |  varchar  |  256   |       0       |          Y           |      N      |                   |                           comment                            |
|       7       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       8       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                           modifier                           |
|       9       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      10       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|      11       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |                     store component type                     |

**Table name:** T_STORE_ENV_VAR

Environment variable information table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |  STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   |                       Component coding                       |
|       3       |  STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         | Component type 0: Plug-in 1: template 2: image 3: IDE plug-in 4: Micro extension |
|       4       |   VAR_NAME   |  varchar  |   64   |       0       |          N           |      N      |                   |                        Variable name                         |
|       5       |  VAR_VALUE   |   text    | 65535  |       0       |          N           |      N      |                   |                        Variable value                        |
|       6       |   VAR_DESC   |   text    | 65535  |       0       |          Y           |      N      |                   |                         description                          |
|       7       |    SCOPE     |  varchar  |   16   |       0       |          N           |      N      |                   |       Validity range TEST: test PRD: official ALL: All       |
|       8       | ENCRYPT_FLAG |    bit    |   1    |       0       |          Y           |      N      |       B '0'       |           Whether to encrypt. TRUE: yes FALSE: no            |
|       9       |   VERSION    |    int    |   10   |       0       |          N           |      N      |         1         |                        Version number                        |
|      10       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|      11       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|      12       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      13       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_STORE_MEDIA_INFO

Media information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :----------------------------------------------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                      |                         Primary key                          |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                      |                store component identification                |
|       3       |  MEDIA_URL  |  varchar  |  256   |       0       |          N           |      N      |                      |                     Media resource link                      |
|       4       | MEDIA_TYPE  |  varchar  |   32   |       0       |          N           |      N      |                      |      Media resource type PICTURE: picture VIDEO: video       |
|       5       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |          0           | store component type 0: plug-in 1: template 2: image 3: IDE plug-in 4: micro extension |
|       6       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |        system        |                           founder                            |
|       7       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |        system        |                        Recent reviser                        |
|       8       | CREATE_TIME | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |                        Creation time                         |
|       9       | UPDATE_TIME | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |                         Update time                          |

**Table name:** T_STORE_MEMBER

store component information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       3       |  USERNAME   |  varchar  |   64   |       0       |          N           |      N      |                   |       User name        |
|       4       |    TYPE     |  tinyint  |   4    |       0       |          N           |      N      |                   |          type          |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |        modifier        |
|       7       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |
|       8       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time       |
|       9       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |

**Table name:** T_STORE_OPT_LOG

store operation log table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       3       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |
|       4       |  OPT_TYPE   |  varchar  |   64   |       0       |          N           |      N      |                   |   Type of operation    |
|       5       |  OPT_DESC   |  varchar  |  512   |       0       |          N           |      N      |                   |   Operation content    |
|       6       |  OPT_USER   |  varchar  |   64   |       0       |          N           |      N      |                   |     Operating user     |
|       7       |  OPT_TIME   | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Operating time     |
|       8       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|       9       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |

**Table name:** T_STORE_PIPELINE_BUILD_REL

**Note:** The store component builds the association table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |    Primary key     |
|       2       |  STORE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   | Store component ID |
|       3       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |                   |    Pipeline ID     |
|       4       |  BUILD_ID   |  varchar  |   34   |       0       |          N           |      N      |                   |      Build ID      |
|       5       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       6       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |   Recent reviser   |
|       7       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       8       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_STORE_PIPELINE_REL

Store components and pipeline-associated relationship table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   |                    Store component coding                    |
|       3       | PIPELINE_ID |  varchar  |   34   |       0       |          N           |      N      |                   |                         Pipeline ID                          |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |                           founder                            |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |
|       8       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         | Store component type 0: Plug-in 1: Template 2: Image 3: IDE plug-in |

**Table name:** T_STORE_PROJECT_REL

**Description:** The store component is associated with the item relational table

**Data column:**

| Serial number |     name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                 description                 |
| :-----------: | :----------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------------------------: |
|       1       |      ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |               Primary key ID                |
|       2       |  STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   |           store component coding            |
|       3       | PROJECT_CODE |  varchar  |   32   |       0       |          N           |      N      |                   | The project to which the user group belongs |
|       4       |     TYPE     |  tinyint  |   4    |       0       |          N           |      N      |                   |                    type                     |
|       5       |   CREATOR    |  varchar  |   50   |       0       |          N           |      N      |      system       |                   founder                   |
|       6       |   MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |                  modifier                   |
|       7       | CREATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                Creation time                |
|       8       | UPDATE_TIME  | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                 Update time                 |
|       9       |  STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |            store component type             |

**Table name:** T_STORE_RELEASE

**Note:** The store component publishes the upgrade information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |                         description                          |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------------------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |                         Primary key                          |
|       2       |     STORE_CODE      |  varchar  |   64   |       0       |          N           |      N      |                   |                     store component code                     |
|       3       |  FIRST_PUB_CREATOR  |  varchar  |   64   |       0       |          N           |      N      |                   |                       First publisher                        |
|       4       |   FIRST_PUB_TIME    | datetime  |   19   |       0       |          N           |      N      |                   |                      First release time                      |
|       5       |   LATEST_UPGRADER   |  varchar  |   64   |       0       |          N           |      N      |                   |                      Recently upgraded                       |
|       6       | LATEST_UPGRADE_TIME | datetime  |   19   |       0       |          N           |      N      |                   |                      Last upgrade time                       |
|       7       |     STORE_TYPE      |  tinyint  |   4    |       0       |          N           |      N      |         0         | store component type 0: plug-in 1: template 2: image 3: IDE plug-in |
|       8       |       CREATOR       |  varchar  |   64   |       0       |          N           |      N      |      system       |                           founder                            |
|       9       |      MODIFIER       |  varchar  |   64   |       0       |          N           |      N      |      system       |                        Recent reviser                        |
|      10       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                        Creation time                         |
|      11       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |                         Update time                          |

**Table name:** T_STORE_SENSITIVE_API

Sensitive API interface information table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |       description        |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |      Primary key ID      |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   |  store component coding  |
|       3       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |   store component type   |
|       4       |  API_NAME   |  varchar  |   64   |       0       |          N           |      N      |                   |         API name         |
|       5       | ALIAS_NAME  |  varchar  |   64   |       0       |          N           |      N      |                   |          alias           |
|       6       | API_STATUS  |  varchar  |   64   |       0       |          N           |      N      |                   |        API status        |
|       7       |  API_LEVEL  |  varchar  |   64   |       0       |          N           |      N      |                   |        API level         |
|       8       | APPLY_DESC  |  varchar  |  1024  |       0       |          Y           |      N      |                   | Application instructions |
|       9       | APPROVE_MSG |  varchar  |  1024  |       0       |          Y           |      N      |                   |   Approval information   |
|      10       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |                   |         founder          |
|      11       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |                   |         modifier         |
|      12       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Creation time       |
|      13       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |       Update time        |

**Table name:** T_STORE_SENSITIVE_CONF

**Note:** store private configuration table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       3       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |
|       4       | FIELD_NAME  |  varchar  |   64   |       0       |          N           |      N      |                   |       Field name       |
|       5       | FIELD_VALUE |   text    | 65535  |       0       |          N           |      N      |                   |      Field value       |
|       6       | FIELD_DESC  |   text    | 65535  |       0       |          Y           |      N      |                   |   Field description    |
|       7       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|       8       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |        modifier        |
|       9       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |
|      10       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time       |
|      11       | FIELD_TYPE  |  varchar  |   16   |       0       |          Y           |      N      |      BACKEND      |       Field type       |

**Table name:** T_STORE_STATISTICS

store statistics table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       |  STORE_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |   Store component ID   |
|       3       | STORE_CODE  |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       4       |  DOWNLOADS  |    int    |   10   |       0       |          Y           |      N      |                   |        download        |
|       5       |   COMMITS   |    int    |   10   |       0       |          Y           |      N      |                   |   Number of comments   |
|       6       |    SCORE    |    int    |   10   |       0       |          Y           |      N      |                   |         score          |
|       7       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |        founder         |
|       8       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |        modifier        |
|       9       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |
|      10       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time       |
|      11       | STORE_TYPE  |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |

**Table name:** T_STORE_STATISTICS_DAILY

store daily statistics table

**Data column:**

| Serial number |       name        | Data type | length | Decimal place | Allowable null value | Primary key |    Default value     |                description                 |
| :-----------: | :---------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :------------------: | :----------------------------------------: |
|       1       |        ID         |  varchar  |   32   |       0       |          N           |      Y      |                      |                Primary key                 |
|       2       |    STORE_CODE     |  varchar  |   64   |       0       |          N           |      N      |                      |              Component coding              |
|       3       |    STORE_TYPE     |  tinyint  |   4    |       0       |          N           |      N      |          0           |               Component type               |
|       4       |  TOTAL_DOWNLOADS  |    int    |   10   |       0       |          Y           |      N      |          0           |              Total downloads               |
|       5       |  DAILY_DOWNLOADS  |    int    |   10   |       0       |          Y           |      N      |          0           |              Daily downloads               |
|       6       | DAILY_SUCCESS_NUM |    int    |   10   |       0       |          Y           |      N      |          0           |  Number of successful executions per day   |
|       7       |  DAILY_FAIL_NUM   |    int    |   10   |       0       |          Y           |      N      |          0           | Total number of execution failures per day |
|       8       | DAILY_FAIL_DETAIL |  varchar  |  4096  |       0       |          Y           |      N      |                      |      Daily execution failure details       |
|       9       |  STATISTICS_TIME  | datetime  |   23   |       0       |          N           |      N      |                      |              Statistical time              |
|      10       |    CREATE_TIME    | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |               Creation time                |
|      11       |    UPDATE_TIME    | datetime  |   23   |       0       |          N           |      N      | CURRENT_TIMESTAMP(3) |                Update time                 |

**Table name:** T_STORE_STATISTICS_TOTAL

**Note:** store full statistics table

**Data column:**

| Serial number |        name        | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |      description       |
| :-----------: | :----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :--------------------: |
|       1       |         ID         |  varchar  |   32   |       0       |          N           |      Y      |                   |     Primary key ID     |
|       2       |     STORE_CODE     |  varchar  |   64   |       0       |          N           |      N      |                   | store component coding |
|       3       |     STORE_TYPE     |  tinyint  |   4    |       0       |          N           |      N      |         0         |  store component type  |
|       4       |     DOWNLOADS      |    int    |   10   |       0       |          Y           |      N      |         0         |        download        |
|       5       |      COMMITS       |    int    |   10   |       0       |          Y           |      N      |         0         |   Number of comments   |
|       6       |       SCORE        |    int    |   10   |       0       |          Y           |      N      |         0         |         score          |
|       7       |   SCORE_AVERAGE    |  decimal  |   4    |       1       |          Y           |      N      |        0.0        |  Comment equalization  |
|       8       |    PIPELINE_NUM    |    int    |   10   |       0       |          Y           |      N      |         0         |   Number of pipeline   |
|       9       | RECENT_EXECUTE_NUM |    int    |   10   |       0       |          Y           |      N      |         0         |     Last execution     |
|      10       |    CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |     Creation time      |
|      11       |    UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |      Update time       |

**Table name:** T_TEMPLATE

**Note:** Template information table

**Data column:**

| Serial number |        name         | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |              description              |
| :-----------: | :-----------------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :-----------------------------------: |
|       1       |         ID          |  varchar  |   32   |       0       |          N           |      Y      |                   |            Primary key ID             |
|       2       |    TEMPLATE_NAME    |  varchar  |  200   |       0       |          N           |      N      |                   |             Template name             |
|       3       |    TEMPLATE_CODE    |  varchar  |   32   |       0       |          N           |      N      |                   |             Template code             |
|       4       |     CLASSIFY_ID     |  varchar  |   32   |       0       |          N           |      N      |                   |              Category ID              |
|       5       |       VERSION       |  varchar  |   20   |       0       |          N           |      N      |                   |            Version number             |
|       6       |    TEMPLATE_TYPE    |  tinyint  |   4    |       0       |          N           |      N      |         1         |             Template type             |
|       7       |  TEMPLATE_RD_TYPE   |  tinyint  |   4    |       0       |          N           |      N      |         1         |       Template development type       |
|       8       |   TEMPLATE_STATUS   |  tinyint  |   4    |       0       |          N           |      N      |                   |            Template state             |
|       9       | TEMPLATE_STATUS_MSG |  varchar  |  1024  |       0       |          Y           |      N      |                   |      Template status information      |
|      10       |      LOGO_URL       |  varchar  |  256   |       0       |          Y           |      N      |                   |            LOGOURL address            |
|      11       |       SUMMARY       |  varchar  |  256   |       0       |          Y           |      N      |                   |             introduction              |
|      12       |     DESCRIPTION     |   text    | 65535  |       0       |          Y           |      N      |                   |              description              |
|      13       |      PUBLISHER      |  varchar  |   50   |       0       |          N           |      N      |      system       |           Atomic publisher            |
|      14       |   PUB_DESCRIPTION   |   text    | 65535  |       0       |          Y           |      N      |                   |          Release description          |
|      15       |     PUBLIC_FLAG     |    bit    |   1    |       0       |          N           |      N      |       B '0'       |     Whether it is a public mirror     |
|      16       |     LATEST_FLAG     |    bit    |   1    |       0       |          N           |      N      |                   | Whether it is the latest version atom |
|      17       |       CREATOR       |  varchar  |   50   |       0       |          N           |      N      |      system       |                founder                |
|      18       |      MODIFIER       |  varchar  |   50   |       0       |          N           |      N      |      system       |               modifier                |
|      19       |     CREATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |             Creation time             |
|      20       |     UPDATE_TIME     | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |              Update time              |
|      21       |      PUB_TIME       | datetime  |   19   |       0       |          Y           |      N      |                   |             Release time              |

**Table name:** T_TEMPLATE_CATEGORY_REL

Template and category correlation table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |    description     |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :----------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   |   Primary key ID   |
|       2       | CATEGORY_ID |  varchar  |   32   |       0       |          N           |      N      |                   | Mirror category ID |
|       3       | TEMPLATE_ID |  varchar  |   32   |       0       |          N           |      N      |                   |    Template ID     |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |      founder       |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |      modifier      |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |   Creation time    |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |    Update time     |

**Table name:** T_TEMPLATE_LABEL_REL

Template and label association table

**Data column:**

| Serial number |    name     | Data type | length | Decimal place | Allowable null value | Primary key |   Default value   |  description   |
| :-----------: | :---------: | :-------: | :----: | :-----------: | :------------------: | :---------: | :---------------: | :------------: |
|       1       |     ID      |  varchar  |   32   |       0       |          N           |      Y      |                   | Primary key ID |
|       2       |  LABEL_ID   |  varchar  |   32   |       0       |          N           |      N      |                   |     Tag ID     |
|       3       | TEMPLATE_ID |  varchar  |   32   |       0       |          N           |      N      |                   |  Template ID   |
|       4       |   CREATOR   |  varchar  |   50   |       0       |          N           |      N      |      system       |    founder     |
|       5       |  MODIFIER   |  varchar  |   50   |       0       |          N           |      N      |      system       |    modifier    |
|       6       | CREATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP | Creation time  |
|       7       | UPDATE_TIME | datetime  |   19   |       0       |          N           |      N      | CURRENT_TIMESTAMP |  Update time   |
