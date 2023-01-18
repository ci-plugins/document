# Retry build - Retry or skip the failed plug-in

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/retry

### Resource description

#### Retry build - Retry or skip the failed plug-in

### Input parameter description

#### Query parameter

| Parameter name  | Parameter type | must | Parameter description                                        | Default value |
| :-------------- | :------------- | :--- | :----------------------------------------------------------- | :------------ |
| taskId          | string         | no   | Plug-in ID to retry or skip, or StageId                      |               |
| failedContainer | boolean        | no   | Retry only all failed jobs                                   |               |
| skip            | boolean        | no   | If true, pass a taskId value (stageId means that all failed plug-ins under the Stage are skipped). |               |
| channelCode     | string         | no   | Channel number. The default is BS                            |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data returns wrapper model build model-ID](retry-the-build.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? taskId={taskId}&failedContainer={failedContainer}&skip={skip}&channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "id" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Data returns wrapper model build model-ID

| Parameter name | Parameter type                        | must | Parameter description |
| :------------- | :------------------------------------ | :--- | :-------------------- |
| data           | [Build model -ID](retry-the-build.md) | no   | data                  |
| message        | string                                | no   | Error message         |
| status         | integer                               | is   | Status code           |

## Build model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | is   | Build ID              |
