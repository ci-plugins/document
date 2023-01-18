# Get environment information by hashId(multiple) (no permissions checked)

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/environment/projects/{projectId}/envs/listRawByEnvHashIds

### Resource description

#### Get environment information by hashId(multiple) (no permissions checked)

### Input parameter description

#### Body parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| body           | array          | is   | Environment hashId(s) |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data return wrapper model List Environment Information (permissions) |

#### Request sample

```
curl -X POST '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : [ {  "updatedTime" : 0,  "canEdit" : true,  "envVars" : [ {  "name" : "String",  "secure" : true,  "value" : "String"  } ],  "updatedUser" : "String",  "canUse" : true,  "envType" : "String",  "name" : "String",  "createdTime" : 0,  "nodeCount" : 0,  "canDelete" : true,  "envHashId" : "String",  "createdUser" : "String",  "desc" : "String"  } ],  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model List Environment Information (permissions)

| Parameter name | Parameter type                               | must | Parameter description |
| :------------- | :------------------------------------------- | :--- | :-------------------- |
| data           | List< Environment Information (permissions)> | no   | data                  |
| message        | string                                       | no   | Error message         |
| status         | integer                                      | is   | Status code           |

## Environmental information (permission)

| Parameter name | Parameter type               | must | Parameter description                           |
| :------------- | :--------------------------- | :--- | :---------------------------------------------- |
| updatedTime    | integer                      | is   | Update time                                     |
| canEdit        | boolean                      | no   | Whether it can be edited                        |
| envVars        | List< environment variable > | is   | Environment variable                            |
| updatedUser    | string                       | is   | updater                                         |
| canUse         | boolean                      | no   | Whether it can be used                          |
| envType        | string                       | is   | Environment type (development environment {DEV} |
| name           | string                       | is   | Environment name                                |
| createdTime    | integer                      | is   | Creation time                                   |
| nodeCount      | integer                      | no   | Number of nodes                                 |
| canDelete      | boolean                      | no   | Whether it can be deleted                       |
| envHashId      | string                       | is   | Environmental HashId                            |
| createdUser    | string                       | is   | founder                                         |
| desc           | string                       | is   | Environment description                         |

## Environment variable

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | is   | Variable name         |
| secure         | boolean        | is   | Safe or not           |
| value          | string         | is   | Variable value        |
