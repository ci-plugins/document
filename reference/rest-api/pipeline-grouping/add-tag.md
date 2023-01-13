# Add tag

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/labels

### Resource description

#### Add tag

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                    | must | Parameter description          | Default value |
| :------------- | :-------------------------------- | :--- | :----------------------------- | :------------ |
| body           | [PipelineLabelCreate](add-tag.md) | is   | Pipelined tag creation request |               |

#### response

| HTTP code | description          | Parameter type                                  |
| :-------- | :------------------- | :---------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](add-tag.md) |

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

## PipelineLabelCreate

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| groupId        | string         | no   | groupId               |
| name           | string         | no   | name                  |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
