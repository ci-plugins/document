# Operation pause plug-in

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/execute/pause

### Resource description

#### Operation pause plug-in

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Pipelining pauses the operation entity class](operation-pause-plugin.md) | no   |                       |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](operation-pause-plugin.md) |

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
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Pipelining pauses the operation entity class

| Parameter name | Parameter type                       | must | Parameter description                                        |
| :------------- | :----------------------------------- | :--- | :----------------------------------------------------------- |
| continue       | boolean                              | no   | continue                                                     |
| containerId    | string                               | no   | Id of the current containerport                              |
| taskId         | string                               | no   | Task ID                                                      |
| element        | [Element](operation-pause-plugin.md) | no   | element information. If there are variable changes in the plug-in, the changed element should be given |
| stageId        | string                               | no   | Current stageId                                              |

## Element

| Parameter name    | Parameter type                                        | must | Parameter description |
| :---------------- | :---------------------------------------------------- | :--- | :-------------------- |
| canRetry          | boolean                                               | no   | canRetry              |
| errorType         | string                                                | no   | errorType             |
| errorCode         | integer                                               | no   | errorCode             |
| canSkip           | boolean                                               | no   | canSkip               |
| startEpoch        | integer                                               | no   | startEpoch            |
| version           | string                                                | no   | version               |
| executeCount      | integer                                               | no   | executeCount          |
| templateModify    | boolean                                               | no   | templateModify        |
| elementEnable     | boolean                                               | no   | elementEnable         |
| errorMsg          | string                                                | no   | errorMsg              |
| elapsed           | integer                                               | no   | elapsed               |
| atomCode          | string                                                | no   | atomCode              |
| additionalOptions | [ElementAdditionalOptions](operation-pause-plugin.md) | no   | additionalOptions     |
| taskAtom          | string                                                | no   | taskAtom              |
| name              | string                                                | no   | name                  |
| id                | string                                                | no   | id                    |
| classType         | string                                                | no   | classType             |
| status            | string                                                | no   | status                |

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
| customVariables       | List<[NameAndValue](operation-pause-plugin.md)>              | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](operation-pause-plugin.md)>              | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](operation-pause-plugin.md)            | no   | elementPostInfo       |

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

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
