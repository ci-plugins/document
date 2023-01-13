# Get pipelineId+ auto-increment id under the project

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/permission/move/projects/{projectCode}/pipelineIds/list

### Resource description

#### Get pipelineId+ auto-increment id under the project

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectCode    | string         | is   | Project Code          |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model ListPipelineIdInfo](get-the-pipelineid-and-auto-increment-id-under-the-project.md) |

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
{  "data" : [ {  "id" : 0,  "pipelineId" : "String"  } ],  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model ListPipelineIdInfo

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | List<[PipelineIdInfo](get-the-pipelineid-and-auto-increment-id-under-the-project.md)> | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## PipelineIdInfo

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | integer        | no   | id                    |
| pipelineId     | string         | no   | pipelineId            |
