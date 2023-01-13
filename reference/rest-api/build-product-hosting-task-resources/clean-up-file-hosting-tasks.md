# Clean up file hosting tasks

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/artifactory/fileTask/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/tasks/{taskId }/clear

### Resource description

#### Clean up file hosting tasks

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |
| pipelineId     | string         | is   | pipelineId            |               |
| buildId        | string         | is   | buildId               |               |
| taskId         | string         | is   | taskId                |               |

#### response

| HTTP code | description          | Parameter type                    |
| :-------- | :------------------- | :-------------------------------- |
| 200       | successful operation | Data return wrapper model Boolean |

#### Request sample

```
curl -X PUT '[Please replace with upper API address bar request address]' 
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
