# Gets a list of environments that the user has permission to use

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/environment/projects/{projectId}/envs/listUsableServerEnvs

### Resource description

#### Gets a list of environments that the user has permission to use

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | yes  | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data return wrapper model List Environment Information (permissions) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]' 
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
| status         | integer                                      | yes  | Status code           |

## Environmental information (permission)

| Parameter name | Parameter type               | must | Parameter description                           |
| :------------- | :--------------------------- | :--- | :---------------------------------------------- |
| updatedTime    | integer                      | yes  | Update time                                     |
| canEdit        | boolean                      | no   | Whether it can be edited                        |
| envVars        | List< environment variable > | yes  | Environment variable                            |
| updatedUser    | string                       | yes  | updater                                         |
| canUse         | boolean                      | no   | Whether it can be used                          |
| envType        | string                       | yes  | Environment type (development environment {DEV} |
| name           | string                       | yes  | Environment name                                |
| createdTime    | integer                      | yes  | Creation time                                   |
| nodeCount      | integer                      | no   | Number of nodes                                 |
| canDelete      | boolean                      | no   | Whether it can be deleted                       |
| envHashId      | string                       | yes  | Environmental HashId                            |
| createdUser    | string                       | yes  | founder                                         |
| desc           | string                       | yes  | Environment description                         |

## Environment variable

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | yes  | Variable name         |
| secure         | boolean        | yes  | Safe or not           |
| value          | string         | yes  | Variable value        |
