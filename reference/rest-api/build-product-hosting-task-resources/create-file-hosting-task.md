# Create a file hosting task

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/artifactory/fileTask/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/create

### Resource description

#### Create a file hosting task

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                     | must | Parameter description | Default value |
| :------------- | :--------------------------------- | :--- | :-------------------- | :------------ |
| body           | Create a file hosting task request | is   | taskId                |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |
| pipelineId     | string         | is   | pipelineId            |               |
| buildId        | string         | is   | buildId               |               |

#### response

| HTTP code | description          | Parameter type                                   |
| :-------- | :------------------- | :----------------------------------------------- |
| 200       | successful operation | The data is returned to the wrapper model String |

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
{  "data" : "String",  "message" : "String",  "status" : 0 } 
```

## Create a file hosting task request

| Parameter name | Parameter type                                         | must | Parameter description |
| :------------- | :----------------------------------------------------- | :--- | :-------------------- |
| path           | string                                                 | is   | File path             |
| fileType       | ENUM(BK_ARCHIVE, BK_CUSTOM, BK_REPORT, BK_PLUGIN_FE, ) | is   | File type             |

## The data is returned to the wrapper model String

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | string         | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
