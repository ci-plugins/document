# View the build status

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/status

### Resource description

#### View the build status

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description             | Default value |
| :------------- | :------------- | :--- | :-------------------------------- | :------------ |
| channelCode    | string         | no   | Channel number. The default is BS |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model with the historical build model with build variables](view-build-status-information.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "buildNum" : 0,  "buildNumAlias" : "String",  "stageStatus" : [ {  "name" : "String",  "stageId" : "String"  } ],  "remark" : "String",  "buildMsg" : "String",  "startTime" : 0,  "id" : "String",  "recommendVersion" : "String",  "retry" : true,  "variables" : {  "string" : "string"  },  "totalTime" : 0,  "webHookType" : "String",  "mobileStart" : true,  "startType" : "String",  "trigger" : "String",  "userId" : "String",  "deleteReason" : "String",  "queueTime" : 0,  "pipelineVersion" : 0,  "buildParameters" : [ {  "valueType" : "ENUM",  "readOnly" : true,  "value" : {  "string" : "string"  },  "key" : "String"  } ],  "material" : [ {  "newCommitId" : "String",  "aliasName" : "String",  "commitTimes" : 0,  "branchName" : "String",  "url" : "String",  "newCommitComment" : "String"  } ],  "currentTimestamp" : 0,  "artifactList" : [ {  "fullPath" : "String",  "modifiedTime" : 0,  "appVersion" : "String",  "shortUrl" : "String",  "downloadUrl" : "String",  "fullName" : "String",  "path" : "String",  "folder" : true,  "size" : 0,  "name" : "String",  "artifactoryType" : "ENUM",  "properties" : [ {  "value" : "String",  "key" : "String"  } ],  "md5" : "String"  } ],  "endTime" : 0,  "webhookInfo" : {  "webhookBranch" : "String",  "webhookEventType" : "String",  "webhookMessage" : "String",  "webhookMergeCommitSha" : "String",  "webhookRepoUrl" : "String",  "webhookCommitId" : "String",  "webhookType" : "String"  },  "errorInfoList" : [ {  "atomCode" : "String",  "errorType" : 0,  "errorCode" : 0,  "taskName" : "String",  "taskId" : "String",  "errorMsg" : "String"  } ],  "status" : "String",  "executeTime" : 0  },  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model with the historical build model with build variables

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Historical construction model with construction variables](view-build-status-information.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Historical construction model with construction variables

| Parameter name   | Parameter type                                               | must | Parameter description                                    |
| :--------------- | :----------------------------------------------------------- | :--- | :------------------------------------------------------- |
| buildNum         | integer                                                      | is   | Build number                                             |
| buildNumAlias    | string                                                       | no   | Customize the build version number                       |
| stageStatus      | List< [historical construction phase status](view-build-status-information.md) > | is   | Stage state                                              |
| remark           | string                                                       | no   | remarks                                                  |
| buildMsg         | string                                                       | no   | Construction information                                 |
| startTime        | integer                                                      | is   | Start time                                               |
| id               | string                                                       | is   | Build ID                                                 |
| recommendVersion | string                                                       | no   | Recommended version number                               |
| retry            | boolean                                                      | no   | Retry or not                                             |
| variables        | object                                                       | is   | Construct a set of variables                             |
| totalTime        | integer                                                      | no   | Total time (seconds)                                     |
| webHookType      | string                                                       | no   | WebHookType                                              |
| mobileStart      | boolean                                                      | no   | mobileStart                                              |
| startType        | string                                                       | no   | Startup type (New)                                       |
| trigger          | string                                                       | is   | Trigger condition                                        |
| userId           | string                                                       | is   | Startup user                                             |
| deleteReason     | string                                                       | is   | End reason                                               |
| queueTime        | integer                                                      | no   | Queue up                                                 |
| pipelineVersion  | integer                                                      | is   | Choreograph file version number                          |
| buildParameters  | List< [Build model-build parameters](view-build-status-information.md) > | no   | Startup parameter                                        |
| material         | List<[PipelineBuildMaterial](view-build-status-information.md)> | no   | Raw material                                             |
| currentTimestamp | integer                                                      | is   | Current server timestamp                                 |
| artifactList     | List< [version repository - file information](view-build-status-information.md) > | no   | Component list                                           |
| endTime          | integer                                                      | is   | End time                                                 |
| webhookInfo      | [WebhookInfo](view-build-status-information.md)              | no   | webhookInfo                                              |
| errorInfoList    | List< [plug-in error message](view-build-status-information.md) > | no   | Pipelined task execution error                           |
| status           | string                                                       | is   | state                                                    |
| executeTime      | integer                                                      | no   | Running time (seconds, not including manual review time) |

## Historical construction phase state

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | is   | Stage name            |
| stageId        | string         | is   | Phase ID              |

## Build model - Build parameters

| Parameter name | Parameter type                                               | must | Parameter description            |
| :------------- | :----------------------------------------------------------- | :--- | :------------------------------- |
| valueType      | ENUM(STRING, TEXTAREA, ENUM, DATE, LONG, BOOLEAN, SVN_TAG, GIT_REF, MULTIPLE, CODE_LIB, CONTAINER_TYPE, ARTIFACTORY, SUB_PIPELINE, CUSTOM_FILE, PASSWORD, TEMPORARY, ) | no   | Element value type               |
| readOnly       | boolean                                                      | no   | Whether to read only             |
| value          | object                                                       | is   | Element value Name - for display |
| key            | string                                                       | is   | Element value ID- identifier     |

## PipelineBuildMaterial

| Parameter name   | Parameter type | must | Parameter description |
| :--------------- | :------------- | :--- | :-------------------- |
| newCommitId      | string         | no   | newCommitId           |
| aliasName        | string         | no   | aliasName             |
| commitTimes      | integer        | no   | commitTimes           |
| branchName       | string         | no   | branchName            |
| url              | string         | no   | url                   |
| newCommitComment | string         | no   | newCommitComment      |

## Version repository - File information

| Parameter name  | Parameter type                                               | must | Parameter description |
| :-------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| fullPath        | string                                                       | is   | Full file path        |
| modifiedTime    | integer                                                      | is   | Update time           |
| appVersion      | string                                                       | is   | app version           |
| shortUrl        | string                                                       | is   | Download short link   |
| downloadUrl     | string                                                       | no   | Download link         |
| fullName        | string                                                       | is   | Full name of document |
| path            | string                                                       | is   | File path             |
| folder          | boolean                                                      | is   | Yes folder            |
| size            | integer                                                      | is   | File size (byte)      |
| name            | string                                                       | is   | File name             |
| artifactoryType | ENUM(PIPELINE, CUSTOM_DIR, )                                 | is   | Warehouse type        |
| properties      | List< [version repository - metadata](view-build-status-information.md) > | is   | metadata              |
| md5             | string                                                       | no   | MD5                   |

## Version Repository - Metadata

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| value          | string         | is   | Metadata value        |
| key            | string         | is   | Metadata key          |

## WebhookInfo

| Parameter name        | Parameter type | must | Parameter description |
| :-------------------- | :------------- | :--- | :-------------------- |
| webhookBranch         | string         | no   | webhookBranch         |
| webhookEventType      | string         | no   | webhookEventType      |
| webhookMessage        | string         | no   | webhookMessage        |
| webhookMergeCommitSha | string         | no   | webhookMergeCommitSha |
| webhookRepoUrl        | string         | no   | webhookRepoUrl        |
| webhookCommitId       | string         | no   | webhookCommitId       |
| webhookType           | string         | no   | webhookType           |

## Plug-in error message

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| atomCode       | string         | no   | Plug-in number        |
| errorType      | integer        | no   | Error type            |
| errorCode      | integer        | is   | Error code            |
| taskName       | string         | no   | Plug-in name          |
| taskId         | string         | no   | Plug-in ID            |
| errorMsg       | string         | no   | Error message         |
