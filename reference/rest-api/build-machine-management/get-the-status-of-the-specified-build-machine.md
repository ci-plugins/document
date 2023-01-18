# Gets the state of the specified builder

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/environment/thirdPartAgent/nodes/status

### Resource description

#### Gets the state of the specified builder

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| nodeHashId     | string         | is   | Node hashId           |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                           |
| :-------- | :------------------- | :------------------------------------------------------- |
| 200       | successful operation | Data return wrapper model node Information (permissions) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? nodeHashId={nodeHashId}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "pipelineRefCount" : 0,  "nodeHashId" : "String",  "displayName" : "String",  "ip" : "String",  "canEdit" : true,  "nodeStatus" : "String",  "nodeType" : "String",  "osName" : "String",  "agentStatus" : true,  "operator" : "String",  "canUse" : true,  "bakOperator" : "String",  "lastBuildTime" : "String",  "lastModifyUser" : "String",  "createTime" : "String",  "lastModifyTime" : "String",  "name" : "String",  "bizId" : 0,  "canDelete" : true,  "nodeId" : "String",  "createdUser" : "String",  "gateway" : "String",  "agentHashId" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model node Information (permissions)

| Parameter name | Parameter type                | must | Parameter description |
| :------------- | :---------------------------- | :--- | :-------------------- |
| data           | Node information (permission) | no   | data                  |
| message        | string                        | no   | Error message         |
| status         | integer                       | is   | Status code           |

## Node information (permission)

| Parameter name   | Parameter type | must | Parameter description                                        |
| :--------------- | :------------- | :--- | :----------------------------------------------------------- |
| pipelineRefCount | integer        | no   | Number of pipeline Job references                            |
| nodeHashId       | string         | is   | Environmental HashId                                         |
| displayName      | string         | no   | Display name                                                 |
| ip               | string         | is   | IP                                                           |
| canEdit          | boolean        | no   | Whether it can be edited                                     |
| nodeStatus       | string         | is   | Node state                                                   |
| nodeType         | string         | is   | Node type                                                    |
| osName           | string         | no   | Operating system                                             |
| agentStatus      | boolean        | is   | agent state                                                  |
| operator         | string         | no   | Responsible person                                           |
| canUse           | boolean        | no   | Whether it can be used                                       |
| bakOperator      | string         | no   | Backup owner                                                 |
| lastBuildTime    | string         | no   | Number of pipeline Job references                            |
| lastModifyUser   | string         | no   | Last modifier                                                |
| createTime       | string         | no   | Creation/import time                                         |
| lastModifyTime   | string         | no   | Last revision time                                           |
| name             | string         | is   | Node name                                                    |
| bizId            | integer        | no   | Owning service. The default value -1 indicates that no service is bound |
| canDelete        | boolean        | no   | Whether it can be deleted                                    |
| nodeId           | string         | is   | Node Id                                                      |
| createdUser      | string         | is   | founder                                                      |
| gateway          | string         | no   | Gateway area                                                 |
| agentHashId      | string         | no   | agent hash id                                                |
