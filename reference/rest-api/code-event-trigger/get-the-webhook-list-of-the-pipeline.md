# Gets the list of Webhooks for the pipeline

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/{projectId}/{pipelineId}/webhook

### Resource description

#### Gets the list of Webhooks for the pipeline

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| page           | integer        | no   | Page number           |               |
| pageSize       | integer        | no   | Page size             |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   |                       |               |
| pipelineId     | string         | is   |                       |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model ListPipelineWebhook](get-the-webhook-list-of-the-pipeline.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : [ {  "repoType" : "ENUM",  "repoName" : "String",  "repositoryType" : "ENUM",  "id" : 0,  "projectName" : "String",  "projectId" : "String",  "repoHashId" : "String",  "taskId" : "String",  "pipelineId" : "String"  } ],  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model ListPipelineWebhook

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | List<[PipelineWebhook](get-the-webhook-list-of-the-pipeline.md)> | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## PipelineWebhook

| Parameter name | Parameter type                                             | must | Parameter description |
| :------------- | :--------------------------------------------------------- | :--- | :-------------------- |
| repoType       | ENUM(ID, NAME, )                                           | no   | repoType              |
| repoName       | string                                                     | no   | repoName              |
| repositoryType | ENUM(CODE_SVN, CODE_GIT, CODE_GITLAB, GITHUB, CODE_TGIT, ) | no   | repositoryType        |
| id             | integer                                                    | no   | id                    |
| projectName    | string                                                     | no   | projectName           |
| projectId      | string                                                     | no   | projectId             |
| repoHashId     | string                                                     | no   | repoHashId            |
| taskId         | string                                                     | no   | taskId                |
| pipelineId     | string                                                     | no   | pipelineId            |
