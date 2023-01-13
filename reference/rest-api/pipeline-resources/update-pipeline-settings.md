# Update pipeline setup

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/setting_update

### Resource description

#### Update pipeline setup

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                 | must | Parameter description | Default value |
| :------------- | :--------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [PipelineSetting](update-pipeline-settings.md) | is   | Pipeline setting      |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](update-pipeline-settings.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## PipelineSetting

| Parameter name         | Parameter type                                               | must | Parameter description  |
| :--------------------- | :----------------------------------------------------------- | :--- | :--------------------- |
| successSubscription    | [Settings - Subscribe to messages](update-pipeline-settings.md) | no   | successSubscription    |
| runLockType            | ENUM(MULTIPLE, SINGLE, SINGLE_LOCK, LOCK, )                  | no   | runLockType            |
| maxPipelineResNum      | integer                                                      | no   | maxPipelineResNum      |
| version                | integer                                                      | no   | version                |
| pipelineId             | string                                                       | no   | pipelineId             |
| labels                 | List                                                         | no   | labels                 |
| pipelineName           | string                                                       | no   | pipelineName           |
| maxConRunningQueueSize | integer                                                      | no   | maxConRunningQueueSize |
| maxQueueSize           | integer                                                      | no   | maxQueueSize           |
| hasPermission          | boolean                                                      | no   | hasPermission          |
| waitQueueTimeMinute    | integer                                                      | no   | waitQueueTimeMinute    |
| failSubscription       | [Settings - Subscribe to messages](update-pipeline-settings.md) | no   | failSubscription       |
| buildNumRule           | string                                                       | no   | buildNumRule           |
| projectId              | string                                                       | no   | projectId              |
| desc                   | string                                                       | no   | desc                   |

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

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
