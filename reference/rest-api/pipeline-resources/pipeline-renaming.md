# Pipeline renaming

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/rename

### Resource description

#### Pipeline renaming

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                               | must | Parameter description | Default value |
| :------------- | :------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Pipeline model -NAME](pipeline-renaming.md) | is   | Pipeline name         |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |

#### response

| HTTP code | description          | Parameter type                                            |
| :-------- | :------------------- | :-------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](pipeline-renaming.md) |

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
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Pipeline model -NAME

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | is   | Pipeline name         |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
