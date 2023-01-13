# Gets the pipeline's webhook build log list

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/{projectId}/{pipelineId}/webhook/buildLog

### Resource description

#### Gets the pipeline's webhook build log list

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| repoName       | string         | no   | Warehouse name        |               |
| commitId       | string         | no   | commitId              |               |
| page           | integer        | no   | Page number           |               |
| pageSize       | integer        | no   | Page size             |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   |                       |               |
| pipelineId     | string         | is   |                       |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model SQLPage pipelining webhook- Trigger log details](get-the-pipelines-webhook-build-log-list.md) |

#### Request sample

```
curl -X GET '[Please replace above API address bar request address]? repoName={repoName}&commitId={commitId}&page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "codeType" : "String",  "repoName" : "String",  "success" : true,  "triggerResult" : "String",  "createdTime" : 0,  "logId" : 0,  "taskName" : "String",  "id" : 0,  "commitId" : "String",  "projectId" : "String",  "taskId" : "String",  "pipelineId" : "String"  } ],  "count" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model SQLPage pipelining webhook- Trigger log details

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [SQLPage Pipelined webhook- Triggers log details](get-the-pipelines-webhook-build-log-list.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## SQLPage Pipelined webhook- Triggers log details

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| records        | List< [pipeline Webhook-trigger log Details](get-the-pipelines-webhook-build-log-list.md) > | no   | records               |
| count          | integer                                                      | no   | count                 |

## Pipelined webhook- Triggers log details

| Parameter name | Parameter type | must | Parameter description                                        |
| :------------- | :------------- | :--- | :----------------------------------------------------------- |
| codeType       | string         | is   | Code base type                                               |
| repoName       | string         | is   | Warehouse name                                               |
| success        | boolean        | is   | Successful trigger                                           |
| triggerResult  | string         | is   | Trigger result, if the trigger is successful it is buildId, if the trigger is unsuccessful it is the reason for the failure |
| createdTime    | integer        | no   | createdTime                                                  |
| logId          | integer        | no   | logId                                                        |
| taskName       | string         | is   | Plug-in name                                                 |
| id             | integer        | no   | id                                                           |
| commitId       | string         | is   | commitId                                                     |
| projectId      | string         | is   | Item ID                                                      |
| taskId         | string         | is   | Plug-in ID                                                   |
| pipelineId     | string         | is   | Pipeline ID                                                  |
