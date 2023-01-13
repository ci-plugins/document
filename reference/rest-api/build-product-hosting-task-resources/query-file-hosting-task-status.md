# Example Query the file hosting task status

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/artifactory/fileTask/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/tasks/{taskId }/status

### Resource description

#### Example Query the file hosting task status

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |
| pipelineId     | string         | is   | pipelineId            |               |
| buildId        | string         | is   | buildId               |               |
| taskId         | string         | is   | taskId                |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | The data returns packaging model version repository - file hosting task information |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "path" : "String",  "ip" : "String",  "id" : "String",  "status" : 0  },  "message" : "String",  "status" : 0 } 
```

## The data returns packaging model version repository - file hosting task information

| Parameter name | Parameter type                                     | must | Parameter description |
| :------------- | :------------------------------------------------- | :--- | :-------------------- |
| data           | Version Repository - File hosting task information | no   | data                  |
| message        | string                                             | no   | Error message         |
| status         | integer                                            | is   | Status code           |

## Version Repository - File hosting task information

| Parameter name | Parameter type | must | Parameter description                               |
| :------------- | :------------- | :--- | :-------------------------------------------------- |
| path           | string         | is   | Absolute file path                                  |
| ip             | string         | is   | IP address of the machine where the file is located |
| id             | string         | is   | Task Id                                             |
| status         | integer        | is   | Task status                                         |
