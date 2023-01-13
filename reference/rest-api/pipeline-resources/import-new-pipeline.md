# Import a new pipeline, including pipeline orchestration and Settings

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/pipeline_upload

### Resource description

#### Import a new pipeline, including pipeline orchestration and Settings

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description             | Default value |
| :------------- | :------------- | :--- | :-------------------------------- | :------------ |
| channelCode    | string         | no   | Channel number. The default is BS |               |

#### Body parameter

| Parameter name | Parameter type                                    | must | Parameter description    | Default value |
| :------------- | :------------------------------------------------ | :--- | :----------------------- | :------------ |
| body           | [PipelineModelAndSetting](import-new-pipeline.md) | is   | Pipeline model and setup |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model pipelining model-ID](import-new-pipeline.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "id" : "String"  },  "message" : "String",  "status" : 0 } 
```

## PipelineModelAndSetting

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| model          | [Pipeline model - Create information](import-new-pipeline.md) | is   | Pipeline model        |
| setting        | [PipelineSetting](import-new-pipeline.md)                    | no   | Pipeline setting      |

## Pipeline model - Create information

| Parameter name       | Parameter type                                         | must | Parameter description                         |
| :------------------- | :----------------------------------------------------- | :--- | :-------------------------------------------- |
| latestVersion        | integer                                                | no   | Latest version of pipeline at submission time |
| pipelineCreator      | string                                                 | no   | founder                                       |
| name                 | string                                                 | is   | name                                          |
| stages               | List< [pipeline model-phase](import-new-pipeline.md) > | is   | Stage set                                     |
| templateId           | string                                                 | no   | Template ID                                   |
| srcTemplateId        | string                                                 | no   | ID of the source template                     |
| tips                 | string                                                 | no   | prompt                                        |
| desc                 | string                                                 | no   | description                                   |
| labels               | List                                                   | no   | label                                         |
| instanceFromTemplate | boolean                                                | no   | Whether it is instantiated from the template  |

## Pipeline model - Phase

| Parameter name     | Parameter type                                               | must | Parameter description                                        |
| :----------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- |
| canRetry           | boolean                                                      | no   | Whether retries can be made at the current Stage             |
| checkIn            | [StagePauseCheck](import-new-pipeline.md)                    | no   | Whether retries can be made at the current Stage             |
| customBuildEnv     | object                                                       | no   | User-defined environment variables                           |
| finally            | boolean                                                      | no   | Identifies whether it is FinallyStage. Each Model can contain only one FinallyStage and is in the last position |
| name               | string                                                       | is   | Stage name                                                   |
| containers         | List< [pipeline model-polymorphic base class >](import-new-pipeline.md) | is   | Container set                                                |
| id                 | string                                                       | no   | Phase ID                                                     |
| stageControlOption | [StageControlOption](import-new-pipeline.md)                 | is   | Flow control options                                         |
| checkOut           | [StagePauseCheck](import-new-pipeline.md)                    | no   | Whether retries can be made at the current Stage             |
| fastKill           | boolean                                                      | no   | Whether to enable the container failure quick termination phase |

## StagePauseCheck

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| ruleIds        | List                                                         | no   | ruleIds               |
| reviewParams   | List< [Manual audit - Custom parameters](import-new-pipeline.md) > | no   | reviewParams          |
| manualTrigger  | boolean                                                      | no   | manualTrigger         |
| checkTimes     | integer                                                      | no   | checkTimes            |
| reviewDesc     | string                                                       | no   | reviewDesc            |
| reviewGroups   | List<[Stage Audit group information](import-new-pipeline.md) > | no   | reviewGroups          |
| timeout        | integer                                                      | no   | timeout               |
| status         | string                                                       | no   | status                |

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](import-new-pipeline.md) > | no   | Drop-down list        |
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
| params         | List< [Manual audit - Custom parameters](import-new-pipeline.md) > | no   | Audit incoming variables             |
| reviewers      | List                                                         | is   | auditor                              |
| operator       | string                                                       | no   | Audit operator                       |
| reviewTime     | integer                                                      | no   | Audit operation time                 |
| status         | string                                                       | no   | Audit results (enumeration)          |

## Pipeline Model - polymorphic base class

| Parameter name      | Parameter type                   | must | Parameter description |
| :------------------ | :------------------------------- | :--- | :-------------------- |
| canRetry            | boolean                          | no   | canRetry              |
| elementElapsed      | integer                          | no   | elementElapsed        |
| startEpoch          | integer                          | no   | startEpoch            |
| executeCount        | integer                          | no   | executeCount          |
| jobId               | string                           | no   | jobId                 |
| containPostTaskFlag | boolean                          | no   | containPostTaskFlag   |
| systemElapsed       | integer                          | no   | systemElapsed         |
| elements            | List[ ](import-new-pipeline.md)> | no   | elements              |
| name                | string                           | no   | name                  |
| id                  | string                           | no   | id                    |
| startVMStatus       | string                           | no   | startVMStatus         |
| containerId         | string                           | no   | containerId           |
| classType           | string                           | no   | classType             |
| status              | string                           | no   | status                |

## Element

| Parameter name    | Parameter type                                     | must | Parameter description |
| :---------------- | :------------------------------------------------- | :--- | :-------------------- |
| canRetry          | boolean                                            | no   | canRetry              |
| errorType         | string                                             | no   | errorType             |
| errorCode         | integer                                            | no   | errorCode             |
| canSkip           | boolean                                            | no   | canSkip               |
| startEpoch        | integer                                            | no   | startEpoch            |
| version           | string                                             | no   | version               |
| executeCount      | integer                                            | no   | executeCount          |
| templateModify    | boolean                                            | no   | templateModify        |
| elementEnable     | boolean                                            | no   | elementEnable         |
| errorMsg          | string                                             | no   | errorMsg              |
| elapsed           | integer                                            | no   | elapsed               |
| atomCode          | string                                             | no   | atomCode              |
| additionalOptions | [ElementAdditionalOptions](import-new-pipeline.md) | no   | additionalOptions     |
| taskAtom          | string                                             | no   | taskAtom              |
| name              | string                                             | no   | name                  |
| id                | string                                             | no   | id                    |
| classType         | string                                             | no   | classType             |
| status            | string                                             | no   | status                |

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
| customVariables       | List<[NameAndValue](import-new-pipeline.md)>                 | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](import-new-pipeline.md)>                 | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](import-new-pipeline.md)               | no   | elementPostInfo       |

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
| reviewParams    | List< [Manual audit - Custom parameters](import-new-pipeline.md) > | no   | reviewParams          |
| manualTrigger   | boolean                                                      | no   | manualTrigger         |
| enable          | boolean                                                      | no   | enable                |
| customCondition | string                                                       | no   | customCondition       |
| triggerUsers    | List                                                         | no   | triggerUsers          |
| reviewDesc      | string                                                       | no   | reviewDesc            |
| runCondition    | ENUM(AFTER_LAST_FINISHED, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, ) | no   | runCondition          |
| timeout         | integer                                                      | no   | timeout               |
| customVariables | List<[NameAndValue](import-new-pipeline.md)>                 | no   | customVariables       |

## PipelineSetting

| Parameter name         | Parameter type                                             | must | Parameter description  |
| :--------------------- | :--------------------------------------------------------- | :--- | :--------------------- |
| successSubscription    | [Settings - Subscribe to messages](import-new-pipeline.md) | no   | successSubscription    |
| runLockType            | ENUM(MULTIPLE, SINGLE, SINGLE_LOCK, LOCK, )                | no   | runLockType            |
| maxPipelineResNum      | integer                                                    | no   | maxPipelineResNum      |
| version                | integer                                                    | no   | version                |
| pipelineId             | string                                                     | no   | pipelineId             |
| labels                 | List                                                       | no   | labels                 |
| pipelineName           | string                                                     | no   | pipelineName           |
| maxConRunningQueueSize | integer                                                    | no   | maxConRunningQueueSize |
| maxQueueSize           | integer                                                    | no   | maxQueueSize           |
| hasPermission          | boolean                                                    | no   | hasPermission          |
| waitQueueTimeMinute    | integer                                                    | no   | waitQueueTimeMinute    |
| failSubscription       | [Settings - Subscribe to messages](import-new-pipeline.md) | no   | failSubscription       |
| buildNumRule           | string                                                     | no   | buildNumRule           |
| projectId              | string                                                     | no   | projectId              |
| desc                   | string                                                     | no   | desc                   |

## Settings - Subscribe to messages

| Parameter name          | Parameter type | must | Parameter description                                        |
| :---------------------- | :------------- | :--- | :----------------------------------------------------------- |
| types                   | List           | is   | Notification method (email, rtx)                             |
| wechatGroupMarkdownFlag | boolean        | no   | The enterprise wechat group notification is converted to Markdown format |
| groups                  | List           | no   | grouping                                                     |
| detailFlag              | boolean        | no   | Notification pipeline details connection switch              |
| users                   | string         | no   | Notifying officer                                            |
| wechatGroupFlag         | boolean        | no   | Enterprise wechat group notification switch                  |
| content                 | string         | no   | Customize notification content                               |
| wechatGroup             | string         | no   | Enterprise wechat group notification group ID                |

## The data is returned to the wrapper model pipelining model-ID

| Parameter name | Parameter type                               | must | Parameter description |
| :------------- | :------------------------------------------- | :--- | :-------------------- |
| data           | [Pipeline model -ID](import-new-pipeline.md) | no   | data                  |
| message        | string                                       | no   | Error message         |
| status         | integer                                      | is   | Status code           |

## Pipeline model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | is   | Pipeline ID           |
