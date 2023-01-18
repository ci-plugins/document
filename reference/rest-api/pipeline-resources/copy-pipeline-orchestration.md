# Copy pipelining

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/copy

### Resource description

#### Copy pipelining

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Pipeline-copy Indicates the creation information](copy-pipeline-orchestration.md) | is   | Pipeline COPY         |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline model        |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model pipelining model-ID](copy-pipeline-orchestration.md) |

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
{  "data" : {  "id" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Pipeline-copy Indicates the creation information

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | is   | name                  |
| hasCollect     | boolean        | no   | Collection or not     |
| desc           | string         | no   | description           |
| group          | string         | no   | Group name            |

## The data is returned to the wrapper model pipelining model-ID

| Parameter name | Parameter type                                       | must | Parameter description |
| :------------- | :--------------------------------------------------- | :--- | :-------------------- |
| data           | [Pipeline model -ID](copy-pipeline-orchestration.md) | no   | data                  |
| message        | string                                               | no   | Error message         |
| status         | integer                                              | is   | Status code           |

## Pipeline model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | is   | Pipeline ID           |
