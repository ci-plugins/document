# Change grouping

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/groups

### Resource description

#### Change grouping

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                         | must | Parameter description                | Default value |
| :------------- | :------------------------------------- | :--- | :----------------------------------- | :------------ |
| body           | [PipelineGroupUpdate](change-group.md) | is   | Pipelined tags group update requests |               |

#### response

| HTTP code | description          | Parameter type                                       |
| :-------- | :------------------- | :--------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](change-group.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## PipelineGroupUpdate

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | no   | name                  |
| id             | string         | no   | id                    |
| projectId      | string         | no   | projectId             |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
