# Gets a pipeline list of projects

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines

### Resource description

#### Gets a pipeline list of projects

### Input parameter description

#### Query parameter

| Parameter name  | Parameter type | must | Parameter description             | Default value |
| :-------------- | :------------- | :--- | :-------------------------------- | :------------ |
| page            | integer        | no   | What page                         | 1             |
| pageSize        | integer        | no   | How many pieces per page          | 20            |
| checkPermission | boolean        | no   | Check permission                  |               |
| channelCode     | string         | no   | Channel number. The default is BS |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Page Data wrapper model pipeline model-list information](get-the-pipeline-list-of-the-project.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? page={page}&pageSize={pageSize}&checkPermission={checkPermission}&channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "latestBuildUserId" : "String",  "creator" : "String",  "latestBuildEndTime" : 0,  "buildCount" : 0,  "latestBuildTaskName" : "String",  "groupLabel" : [ {  "groupName" : "String",  "labelName" : "string"  } ],  "updateTime" : 0,  "pipelineDesc" : "String",  "pipelineId" : "String",  "latestBuildStartTime" : 0,  "pipelineName" : "String",  "canManualStartup" : true,  "pipelineVersion" : 0,  "taskCount" : 0,  "latestBuildId" : "String",  "createTime" : 0,  "runningBuildCount" : 0,  "latestBuildStatus" : "ENUM",  "lock" : true,  "model" : {  "latestVersion" : 0,  "pipelineCreator" : "String",  "name" : "String",  "stages" : [ {  "canRetry" : true,  "checkIn" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "customBuildEnv" : {  "string" : "string"  },  "finally" : true,  "name" : "String",  "containers" : [ {  "canRetry" : true,  "elementElapsed" : 0,  "startEpoch" : 0,  "executeCount" : 0,  "jobId" : "String",  "containPostTaskFlag" : true,  "systemElapsed" : 0,  "elements" : [ {  "canRetry" : true,  "errorType" : "String",  "errorCode" : 0,  "canSkip" : true,  "startEpoch" : 0,  "version" : "String",  "executeCount" : 0,  "templateModify" : true,  "elementEnable" : true,  "errorMsg" : "String",  "elapsed" : 0,  "atomCode" : "String",  "additionalOptions" : {  "enableCustomEnv" : true,  "continueWhenFailed" : true,  "manualRetry" : true,  "pauseBeforeExec" : true,  "retryCount" : 0,  "manualSkip" : true,  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ],  "otherTask" : "String",  "customEnv" : [ {  "value" : "String",  "key" : "String"  } ],  "retryWhenFailed" : true,  "enable" : true,  "subscriptionPauseUser" : "String",  "customCondition" : "String",  "runCondition" : "ENUM",  "elementPostInfo" : {  "parentElementId" : "String",  "postCondition" : "String",  "parentElementJobIndex" : 0,  "parentElementName" : "String",  "postEntryParam" : "String"  }  },  "taskAtom" : "String",  "name" : "String",  "id" : "String",  "classType" : "String",  "status" : "String"  } ],  "name" : "String",  "id" : "String",  "startVMStatus" : "String",  "containerId" : "String",  "classType" : "String",  "status" : "String"  } ],  "id" : "String",  "stageControlOption" : {  "triggered" : true,  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "enable" : true,  "customCondition" : "String",  "triggerUsers" : "string",  "reviewDesc" : "String",  "runCondition" : "ENUM",  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ]  },  "checkOut" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "fastKill" : true  } ],  "templateId" : "String",  "srcTemplateId" : "String",  "tips" : "String",  "desc" : "String",  "labels" : "string",  "instanceFromTemplate" : true  },  "latestBuildNum" : 0,  "projectId" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model Page Data wrapper model pipeline model-list information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Paging data wrapper model Pipelined model - list information](get-the-pipeline-list-of-the-project.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging data wrapper model Pipelined model - list information

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [pipeline model-list information](get-the-pipeline-list-of-the-project.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Pipeline model - List information

| Parameter name       | Parameter type                                               | must | Parameter description                  |
| :------------------- | :----------------------------------------------------------- | :--- | :------------------------------------- |
| latestBuildUserId    | string                                                       | no   | id of the last executor                |
| creator              | string                                                       | no   | Pipelining founder                     |
| latestBuildEndTime   | integer                                                      | no   | Last build end time                    |
| buildCount           | integer                                                      | is   | Number of builds                       |
| latestBuildTaskName  | string                                                       | no   | Finally build the task name            |
| groupLabel           | List<[PipelineGroupLabels](get-the-pipeline-list-of-the-project.md)> | no   | Pipelined grouping and labeling        |
| updateTime           | integer                                                      | is   | Deployment time                        |
| pipelineDesc         | string                                                       | no   | Pipeline description                   |
| pipelineId           | string                                                       | is   | Pipeline ID                            |
| latestBuildStartTime | integer                                                      | no   | Last build start time                  |
| pipelineName         | string                                                       | is   | Pipeline name                          |
| canManualStartup     | boolean                                                      | is   | Whether it can be manually started     |
| pipelineVersion      | integer                                                      | is   | Choreograph file version number        |
| taskCount            | integer                                                      | is   | Number of pipeline tasks               |
| latestBuildId        | string                                                       | no   | Finally build the instance ID          |
| createTime           | integer                                                      | is   | Pipeline creation time                 |
| runningBuildCount    | integer                                                      | is   | The number of currently running builds |
| latestBuildStatus    | ENUM(SUCCEED, FAILED, CANCELED, RUNNING, TERMINATE, REVIEWING, REVIEW_ABORT, REVIEW_PROCESSED, HEARTBEAT_TIMEOUT, PREPARE_ENV, UNEXEC, SKIP, QUALITY_CHECK_FAIL, QUEUE, LOOP_WAITING, CALL_WAITING, TRY_FINALLY, QUEUE_TIMEOUT, EXEC_TIMEOUT, QUEUE_CACHE, RETRY, PAUSE, STAGE_SUCCESS, QUOTA_FAILED, DEPENDENT_WAITING, UNKNOWN, ) | no   | Final build state                      |
| lock                 | boolean                                                      | no   | Run lock                               |
| model                | [Pipeline model - Create information](get-the-pipeline-list-of-the-project.md) | no   | Arrangement details                    |
| latestBuildNum       | integer                                                      | no   | Finally build the version number       |
| projectId            | string                                                       | is   | Item ID                                |

## PipelineGroupLabels

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| groupName      | string         | no   | groupName             |
| labelName      | List           | no   | labelName             |

## Pipeline model - Create information

| Parameter name       | Parameter type                                               | must | Parameter description                         |
| :------------------- | :----------------------------------------------------------- | :--- | :-------------------------------------------- |
| latestVersion        | integer                                                      | no   | Latest version of pipeline at submission time |
| pipelineCreator      | string                                                       | no   | founder                                       |
| name                 | string                                                       | is   | name                                          |
| stages               | List< [pipeline model-phase](get-the-pipeline-list-of-the-project.md) > | is   | Stage set                                     |
| templateId           | string                                                       | no   | Template ID                                   |
| srcTemplateId        | string                                                       | no   | ID of the source template                     |
| tips                 | string                                                       | no   | prompt                                        |
| desc                 | string                                                       | no   | description                                   |
| labels               | List                                                         | no   | label                                         |
| instanceFromTemplate | boolean                                                      | no   | Whether it is instantiated from the template  |

## Pipeline model - Phase

| Parameter name     | Parameter type                                               | must | Parameter description                                        |
| :----------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- |
| canRetry           | boolean                                                      | no   | Whether retries can be made at the current Stage             |
| checkIn            | [StagePauseCheck](get-the-pipeline-list-of-the-project.md)   | no   | Whether retries can be made at the current Stage             |
| customBuildEnv     | object                                                       | no   | User-defined environment variables                           |
| finally            | boolean                                                      | no   | Identifies whether it is FinallyStage. Each Model can contain only one FinallyStage and is in the last position |
| name               | string                                                       | is   | Stage name                                                   |
| containers         | List< [pipeline model-polymorphic base class >](get-the-pipeline-list-of-the-project.md) | is   | Container set                                                |
| id                 | string                                                       | no   | Phase ID                                                     |
| stageControlOption | [StageControlOption](get-the-pipeline-list-of-the-project.md) | is   | Flow control options                                         |
| checkOut           | [StagePauseCheck](get-the-pipeline-list-of-the-project.md)   | no   | Whether retries can be made at the current Stage             |
| fastKill           | boolean                                                      | no   | Whether to enable the container failure quick termination phase |

## StagePauseCheck

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| ruleIds        | List                                                         | no   | ruleIds               |
| reviewParams   | List< [Manual audit - Custom parameters](get-the-pipeline-list-of-the-project.md) > | no   | reviewParams          |
| manualTrigger  | boolean                                                      | no   | manualTrigger         |
| checkTimes     | integer                                                      | no   | checkTimes            |
| reviewDesc     | string                                                       | no   | reviewDesc            |
| reviewGroups   | List<[Stage Audit group information](get-the-pipeline-list-of-the-project.md) > | no   | reviewGroups          |
| timeout        | integer                                                      | no   | timeout               |
| status         | string                                                       | no   | status                |

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](get-the-pipeline-list-of-the-project.md) > | no   | Drop-down list        |
| chineseName    | string                                                       | no   | Chinese name          |
| value          | object                                                       | is   | Parameter content     |
| key            | string                                                       | is   | Parameter name        |
| required       | boolean                                                      | is   | Is it required?       |
| desc           | string                                                       | no   | Parameter description |

## Manual Audit - Custom Parameters - Drop down box list sword

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| value          | string         | is   | Parameter content     |
| key            | string         | is   | Parameter name        |

## Stage Audit group information

| Parameter name | Parameter type                                               | must | Parameter description                |
| :------------- | :----------------------------------------------------------- | :--- | :----------------------------------- |
| name           | string                                                       | is   | Audit group name                     |
| id             | string                                                       | no   | Audit team ID(background generation) |
| suggest        | string                                                       | no   | Audit suggestion                     |
| params         | List< [Manual audit - Custom parameters](get-the-pipeline-list-of-the-project.md) > | no   | Audit incoming variables             |
| reviewers      | List                                                         | is   | auditor                              |
| operator       | string                                                       | no   | Audit operator                       |
| reviewTime     | integer                                                      | no   | Audit operation time                 |
| status         | string                                                       | no   | Audit results (enumeration)          |

## Pipeline Model - polymorphic base class

| Parameter name      | Parameter type                                    | must | Parameter description |
| :------------------ | :------------------------------------------------ | :--- | :-------------------- |
| canRetry            | boolean                                           | no   | canRetry              |
| elementElapsed      | integer                                           | no   | elementElapsed        |
| startEpoch          | integer                                           | no   | startEpoch            |
| executeCount        | integer                                           | no   | executeCount          |
| jobId               | string                                            | no   | jobId                 |
| containPostTaskFlag | boolean                                           | no   | containPostTaskFlag   |
| systemElapsed       | integer                                           | no   | systemElapsed         |
| elements            | List[ ](get-the-pipeline-list-of-the-project.md)> | no   | elements              |
| name                | string                                            | no   | name                  |
| id                  | string                                            | no   | id                    |
| startVMStatus       | string                                            | no   | startVMStatus         |
| containerId         | string                                            | no   | containerId           |
| classType           | string                                            | no   | classType             |
| status              | string                                            | no   | status                |

## Element

| Parameter name    | Parameter type                                               | must | Parameter description |
| :---------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| canRetry          | boolean                                                      | no   | canRetry              |
| errorType         | string                                                       | no   | errorType             |
| errorCode         | integer                                                      | no   | errorCode             |
| canSkip           | boolean                                                      | no   | canSkip               |
| startEpoch        | integer                                                      | no   | startEpoch            |
| version           | string                                                       | no   | version               |
| executeCount      | integer                                                      | no   | executeCount          |
| templateModify    | boolean                                                      | no   | templateModify        |
| elementEnable     | boolean                                                      | no   | elementEnable         |
| errorMsg          | string                                                       | no   | errorMsg              |
| elapsed           | integer                                                      | no   | elapsed               |
| atomCode          | string                                                       | no   | atomCode              |
| additionalOptions | [ElementAdditionalOptions](get-the-pipeline-list-of-the-project.md) | no   | additionalOptions     |
| taskAtom          | string                                                       | no   | taskAtom              |
| name              | string                                                       | no   | name                  |
| id                | string                                                       | no   | id                    |
| classType         | string                                                       | no   | classType             |
| status            | string                                                       | no   | status                |

## ElementAdditionalOptions

| Parameter name        | Parameter type                                               | must | Parameter description |
| :-------------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| enableCustomEnv       | boolean                                                      | no   | enableCustomEnv       |
| continueWhenFailed    | boolean                                                      | no   | continueWhenFailed    |
| manualRetry           | boolean                                                      | no   | manualRetry           |
| pauseBeforeExec       | boolean                                                      | no   | pauseBeforeExec       |
| retryCount            | integer                                                      | no   | retryCount            |
| manualSkip            | boolean                                                      | no   | manualSkip            |
| timeout               | integer                                                      | no   | timeout               |
| customVariables       | List<[NameAndValue](get-the-pipeline-list-of-the-project.md)> | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](get-the-pipeline-list-of-the-project.md)> | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](get-the-pipeline-list-of-the-project.md) | no   | elementPostInfo       |

