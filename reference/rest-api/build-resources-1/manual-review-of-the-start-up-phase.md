# Manually audit the startup phase

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/stages/{stageId}/manualStart

### Resource description

#### Manually audit the startup phase

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| cancel         | boolean        | no   | Cancel execution      |               |

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Manual audit - Customize parameters](manual-review-of-the-start-up-phase.md) | no   | Audit request body    |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |
| stageId        | string         | is   | Phase ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](manual-review-of-the-start-up-phase.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? cancel={cancel}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](manual-review-of-the-start-up-phase.md) > | no   | Drop-down list        |
| chineseName    | string                                                       | no   | Chinese name          |
| value          | object                                                       | is   | Parameter content     |
| key            | string                                                       | is   | Parameter name        |
| required       | boolean                                                      | is   | Is it required?       |
| desc           | string                                                       | no   | Parameter description |

## Manual Audit - Custom Parameters - Drop down box list sword

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| value          | string         | is   | Parameter content     |
| key            | string         | is   | Parameter name        |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
