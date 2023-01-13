# Get build node information (extension interface)

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/environment/projects/{projectId}/nodes/{nodeHashId}/listPipelineRef

### Resource description

#### Get build node information (extension interface)

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description       | Default value |
| :------------- | :------------- | :--- | :-------------------------- | :------------ |
| sortBy         | string         | yes  | Sort the field pipelineName | lastBuildTime |
| sortDirection  | string         | yes  | Sort direction, ASC         | DESC          |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | yes  | Item ID               |               |
| nodeHashId     | string         | yes  | Node hashId           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data return wrapper model List third-party builder pipeline reference information |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? sortBy={sortBy}&sortDirection={sortDirection}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{
  "data" : [ {
    "pipelineName" : "String",
    "jobName" : "String",
    "jobId" : "String",
    "agentId" : 0,
    "vmSeqId" : "String",
    "nodeHashId" : "String",
    "nodeId" : 0,
    "projectId" : "String",
    "agentHashId" : "String",
    "pipelineId" : "String",
    "lastBuildTime" : "String"
  } ],
  "message" : "String",
  "status" : 0
}
```

## Data return wrapper model List third-party builder pipeline reference information

| Parameter name | Parameter type                                             | must | Parameter description |
| :------------- | :--------------------------------------------------------- | :--- | :-------------------- |
| data           | List< third-party builder pipeline reference information > | no   | data                  |
| message        | string                                                     | no   | Error message         |
| status         | integer                                                    | yes  | Status code           |

## Third party builder pipeline reference information

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| pipelineName   | string         | yes  | Pipeline name         |
| jobName        | string         | yes  | Job Name              |
| jobId          | string         | yes  | Job ID                |
| agentId        | integer        | yes  | Agent ID              |
| vmSeqId        | string         | yes  | Vm Seq ID             |
| nodeHashId     | string         | yes  | Node Hash ID          |
| nodeId         | integer        | yes  | Node ID               |
| projectId      | string         | yes  | Item ID               |
| agentHashId    | string         | yes  | Agent Hash ID         |
| pipelineId     | string         | yes  | Pipeline ID           |
| lastBuildTime  | string         | no   | Last build time       |
