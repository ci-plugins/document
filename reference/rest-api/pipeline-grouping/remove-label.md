# Remove label

### Request method/request path

#### DELETE /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/labels/{labelId}

### Resource description

#### Remove label

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| labelId        | string         | is   | Tag ID                |               |

#### response

| HTTP code | description          | Parameter type                                       |
| :-------- | :------------------- | :--------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](remove-label.md) |

#### Request sample

```
curl -X DELETE '[Please replace API address bar request address]' 
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
