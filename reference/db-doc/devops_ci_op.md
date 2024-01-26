# devops\_ci\_op

**数据库名：** devops\_ci\_op

**文档版本：** 1.0.1

**文档描述：** devops\_ci\_op的数据库文档

|                                      表名                                      |  说明 |
| :--------------------------------------------------------------------------: | :-: |
|                  [dept\_info](devops\_ci\_op.md#dept\_info)                  |     |
|               [project\_info](devops\_ci\_op.md#project\_info)               |     |
|                        [role](devops\_ci\_op.md#role)                        |     |
|            [role\_permission](devops\_ci\_op.md#role\_permission)            |     |
|             [schema\_version](devops\_ci\_op.md#schema\_version)             |     |
|             [spring\_session](devops\_ci\_op.md#spring\_session)             |     |
| [SPRING\_SESSION\_ATTRIBUTES](devops\_ci\_op.md#SPRING\_SESSION\_ATTRIBUTES) |     |
|              [t\_user\_token](devops\_ci\_op.md#t\_user\_token)              |     |
|                 [url\_action](devops\_ci\_op.md#url\_action)                 |     |
|                        [user](devops\_ci\_op.md#user)                        |     |
|            [user\_permission](devops\_ci\_op.md#user\_permission)            |     |
|                  [user\_role](devops\_ci\_op.md#user\_role)                  |     |

**表名：** dept\_info

**说明：**

**数据列：**

|  序号 |        名称        |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |               说明               |
| :-: | :--------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------------------------: |
|  1  |        id        |    int   |  10 |  0  |   N  |  Y  |     |            ä¸»é”®ID            |
|  2  |   create\_time   | datetime |  19 |  0  |   Y  |  N  |     |          åˆ›å»ºæ—¶é—´          |
|  3  |     dept\_id     |    int   |  10 |  0  |   N  |  N  |     |   é¡¹ç›®æ‰€å±žäºŒçº§æœºæž„ID   |
|  4  |    dept\_name    |  varchar | 100 |  0  |   N  |  N  |     | é¡¹ç›®æ‰€å±žäºŒçº§æœºæž„åç§° |
|  5  |       level      |    int   |  10 |  0  |   N  |  N  |     |            å±‚çº§ID            |
|  6  | parent\_dept\_id |    int   |  10 |  0  |   Y  |  N  |     |                                |
|  7  |   UPDATE\_TIME   | datetime |  19 |  0  |   Y  |  N  |     |          æ›´æ–°æ—¶é—´          |

**表名：** project\_info

**说明：**

**数据列：**

|  序号 |           名称          |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |                    说明                   |
| :-: | :-------------------: | :------: | :-: | :-: | :--: | :-: | :-: | :-------------------------------------: |
|  1  |           id          |    int   |  10 |  0  |   N  |  Y  |     |                 ä¸»é”®ID                |
|  2  |    approval\_status   |    int   |  10 |  0  |   Y  |  N  |     |               å®¡æ ¸çŠ¶æ€              |
|  3  |     approval\_time    | datetime |  19 |  0  |   Y  |  N  |     |               æ‰¹å‡†æ—¶é—´              |
|  4  |        approver       |  varchar | 100 |  0  |   Y  |  N  |     |                æ‰¹å‡†äºº                |
|  5  |      cc\_app\_id      |    int   |  10 |  0  |   Y  |  N  |     |                 åº”ç”¨ID                |
|  6  |      created\_at      | datetime |  19 |  0  |   Y  |  N  |     |               åˆ›å»ºæ—¶é—´              |
|  7  |        creator        |  varchar | 100 |  0  |   Y  |  N  |     |                åˆ›å»ºè€…                |
|  8  |   creator\_bg\_name   |  varchar | 100 |  0  |   Y  |  N  |     |         åˆ›å»ºè€…äº‹ä¸šç¾¤åç§°        |
|  9  | creator\_center\_name |  varchar | 100 |  0  |   Y  |  N  |     |          åˆ›å»ºè€…ä¸­å¿ƒåå­—          |
|  10 |  creator\_dept\_name  |  varchar | 100 |  0  |   Y  |  N  |     | åˆ›å»ºè€…é¡¹ç›®æ‰€å±žäºŒçº§æœºæž„åç§° |
|  11 |     english\_name     |  varchar | 255 |  0  |   Y  |  N  |     |               è‹±æ–‡åç§°              |
|  12 |      is\_offlined     |    bit   |  1  |  0  |   Y  |  N  |     |               æ˜¯å¦åœç”¨              |
|  13 |      is\_secrecy      |    bit   |  1  |  0  |   Y  |  N  |     |               æ˜¯å¦ä¿å¯†              |
|  14 |    project\_bg\_id    |    int   |  10 |  0  |   Y  |  N  |     |               äº‹ä¸šç¾¤ID               |
|  15 |   project\_bg\_name   |  varchar | 100 |  0  |   Y  |  N  |     |             äº‹ä¸šç¾¤åç§°             |
|  16 |  project\_center\_id  |  varchar |  50 |  0  |   Y  |  N  |     |                 ä¸­å¿ƒID                |
|  17 | project\_center\_name |  varchar | 100 |  0  |   Y  |  N  |     |               ä¸­å¿ƒåå­—              |
|  18 |   project\_dept\_id   |    int   |  10 |  0  |   Y  |  N  |     |                 æœºæž„ID                |
|  19 |  project\_dept\_name  |  varchar | 100 |  0  |   Y  |  N  |     |      é¡¹ç›®æ‰€å±žäºŒçº§æœºæž„åç§°     |
|  20 |      project\_id      |  varchar | 100 |  0  |   Y  |  N  |     |                 é¡¹ç›®ID                |
|  21 |     project\_name     |  varchar | 100 |  0  |   Y  |  N  |     |               é¡¹ç›®åç§°              |
|  22 |     project\_type     |    int   |  10 |  0  |   Y  |  N  |     |               é¡¹ç›®ç±»åž‹              |
|  23 |        use\_bk        |    bit   |  1  |  0  |   Y  |  N  |     |             æ˜¯å¦ç”¨è“é²¸             |

**表名：** role

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |      id      |    int   |  10 |  0  |   N  |  Y  |     |   ä¸»é”®ID   |
|  2  |  description |  varchar | 255 |  0  |   Y  |  N  |     |    æè¿°    |
|  3  |     name     |  varchar | 255 |  0  |   N  |  N  |     |    åç§°    |
|  4  |   ch\_name   |  varchar | 255 |  0  |   Y  |  N  |     |   åˆ†æ”¯å  |
|  5  | create\_time | datetime |  19 |  0  |   Y  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  6  | modify\_time | datetime |  19 |  0  |   Y  |  N  |     | ä¿®æ”¹æ—¶é—´ |

**表名：** role\_permission

**说明：**

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |        id       |    int   |  10 |  0  |   N  |  Y  |     |   ä¸»é”®ID   |
|  2  |   expire\_time  | datetime |  19 |  0  |   Y  |  N  |     | è¿‡æœŸæ—¶é—´ |
|  3  |     role\_id    |    int   |  10 |  0  |   Y  |  N  |     |   è§’è‰²ID   |
|  4  | url\_action\_id |    int   |  10 |  0  |   Y  |  N  |     |              |
|  5  |   create\_time  | datetime |  19 |  0  |   Y  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  6  |   modify\_time  | datetime |  19 |  0  |   Y  |  N  |     | ä¿®æ”¹æ—¶é—´ |

**表名：** schema\_version

**说明：**

**数据列：**

|  序号 |        名称       |    数据类型   |  长度  | 小数位 | 允许空值 |  主键 |         默认值        |      说明      |
| :-: | :-------------: | :-------: | :--: | :-: | :--: | :-: | :----------------: | :----------: |
|  1  | installed\_rank |    int    |  10  |  0  |   N  |  Y  |                    |              |
|  2  |     version     |  varchar  |  50  |  0  |   Y  |  N  |                    |   ç‰ˆæœ¬å·  |
|  3  |   description   |  varchar  |  200 |  0  |   N  |  N  |                    |    æè¿°    |
|  4  |       type      |  varchar  |  20  |  0  |   N  |  N  |                    |    ç±»åž‹    |
|  5  |      script     |  varchar  | 1000 |  0  |   N  |  N  |                    | æ‰“åŒ…è„šæœ¬ |
|  6  |     checksum    |    int    |  10  |  0  |   Y  |  N  |                    |   æ ¡éªŒå’Œ  |
|  7  |  installed\_by  |  varchar  |  100 |  0  |   N  |  N  |                    |   å®‰è£…è€…  |
|  8  |  installed\_on  | timestamp |  19  |  0  |   N  |  N  | CURRENT\_TIMESTAMP | å®‰è£…æ—¶é—´ |
|  9  | execution\_time |    int    |  10  |  0  |   N  |  N  |                    | æ‰§è¡Œæ—¶é—´ |
|  10 |     success     |    bit    |   1  |  0  |   N  |  N  |                    | æ˜¯å¦æˆåŠŸ |

**表名：** spring\_session

**说明：**

**数据列：**

|  序号 |            名称           |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :---------------------: | :-----: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |       SESSION\_ID       |   char  |  36 |  0  |   N  |  Y  |     |   SESSIONID  |
|  2  |      CREATION\_TIME     |  bigint |  20 |  0  |   N  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  3  |    LAST\_ACCESS\_TIME   |  bigint |  20 |  0  |   N  |  N  |     |              |
|  4  | MAX\_INACTIVE\_INTERVAL |   int   |  10 |  0  |   N  |  N  |     |              |
|  5  |     PRINCIPAL\_NAME     | varchar | 100 |  0  |   Y  |  N  |     |              |

**表名：** SPRING\_SESSION\_ATTRIBUTES

**说明：**

**数据列：**

|  序号 |        名称        |   数据类型  |   长度  | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :--------------: | :-----: | :---: | :-: | :--: | :-: | :-: | :----------: |
|  1  |    SESSION\_ID   |   char  |   36  |  0  |   N  |  Y  |     |   SESSIONID  |
|  2  |  ATTRIBUTE\_NAME | varchar |  200  |  0  |   N  |  Y  |     | å±žæ€§åç§° |
|  3  | ATTRIBUTE\_BYTES |   blob  | 65535 |  0  |   Y  |  N  |     | å±žæ€§å­—èŠ‚ |

**表名：** t\_user\_token

**说明：**

**数据列：**

|  序号 |             名称            |   数据类型  |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |         说明         |
| :-: | :-----------------------: | :-----: | :-: | :-: | :--: | :-: | :-: | :----------------: |
|  1  |          user\_Id         | varchar | 255 |  0  |   N  |  Y  |     |      ç”¨æˆ·ID      |
|  2  |       access\_Token       | varchar | 255 |  0  |   Y  |  N  |     |     æƒé™Token    |
|  3  |    expire\_Time\_Mills    |  bigint |  20 |  0  |   N  |  N  |     |    è¿‡æœŸæ—¶é—´    |
|  4  | last\_Access\_Time\_Mills |  bigint |  20 |  0  |   N  |  N  |     | æœ€è¿‘é‰´æƒæ—¶é—´ |
|  5  |       refresh\_Token      | varchar | 255 |  0  |   Y  |  N  |     |     åˆ·æ–°token    |
|  6  |         user\_Type        | varchar | 255 |  0  |   Y  |  N  |     |    ç”¨æˆ·ç±»åž‹    |

**表名：** url\_action

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |      id      |    int   |  10 |  0  |   N  |  Y  |     |   ä¸»é”®ID   |
|  2  |    action    |  varchar | 255 |  0  |   N  |  N  |     |    æ“ä½œ    |
|  3  |  description |  varchar | 255 |  0  |   Y  |  N  |     |    æè¿°    |
|  4  |      url     |  varchar | 255 |  0  |   N  |  N  |     |   urlåœ°å€  |
|  5  | create\_time | datetime |  19 |  0  |   Y  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  6  | modify\_time | datetime |  19 |  0  |   Y  |  N  |     | ä¿®æ”¹æ—¶é—´ |

**表名：** user

**说明：**

**数据列：**

|  序号 |         名称        |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |         说明         |
| :-: | :---------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------------: |
|  1  |         id        |    int   |  10 |  0  |   N  |  Y  |     |      ä¸»é”®ID      |
|  2  |       chname      |  varchar | 255 |  0  |   Y  |  N  |     |                    |
|  3  |    create\_time   | datetime |  19 |  0  |   Y  |  N  |     |    åˆ›å»ºæ—¶é—´    |
|  4  |       email       |  varchar | 255 |  0  |   Y  |  N  |     |        email       |
|  5  |        lang       |  varchar | 255 |  0  |   Y  |  N  |     |       è¯­è¨€       |
|  6  | last\_login\_time | datetime |  19 |  0  |   Y  |  N  |     | æœ€è¿‘ç™»å½•æ—¶é—´ |
|  7  |       phone       |  varchar | 255 |  0  |   Y  |  N  |     |       ç”µè¯       |
|  8  |      username     |  varchar | 255 |  0  |   N  |  N  |     |    ç”¨æˆ·åç§°    |

**表名：** user\_permission

**说明：**

**数据列：**

|  序号 |        名称       |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :-------------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |        id       |    int   |  10 |  0  |   N  |  Y  |     |   ä¸»é”®ID   |
|  2  |   expire\_time  | datetime |  19 |  0  |   Y  |  N  |     | è¿‡æœŸæ—¶é—´ |
|  3  | url\_action\_id |    int   |  10 |  0  |   Y  |  N  |     |              |
|  4  |     user\_id    |    int   |  10 |  0  |   Y  |  N  |     |   ç”¨æˆ·ID   |
|  5  |   create\_time  | datetime |  19 |  0  |   Y  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  6  |   modify\_time  | datetime |  19 |  0  |   Y  |  N  |     | ä¿®æ”¹æ—¶é—´ |

**表名：** user\_role

**说明：**

**数据列：**

|  序号 |      名称      |   数据类型   |  长度 | 小数位 | 允许空值 |  主键 | 默认值 |      说明      |
| :-: | :----------: | :------: | :-: | :-: | :--: | :-: | :-: | :----------: |
|  1  |      id      |    int   |  10 |  0  |   N  |  Y  |     |   ä¸»é”®ID   |
|  2  |   role\_id   |    int   |  10 |  0  |   Y  |  N  |     |   è§’è‰²ID   |
|  3  |   user\_id   |    int   |  10 |  0  |   Y  |  N  |     |   ç”¨æˆ·ID   |
|  4  | expire\_time | datetime |  19 |  0  |   Y  |  N  |     | è¿‡æœŸæ—¶é—´ |
|  5  | create\_time | datetime |  19 |  0  |   Y  |  N  |     | åˆ›å»ºæ—¶é—´ |
|  6  | modify\_time | datetime |  19 |  0  |   Y  |  N  |     | ä¿®æ”¹æ—¶é—´ |