## NameAndValue

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| value          | string         | no   | value                 |
| key            | string         | no   | key                   |

## Element post message

| Parameter name        | Parameter type | must | Parameter description                         |
| :-------------------- | :------------- | :--- | :-------------------------------------------- |
| parentElementId       | string         | no   | Parent element ID                             |
| postCondition         | string         | no   | Execution condition                           |
| parentElementJobIndex | integer        | no   | The position of the parent element in the job |
| parentElementName     | string         | no   | Parent element name                           |
| postEntryParam        | string         | no   | Entry parameter                               |

## StageControlOption

| Parameter name  | Parameter type                                               | must | Parameter description |
| :-------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| triggered       | boolean                                                      | no   | triggered             |
| reviewParams    | List< [Manual audit - Custom parameters](get-the-pipeline-list-of-the-project.md) > | no   | reviewParams          |
| manualTrigger   | boolean                                                      | no   | manualTrigger         |
| enable          | boolean                                                      | no   | enable                |
| customCondition | string                                                       | no   | customCondition       |
| triggerUsers    | List                                                         | no   | triggerUsers          |
| reviewDesc      | string                                                       | no   | reviewDesc            |
| runCondition    | ENUM(AFTER_LAST_FINISHED, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, ) | no   | runCondition          |
| timeout         | integer                                                      | no   | timeout               |
| customVariables | List<[NameAndValue](get-the-pipeline-list-of-the-project.md)> | no   | customVariables       |
