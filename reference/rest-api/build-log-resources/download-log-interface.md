## Download log interface

## Request method/request path

### GET  /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/logs/download

## Resource Description

### Download log interface

## Input parameter description

### Query

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| tag | string | no | element ID |  |
| jobId | string | no | jobId |  |
| executeCount | integer | no | Number of executions |  |

### Path

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| projectId | string | yes | project ID |  |
| pipelineId | string | yes | pipeline ID |  |
| buildId | string | yes | build ID |  |

### Response

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| default | successful operation | parse error |

### Request Demo

```javascript
curl -X GET '[API URL]?tag={tag}&amp;jobId={jobId}&amp;executeCount={executeCount}'
```

### HEADER Demo

```javascript
accept: application/json
Content-Type: application/json
```

