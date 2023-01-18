# Remove pipelining

### Request method/request path

#### DELETE /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}

### Resource description

#### Remove pipelining

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description             | Default value |
| :------------- | :------------- | :--- | :-------------------------------- | :------------ |
| channelCode    | string         | no   | Channel number. The default is BS |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](delete-the-pipeline-orchestration.md) |

#### Request sample

```
curl -X DELETE '[Please replace API address bar request address]? channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
