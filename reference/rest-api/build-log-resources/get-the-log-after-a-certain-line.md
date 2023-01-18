#  Get the log after a certain line

### Request method/request path

#### GET  /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/logs/after

### Resource Description

#### Get the log after a certain line

### Input parameter description

#### Query Parameters

| Parameter Name | Parameter Type | Required | Parameter Description | Default |
| :--- | :--- | :--- | :--- | :--- |
| start | integer | yes | start line number |  |
| debug | boolean | no | whether to include debug logs |  |
| tag | string | no | the corresponding elementId |  |
| jobId | string | no | The corresponding jobId |  |
| executeCount | integer | no | Execution count |  |

#### Path Parameters

| Parameter Name | Parameter Type | Required | Parameter Description | Default |
| :--- | :--- | :--- | :--- | :--- |
| projectId | string | yes | project ID |  |
| pipelineId | string | yes | pipeline ID |  |
| buildId | string | yes | build ID |  |

#### 响应

| HTTP code | Description | Parameter Type |
| :--- | :--- | :--- |
| 200 | successful operation | [Data return wrapper model log query model](get-the-log-after-a-certain-line.md) |

#### request demo

```javascript
curl -X GET '[API URL]?start={start}&amp;debug={debug}&amp;tag={tag}&amp;jobId={jobId}&amp;executeCount={executeCount}'
```

#### HEADER demo

```javascript
accept: application/json
Content-Type: application/json
```

### response demo-200

```javascript
{
  "data" : {
    "timeUsed" : 0,
    "hasMore" : true,
    "subTags" : "string",
    "buildId" : "String",
    "finished" : true,
    "logs" : [ {
      "subTag" : "String",
      "jobId" : "String",
      "lineNo" : 0,
      "tag" : "String",
      "message" : "String",
      "priority" : "String",
      "executeCount" : 0,
      "timestamp" : 0
    } ],
    "status" : 0
  },
  "message" : "String",
  "status" : 0
}
```

## Data return wrapper model log query model

| Parameter Name | Parameter Type | Required | Parameter Description |
| :--- | :--- | :--- | :--- |
| data | [Log query model](get-the-log-after-a-certain-line.md) | no | data |
| message | string | no | error message |
| status | integer | yes | statuscode |

## Log query model

| Parameter Name | Parameter Type | Required | Parameter Description |
| :--- | :--- | :--- | :--- |
| timeUsed | integer | no   | cost time |
| hasMore | boolean | no | Is there a follow-up log |
| subTags | List | yes | Log sub-tag list |
| buildId | string | yes | build ID |
| finished | boolean | yes | Whether to end |
| logs | List&lt;[log model](get-the-log-after-a-certain-line.md)&gt; | yes | 日志列表 |
| status | integer | no | Log query status |

## Log model

| Parameter Name | Parameter Type | Required | Parameter Description |
| :--- | :--- | :--- | :--- |
| subTag | string | yes | log children tag |
| jobId | string | yes | log jobId |
| lineNo | integer | yes | log 行号 |
| tag | string | yes | log  tag |
| message | string | yes | log message body |
| priority | string | yes | log weight level |
| executeCount | integer | yes | log execution count |
| timestamp | integer | yes |  log timestamp |

