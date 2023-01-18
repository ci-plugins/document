# Get the code commit record

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/repositoryCommit

### Resource description

#### Get the code commit record

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | buildID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model ListCommitResponse](get-the-code-submission-record.md) |

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
{  "data" : [ {  "elementId" : "String",  "records" : [ {  "elementId" : "String",  "repoId" : "String",  "committer" : "String",  "commitTime" : 0,  "repoName" : "String",  "commit" : "String",  "buildId" : "String",  "comment" : "String",  "type" : 0,  "url" : "String",  "pipelineId" : "String"  } ],  "name" : "String"  } ],  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model ListCommitResponse

| Parameter name | Parameter type                                            | must | Parameter description |
| :------------- | :-------------------------------------------------------- | :--- | :-------------------- |
| data           | List<[CommitResponse](get-the-code-submission-record.md)> | no   | data                  |
| message        | string                                                    | no   | Error message         |
| status         | integer                                                   | is   | Status code           |

## CommitResponse

| Parameter name | Parameter type                                        | must | Parameter description |
| :------------- | :---------------------------------------------------- | :--- | :-------------------- |
| elementId      | string                                                | no   | elementId             |
| records        | List<[CommitData](get-the-code-submission-record.md)> | no   | records               |
| name           | string                                                | no   | name                  |

## CommitData

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| elementId      | string         | no   | elementId             |
| repoId         | string         | no   | repoId                |
| committer      | string         | no   | committer             |
| commitTime     | integer        | no   | commitTime            |
| repoName       | string         | no   | repoName              |
| commit         | string         | no   | commit                |
| buildId        | string         | no   | buildId               |
| comment        | string         | no   | comment               |
| type           | integer        | no   | type                  |
| url            | string         | no   | url                   |
| pipelineId     | string         | no   | pipelineId            |
