# Change label

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/labels

### Resource description

#### Change label

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                         | must | Parameter description          | Default value |
| :------------- | :------------------------------------- | :--- | :----------------------------- | :------------ |
| body           | [PipelineLabelUpdate](change-label.md) | is   | Pipelined label update request |               |

#### response

| HTTP code | description          | Parameter type                                       |
| :-------- | :------------------- | :--------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](change-label.md) |

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

## PipelineLabelUpdate

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| groupId        | string         | no   | groupId               |
| name           | string         | no   | name                  |
| id             | string         | no   | id                    |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
