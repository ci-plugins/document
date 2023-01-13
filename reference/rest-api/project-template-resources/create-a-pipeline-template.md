# Create pipeline template

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/templates

### Resource description

#### Create pipeline template

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Pipeline model - Create information](create-a-pipeline-template.md) | is   | template              |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data returns the wrapper model TemplateId](create-a-pipeline-template.md) |

#### Request sample

```
curl -X POST '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "id" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Pipeline model - Create information

| Parameter name       | Parameter type                                               | must | Parameter description                         |
| :------------------- | :----------------------------------------------------------- | :--- | :-------------------------------------------- |
| latestVersion        | integer                                                      | no   | Latest version of pipeline at submission time |
| pipelineCreator      | string                                                       | no   | founder                                       |
| name                 | string                                                       | is   | name                                          |
| stages               | List< [pipeline model-phase](create-a-pipeline-template.md) > | is   | Stage set                                     |
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
| checkIn            | [StagePauseCheck](create-a-pipeline-template.md)             | no   | Whether retries can be made at the current Stage             |
| customBuildEnv     | object                                                       | no   | User-defined environment variables                           |
| finally            | boolean                                                      | no   | Identifies whether it is FinallyStage. Each Model can contain only one FinallyStage and is in the last position |
| name               | string                                                       | is   | Stage name                                                   |
| containers         | List< [pipeline model-polymorphic base class >](create-a-pipeline-template.md) | is   | Container set                                                |
| id                 | string                                                       | no   | Phase ID                                                     |
| stageControlOption | [StageControlOption](create-a-pipeline-template.md)          | is   | Flow control options                                         |
| checkOut           | [StagePauseCheck](create-a-pipeline-template.md)             | no   | Whether retries can be made at the current Stage             |
| fastKill           | boolean                                                      | no   | Whether to enable the container failure quick termination phase |

## StagePauseCheck

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| ruleIds        | List                                                         | no   | ruleIds               |
| reviewParams   | List< [Manual audit - Custom parameters](create-a-pipeline-template.md) > | no   | reviewParams          |
| manualTrigger  | boolean                                                      | no   | manualTrigger         |
| checkTimes     | integer                                                      | no   | checkTimes            |
| reviewDesc     | string                                                       | no   | reviewDesc            |
| reviewGroups   | List<[Stage Audit group information](create-a-pipeline-template.md) > | no   | reviewGroups          |
| timeout        | integer                                                      | no   | timeout               |
| status         | string                                                       | no   | status                |

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](create-a-pipeline-template.md) > | no   | Drop-down list        |
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
| params         | List< [Manual audit - Custom parameters](create-a-pipeline-template.md) > | no   | Audit incoming variables             |
| reviewers      | List                                                         | is   | auditor                              |
| operator       | string                                                       | no   | Audit operator                       |
| reviewTime     | integer                                                      | no   | Audit operation time                 |
| status         | string                                                       | no   | Audit results (enumeration)          |

## Pipeline Model - polymorphic base class

| Parameter name      | Parameter type                          | must | Parameter description |
| :------------------ | :-------------------------------------- | :--- | :-------------------- |
| canRetry            | boolean                                 | no   | canRetry              |
| elementElapsed      | integer                                 | no   | elementElapsed        |
| startEpoch          | integer                                 | no   | startEpoch            |
| executeCount        | integer                                 | no   | executeCount          |
| jobId               | string                                  | no   | jobId                 |
| containPostTaskFlag | boolean                                 | no   | containPostTaskFlag   |
| systemElapsed       | integer                                 | no   | systemElapsed         |
| elements            | List[ ](create-a-pipeline-template.md)> | no   | elements              |
| name                | string                                  | no   | name                  |
| id                  | string                                  | no   | id                    |
| startVMStatus       | string                                  | no   | startVMStatus         |
| containerId         | string                                  | no   | containerId           |
| classType           | string                                  | no   | classType             |
| status              | string                                  | no   | status                |

## Element

| Parameter name    | Parameter type                                            | must | Parameter description |
| :---------------- | :-------------------------------------------------------- | :--- | :-------------------- |
| canRetry          | boolean                                                   | no   | canRetry              |
| errorType         | string                                                    | no   | errorType             |
| errorCode         | integer                                                   | no   | errorCode             |
| canSkip           | boolean                                                   | no   | canSkip               |
| startEpoch        | integer                                                   | no   | startEpoch            |
| version           | string                                                    | no   | version               |
| executeCount      | integer                                                   | no   | executeCount          |
| templateModify    | boolean                                                   | no   | templateModify        |
| elementEnable     | boolean                                                   | no   | elementEnable         |
| errorMsg          | string                                                    | no   | errorMsg              |
| elapsed           | integer                                                   | no   | elapsed               |
| atomCode          | string                                                    | no   | atomCode              |
| additionalOptions | [ElementAdditionalOptions](create-a-pipeline-template.md) | no   | additionalOptions     |
| taskAtom          | string                                                    | no   | taskAtom              |
| name              | string                                                    | no   | name                  |
| id                | string                                                    | no   | id                    |
| classType         | string                                                    | no   | classType             |
| status            | string                                                    | no   | status                |

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
| customVariables       | List<[NameAndValue](create-a-pipeline-template.md)>          | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](create-a-pipeline-template.md)>          | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](create-a-pipeline-template.md)        | no   | elementPostInfo       |

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
| reviewParams    | List< [Manual audit - Custom parameters](create-a-pipeline-template.md) > | no   | reviewParams          |
| manualTrigger   | boolean                                                      | no   | manualTrigger         |
| enable          | boolean                                                      | no   | enable                |
| customCondition | string                                                       | no   | customCondition       |
| triggerUsers    | List                                                         | no   | triggerUsers          |
| reviewDesc      | string                                                       | no   | reviewDesc            |
| runCondition    | ENUM(AFTER_LAST_FINISHED, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, ) | no   | runCondition          |
| timeout         | integer                                                      | no   | timeout               |
| customVariables | List<[NameAndValue](create-a-pipeline-template.md)>          | no   | customVariables       |

## The data returns the wrapper model TemplateId

| Parameter name | Parameter type                              | must | Parameter description |
| :------------- | :------------------------------------------ | :--- | :-------------------- |
| data           | [TemplateId](create-a-pipeline-template.md) | no   | data                  |
| message        | string                                      | no   | Error message         |
| status         | integer                                     | is   | Status code           |

## TemplateId

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | no   | id                    |
