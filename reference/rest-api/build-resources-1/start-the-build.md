# Start build

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/start

### Resource description

#### Start build

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description                     | Default value |
| :------------- | :------------- | :--- | :---------------------------------------- | :------------ |
| buildNo        | integer        | no   | Manually specify build version parameters |               |
| channelCode    | string         | no   | Channel number. The default is BS         |               |

#### Body parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| body           | map            | is   | Startup parameter     |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data returns wrapper model build model-ID](start-the-build.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? buildNo={buildNo}&channelCode={channelCode}' 
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
| data           | [Build model -ID](start-the-build.md) | no   | data                  |
| message        | string                                | no   | Error message         |
| status         | integer                               | is   | Status code           |

## Build model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | is   | Build ID              |
