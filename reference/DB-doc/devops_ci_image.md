# devops_ci_image

**Database name:** devops_ci_image

**Issue:** 1.0.0

**Documentation:** Database documentation for devops_ci_image

|               Table name                | description |
| :-------------------------------------: | :---------: |
| [T_UPLOAD_IMAGE_TASK](broken-reference) |             |

**Table name:** T_UPLOAD_IMAGE_TASK

**Explanation:**

**Data column:**

| Serial number |     name     | Data type |   length   | Decimal place | Allowable null value | Primary key | Default value |    description    |
| :-----------: | :----------: | :-------: | :--------: | :-----------: | :------------------: | :---------: | :-----------: | :---------------: |
|       1       |   TASK_ID    |  varchar  |    128     |       0       |          N           |      Y      |               |      Task ID      |
|       2       |  PROJECT_ID  |  varchar  |    128     |       0       |          N           |      N      |               |      Item ID      |
|       3       |   OPERATOR   |  varchar  |    128     |       0       |          N           |      N      |               |     operator      |
|       4       | CREATED_TIME | timestamp |     19     |       0       |          Y           |      N      |               |   Creation time   |
|       5       | UPDATED_TIME | timestamp |     19     |       0       |          Y           |      N      |               | Modification time |
|       6       | TASK_STATUS  |  varchar  |     32     |       0       |          N           |      N      |               |    Task status    |
|       7       | TASK_MESSAGE |  varchar  |    256     |       0       |          Y           |      N      |               |   Task message    |
|       8       |  IMAGE_DATA  | longtext  | 2147483647 |       0       |          Y           |      N      |               |    Mirror list    |

|      |      |      |      |      |      |      |      |      |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
|      |      |      |      |      |      |      |      |      |
