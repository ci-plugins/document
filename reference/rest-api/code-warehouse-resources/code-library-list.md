# Code base list

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/repositories/{projectId}/hasPermissionList

### Resource description

#### Code base list

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| repositoryType | string         | no   | Warehouse type        |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Wrapper Model Paging Data wrapper model code base model - basic information](code-library-list.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? repositoryType={repositoryType}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "aliasName" : "String",  "updatedTime" : 0,  "repositoryId" : 0,  "type" : "ENUM",  "repositoryHashId" : "String",  "url" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper Model Paging Data wrapper model code base model - basic information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Paging data wrapper model code base model - Basic information](code-library-list.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging data wrapper model code base model - Basic information

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [Code base model - Basic Information](code-library-list.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Code base model - Basic information

| Parameter name   | Parameter type                                             | must | Parameter description |
| :--------------- | :--------------------------------------------------------- | :--- | :-------------------- |
| aliasName        | string                                                     | is   | Warehouse alias       |
| updatedTime      | integer                                                    | is   | Last update time      |
| repositoryId     | integer                                                    | no   | Warehouse ID          |
| type             | ENUM(CODE_SVN, CODE_GIT, CODE_GITLAB, GITHUB, CODE_TGIT, ) | is   | type                  |
| repositoryHashId | string                                                     | no   | Warehouse hash ID     |
| url              | string                                                     | is   | URL                   |
