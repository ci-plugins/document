# Add group

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/groups

### Resource description

#### Add group

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                      | must | Parameter description                | Default value |
| :------------- | :---------------------------------- | :--- | :----------------------------------- | :------------ |
| body           | [PipelineGroupCreate](add-group.md) | is   | Pipelined tag groups create requests |               |

#### response

| HTTP code | description          | Parameter type                                    |
| :-------- | :------------------- | :------------------------------------------------ |
| 200       | successful operation | [Data return wrapper model Boolean](add-group.md) |

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

## PipelineGroupCreate

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | no   | name                  |
| projectId      | string         | no   | projectId             |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
