# Acquisition pipeline layout

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}

### Resource description

#### Acquisition pipeline layout

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| channelCode    | string         | no   | channel               |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data returns wrapper model pipelined Model-creation information](get-the-pipeline-orchestration.md) |

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
{  "data" : {  "latestVersion" : 0,  "pipelineCreator" : "String",  "name" : "String",  "stages" : [ {  "canRetry" : true,  "checkIn" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "customBuildEnv" : {  "string" : "string"  },  "finally" : true,  "name" : "String",  "containers" : [ {  "canRetry" : true,  "elementElapsed" : 0,  "startEpoch" : 0,  "executeCount" : 0,  "jobId" : "String",  "containPostTaskFlag" : true,  "systemElapsed" : 0,  "elements" : [ {  "canRetry" : true,  "errorType" : "String",  "errorCode" : 0,  "canSkip" : true,  "startEpoch" : 0,  "version" : "String",  "executeCount" : 0,  "templateModify" : true,  "elementEnable" : true,  "errorMsg" : "String",  "elapsed" : 0,  "atomCode" : "String",  "additionalOptions" : {  "enableCustomEnv" : true,  "continueWhenFailed" : true,  "manualRetry" : true,  "pauseBeforeExec" : true,  "retryCount" : 0,  "manualSkip" : true,  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ],  "otherTask" : "String",  "customEnv" : [ {  "value" : "String",  "key" : "String"  } ],  "retryWhenFailed" : true,  "enable" : true,  "subscriptionPauseUser" : "String",  "customCondition" : "String",  "runCondition" : "ENUM",  "elementPostInfo" : {  "parentElementId" : "String",  "postCondition" : "String",  "parentElementJobIndex" : 0,  "parentElementName" : "String",  "postEntryParam" : "String"  }  },  "taskAtom" : "String",  "name" : "String",  "id" : "String",  "classType" : "String",  "status" : "String"  } ],  "name" : "String",  "id" : "String",  "startVMStatus" : "String",  "containerId" : "String",  "classType" : "String",  "status" : "String"  } ],  "id" : "String",  "stageControlOption" : {  "triggered" : true,  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "enable" : true,  "customCondition" : "String",  "triggerUsers" : "string",  "reviewDesc" : "String",  "runCondition" : "ENUM",  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ]  },  "checkOut" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "fastKill" : true  } ],  "templateId" : "String",  "srcTemplateId" : "String",  "tips" : "String",  "desc" : "String",  "labels" : "string",  "instanceFromTemplate" : true  },  "message" : "String",  "status" : 0 } 
```

## Data returns wrapper model pipelined Model-creation information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Pipeline model - Create information](get-the-pipeline-orchestration.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Pipeline model - Create information

| Parameter name       | Parameter type                                               | must | Parameter description                         |
| :------------------- | :----------------------------------------------------------- | :--- | :-------------------------------------------- |
| latestVersion        | integer                                                      | no   | Latest version of pipeline at submission time |
| pipelineCreator      | string                                                       | no   | founder                                       |
| name                 | string                                                       | is   | name                                          |
| stages               | List< [pipeline model-phase](get-the-pipeline-orchestration.md) > | is   | Stage set                                     |
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
| checkIn            | [StagePauseCheck](get-the-pipeline-orchestration.md)         | no   | Whether retries can be made at the current Stage             |
| customBuildEnv     | object                                                       | no   | User-defined environment variables                           |
| finally            | boolean                                                      | no   | Identifies whether it is FinallyStage. Each Model can contain only one FinallyStage and is in the last position |
| name               | string                                                       | is   | Stage name                                                   |
| containers         | List< [pipeline model-polymorphic base class >](get-the-pipeline-orchestration.md) | is   | Container set                                                |
| id                 | string                                                       | no   | Phase ID                                                     |
| stageControlOption | [StageControlOption](get-the-pipeline-orchestration.md)      | is   | Flow control options                                         |
| checkOut           | [StagePauseCheck](get-the-pipeline-orchestration.md)         | no   | Whether retries can be made at the current Stage             |
| fastKill           | boolean                                                      | no   | Whether to enable the container failure quick termination phase |

## StagePauseCheck

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| ruleIds        | List                                                         | no   | ruleIds               |
| reviewParams   | List< [Manual audit - Custom parameters](get-the-pipeline-orchestration.md) > | no   | reviewParams          |
| manualTrigger  | boolean                                                      | no   | manualTrigger         |
| checkTimes     | integer                                                      | no   | checkTimes            |
| reviewDesc     | string                                                       | no   | reviewDesc            |
| reviewGroups   | List<[Stage Audit group information](get-the-pipeline-orchestration.md) > | no   | reviewGroups          |
| timeout        | integer                                                      | no   | timeout               |
| status         | string                                                       | no   | status                |

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](get-the-pipeline-orchestration.md) > | no   | Drop-down list        |
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
| params         | List< [Manual audit - Custom parameters](get-the-pipeline-orchestration.md) > | no   | Audit incoming variables             |
| reviewers      | List                                                         | is   | auditor                              |
| operator       | string                                                       | no   | Audit operator                       |
| reviewTime     | integer                                                      | no   | Audit operation time                 |
| status         | string                                                       | no   | Audit results (enumeration)          |

## Pipeline Model - polymorphic base class

| Parameter name      | Parameter type                              | must | Parameter description |
| :------------------ | :------------------------------------------ | :--- | :-------------------- |
| canRetry            | boolean                                     | no   | canRetry              |
| elementElapsed      | integer                                     | no   | elementElapsed        |
| startEpoch          | integer                                     | no   | startEpoch            |
| executeCount        | integer                                     | no   | executeCount          |
| jobId               | string                                      | no   | jobId                 |
| containPostTaskFlag | boolean                                     | no   | containPostTaskFlag   |
| systemElapsed       | integer                                     | no   | systemElapsed         |
| elements            | List[ ](get-the-pipeline-orchestration.md)> | no   | elements              |
| name                | string                                      | no   | name                  |
| id                  | string                                      | no   | id                    |
| startVMStatus       | string                                      | no   | startVMStatus         |
| containerId         | string                                      | no   | containerId           |
| classType           | string                                      | no   | classType             |
| status              | string                                      | no   | status                |

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
| additionalOptions | [ElementAdditionalOptions](get-the-pipeline-orchestration.md) | no   | additionalOptions     |
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
| customVariables       | List<[NameAndValue](get-the-pipeline-orchestration.md)>      | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](get-the-pipeline-orchestration.md)>      | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](get-the-pipeline-orchestration.md)    | no   | elementPostInfo       |

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
| reviewParams    | List< [Manual audit - Custom parameters](get-the-pipeline-orchestration.md) > | no   | reviewParams          |
| manualTrigger   | boolean                                                      | no   | manualTrigger         |
| enable          | boolean                                                      | no   | enable                |
| customCondition | string                                                       | no   | customCondition       |
| triggerUsers    | List                                                         | no   | triggerUsers          |
| reviewDesc      | string                                                       | no   | reviewDesc            |
| runCondition    | ENUM(AFTER_LAST_FINISHED, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, ) | no   | runCondition          |
| timeout         | integer                                                      | no   | timeout               |
| customVariables | List<[NameAndValue](get-the-pipeline-orchestration.md)>      | no   | customVariables       |
