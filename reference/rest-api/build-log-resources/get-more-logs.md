# Get more Logs

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/logs/more

### Resource description

#### Get more Logs

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description           | Default value |
| -------------- | -------------- | ---- | ------------------------------- | ------------- |
| debug          | boolean        | no   | Whether to contain debug logs   |               |
| num            | integer        | no   | Log line count                  |               |
| fromStart      | boolean        | no   | Output in positive order or not |               |
| start          | integer        | is   | Starting line number            |               |
| end            | integer        | is   | End line number                 |               |
| tag            | string         | no   | Corresponds to elementId        |               |
| jobId          | string         | no   | Corresponding jobId             |               |
| executeCount   | integer        | no   | Number of executions            |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| -------------- | -------------- | ---- | --------------------- | ------------- |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| --------- | -------------------- | ------------------------------------------------------------ |
| 200       | successful operation | [Data return wrapper model Log query model](https://github.com/ci-plugins/document/blob/en-us/reference/rest-api/build-log-resources/get-more-logs.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? debug={debug}&num={num}&fromStart={fromStart}&start={start}&end={end}&tag={tag}&jobId={jobId}&executeCount={executeCount } '
```

#### HEADER example

```
accept: application/json Content-Type: application/json
```

### Return example -200

```
{ "data" : { "timeUsed" : 0, "hasMore" : true, "subTags" : "string", "buildId" : "String", "finished" : true, "logs" : [ { "subTag" : "String", "jobId" : "String", "lineNo" : 0, "tag" : "String", "message" : "String", "priority" : "String", "executeCount" : 0, "timestamp" : 0 } ], "status" : 0 }, "message" : "String", "status" : 0 }
```

## Data return wrapper model Log query model

| Parameter name | Parameter type                                               | must | Parameter description |
| -------------- | ------------------------------------------------------------ | ---- | --------------------- |
| data           | [Log query model](https://github.com/ci-plugins/document/blob/en-us/reference/rest-api/build-log-resources/get-more-logs.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Log query model

| Parameter name | Parameter type                                               | must | Parameter description                       |
| -------------- | ------------------------------------------------------------ | ---- | ------------------------------------------- |
| timeUsed       | integer                                                      | no   | Time used                                   |
| hasMore        | boolean                                                      | no   | Check whether subsequent logs are generated |
| subTags        | List                                                         | is   | Nishiko tag list                            |
| buildId        | string                                                       | is   | Build ID                                    |
| finished       | boolean                                                      | is   | End or not                                  |
| logs           | List< [log model](https://github.com/ci-plugins/document/blob/en-us/reference/rest-api/build-log-resources/get-more-logs.md) > | is   | Log list                                    |
| status         | integer                                                      | no   | Log query status                            |

## Log model

| Parameter name | Parameter type | must | Parameter description |
| -------------- | -------------- | ---- | --------------------- |
| subTag         | string         | is   | Nichiko tag           |
| jobId          | string         | is   | Log jobId             |
| lineNo         | integer        | is   | Log line number       |
| tag            | string         | is   | Log tag               |
| message        | string         | is   | Log message body      |
| priority       | string         | is   | Log weight level      |
| executeCount   | integer        | is   | Log execution times   |
| timestamp      | integer        | is   | Log timestamp         |
