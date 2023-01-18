# Get pipeline template details

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/templates/{templateId}

### Resource description

#### Get pipeline template details

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| version        | integer        | no   | Template version      |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| templateId     | string         | is   | Template ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model TemplateModelDetail](get-the-details-of-the-pipeline-template.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? version={version}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "template" : {  "latestVersion" : 0,  "pipelineCreator" : "String",  "name" : "String",  "stages" : [ {  "canRetry" : true,  "checkIn" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "customBuildEnv" : {  "string" : "string"  },  "finally" : true,  "name" : "String",  "containers" : [ {  "canRetry" : true,  "elementElapsed" : 0,  "startEpoch" : 0,  "executeCount" : 0,  "jobId" : "String",  "containPostTaskFlag" : true,  "systemElapsed" : 0,  "elements" : [ {  "canRetry" : true,  "errorType" : "String",  "errorCode" : 0,  "canSkip" : true,  "startEpoch" : 0,  "version" : "String",  "executeCount" : 0,  "templateModify" : true,  "elementEnable" : true,  "errorMsg" : "String",  "elapsed" : 0,  "atomCode" : "String",  "additionalOptions" : {  "enableCustomEnv" : true,  "continueWhenFailed" : true,  "manualRetry" : true,  "pauseBeforeExec" : true,  "retryCount" : 0,  "manualSkip" : true,  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ],  "otherTask" : "String",  "customEnv" : [ {  "value" : "String",  "key" : "String"  } ],  "retryWhenFailed" : true,  "enable" : true,  "subscriptionPauseUser" : "String",  "customCondition" : "String",  "runCondition" : "ENUM",  "elementPostInfo" : {  "parentElementId" : "String",  "postCondition" : "String",  "parentElementJobIndex" : 0,  "parentElementName" : "String",  "postEntryParam" : "String"  }  },  "taskAtom" : "String",  "name" : "String",  "id" : "String",  "classType" : "String",  "status" : "String"  } ],  "name" : "String",  "id" : "String",  "startVMStatus" : "String",  "containerId" : "String",  "classType" : "String",  "status" : "String"  } ],  "id" : "String",  "stageControlOption" : {  "triggered" : true,  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "enable" : true,  "customCondition" : "String",  "triggerUsers" : "string",  "reviewDesc" : "String",  "runCondition" : "ENUM",  "timeout" : 0,  "customVariables" : [ {  "value" : "String",  "key" : "String"  } ]  },  "checkOut" : {  "ruleIds" : "string",  "reviewParams" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "manualTrigger" : true,  "checkTimes" : 0,  "reviewDesc" : "String",  "reviewGroups" : [ {  "name" : "String",  "id" : "String",  "suggest" : "String",  "params" : [ {  "valueType" : "ENUM",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "chineseName" : "String",  "value" : {  "string" : "string"  },  "key" : "String",  "required" : true,  "desc" : "String"  } ],  "reviewers" : "string",  "operator" : "String",  "reviewTime" : 0,  "status" : "String"  } ],  "timeout" : 0,  "status" : "String"  },  "fastKill" : true  } ],  "templateId" : "String",  "srcTemplateId" : "String",  "tips" : "String",  "desc" : "String",  "labels" : "string",  "instanceFromTemplate" : true  },  "templateType" : "String",  "creator" : "String",  "versions" : [ {  "creator" : "String",  "updateTime" : 0,  "versionName" : "String",  "version" : 0  } ],  "latestVersion" : {  "creator" : "String",  "updateTime" : 0,  "versionName" : "String",  "version" : 0  },  "templateName" : "String",  "hasPermission" : true,  "description" : "String",  "templateParams" : [ {  "defaultValue" : {  "string" : "string"  },  "containerType" : {  "os" : "ENUM",  "buildType" : "ENUM"  },  "glob" : "String",  "replaceKey" : "String",  "readOnly" : true,  "label" : "String",  "type" : "ENUM",  "required" : true,  "repoHashId" : "String",  "scmType" : "ENUM",  "relativePath" : "String",  "propertyType" : "String",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "searchUrl" : "String",  "id" : "String",  "placeholder" : "String",  "properties" : {  "string" : "string"  },  "desc" : "String"  } ],  "params" : [ {  "defaultValue" : {  "string" : "string"  },  "containerType" : {  "os" : "ENUM",  "buildType" : "ENUM"  },  "glob" : "String",  "replaceKey" : "String",  "readOnly" : true,  "label" : "String",  "type" : "ENUM",  "required" : true,  "repoHashId" : "String",  "scmType" : "ENUM",  "relativePath" : "String",  "propertyType" : "String",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "searchUrl" : "String",  "id" : "String",  "placeholder" : "String",  "properties" : {  "string" : "string"  },  "desc" : "String"  } ],  "currentVersion" : {  "creator" : "String",  "updateTime" : 0,  "versionName" : "String",  "version" : 0  },  "logoUrl" : "String"  },  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model TemplateModelDetail

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [TemplateModelDetail](get-the-details-of-the-pipeline-template.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## TemplateModelDetail

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| template       | [Pipeline model - Create information](get-the-details-of-the-pipeline-template.md) | no   | template              |
| templateType   | string                                                       | no   | templateType          |
| creator        | string                                                       | no   | creator               |
| versions       | List<[TemplateVersion](get-the-details-of-the-pipeline-template.md)> | no   | versions              |
| latestVersion  | [TemplateVersion](get-the-details-of-the-pipeline-template.md) | no   | latestVersion         |
| templateName   | string                                                       | no   | templateName          |
| hasPermission  | boolean                                                      | no   | hasPermission         |
| description    | string                                                       | no   | description           |
| templateParams | List< [Build Model-Form Element Attributes](get-the-details-of-the-pipeline-template.md) > | no   | templateParams        |
| params         | List< [Build Model-Form Element Attributes](get-the-details-of-the-pipeline-template.md) > | no   | params                |
| currentVersion | [TemplateVersion](get-the-details-of-the-pipeline-template.md) | no   | currentVersion        |
| logoUrl        | string                                                       | no   | logoUrl               |

## Pipeline model - Create information

| Parameter name       | Parameter type                                               | must | Parameter description                         |
| :------------------- | :----------------------------------------------------------- | :--- | :-------------------------------------------- |
| latestVersion        | integer                                                      | no   | Latest version of pipeline at submission time |
| pipelineCreator      | string                                                       | no   | founder                                       |
| name                 | string                                                       | is   | name                                          |
| stages               | List< [pipeline model-phase](get-the-details-of-the-pipeline-template.md) > | is   | Stage set                                     |
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
| checkIn            | [StagePauseCheck](get-the-details-of-the-pipeline-template.md) | no   | Whether retries can be made at the current Stage             |
| customBuildEnv     | object                                                       | no   | User-defined environment variables                           |
| finally            | boolean                                                      | no   | Identifies whether it is FinallyStage. Each Model can contain only one FinallyStage and is in the last position |
| name               | string                                                       | is   | Stage name                                                   |
| containers         | List< [pipeline model-polymorphic base class >](get-the-details-of-the-pipeline-template.md) | is   | Container set                                                |
| id                 | string                                                       | no   | Phase ID                                                     |
| stageControlOption | [StageControlOption](get-the-details-of-the-pipeline-template.md) | is   | Flow control options                                         |
| checkOut           | [StagePauseCheck](get-the-details-of-the-pipeline-template.md) | no   | Whether retries can be made at the current Stage             |
| fastKill           | boolean                                                      | no   | Whether to enable the container failure quick termination phase |

## StagePauseCheck

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| ruleIds        | List                                                         | no   | ruleIds               |
| reviewParams   | List< [Manual audit - Custom parameters](get-the-details-of-the-pipeline-template.md) > | no   | reviewParams          |
| manualTrigger  | boolean                                                      | no   | manualTrigger         |
| checkTimes     | integer                                                      | no   | checkTimes            |
| reviewDesc     | string                                                       | no   | reviewDesc            |
| reviewGroups   | List<[Stage Audit group information](get-the-details-of-the-pipeline-template.md) > | no   | reviewGroups          |
| timeout        | integer                                                      | no   | timeout               |
| status         | string                                                       | no   | status                |

## Manual audit - Customize parameters

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| valueType      | ENUM(STRING, TEXTAREA, BOOLEAN, ENUM, MULTIPLE, )            | no   | Parameter type        |
| options        | List< [Manual Review - Custom parameters - drop-down list Sword](get-the-details-of-the-pipeline-template.md) > | no   | Drop-down list        |
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
| params         | List< [Manual audit - Custom parameters](get-the-details-of-the-pipeline-template.md) > | no   | Audit incoming variables             |
| reviewers      | List                                                         | is   | auditor                              |
| operator       | string                                                       | no   | Audit operator                       |
| reviewTime     | integer                                                      | no   | Audit operation time                 |
| status         | string                                                       | no   | Audit results (enumeration)          |

## Pipeline Model - polymorphic base class

| Parameter name      | Parameter type                                        | must | Parameter description |
| :------------------ | :---------------------------------------------------- | :--- | :-------------------- |
| canRetry            | boolean                                               | no   | canRetry              |
| elementElapsed      | integer                                               | no   | elementElapsed        |
| startEpoch          | integer                                               | no   | startEpoch            |
| executeCount        | integer                                               | no   | executeCount          |
| jobId               | string                                                | no   | jobId                 |
| containPostTaskFlag | boolean                                               | no   | containPostTaskFlag   |
| systemElapsed       | integer                                               | no   | systemElapsed         |
| elements            | List[ ](get-the-details-of-the-pipeline-template.md)> | no   | elements              |
| name                | string                                                | no   | name                  |
| id                  | string                                                | no   | id                    |
| startVMStatus       | string                                                | no   | startVMStatus         |
| containerId         | string                                                | no   | containerId           |
| classType           | string                                                | no   | classType             |
| status              | string                                                | no   | status                |

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
| additionalOptions | [ElementAdditionalOptions](get-the-details-of-the-pipeline-template.md) | no   | additionalOptions     |
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
| customVariables       | List<[NameAndValue](get-the-details-of-the-pipeline-template.md)> | no   | customVariables       |
| otherTask             | string                                                       | no   | otherTask             |
| customEnv             | List<[NameAndValue](get-the-details-of-the-pipeline-template.md)> | no   | customEnv             |
| retryWhenFailed       | boolean                                                      | no   | retryWhenFailed       |
| enable                | boolean                                                      | no   | enable                |
| subscriptionPauseUser | string                                                       | no   | subscriptionPauseUser |
| customCondition       | string                                                       | no   | customCondition       |
| runCondition          | ENUM(PRE_TASK_SUCCESS, PRE_TASK_FAILED_BUT_CANCEL, PRE_TASK_FAILED_EVEN_CANCEL, PRE_TASK_FAILED_ONLY, OTHER_TASK_RUNNING, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, PARENT_TASK_CANCELED_OR_TIMEOUT, PARENT_TASK_FINISH, ) | no   | runCondition          |
| elementPostInfo       | [Element post message](get-the-details-of-the-pipeline-template.md) | no   | elementPostInfo       |

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
| reviewParams    | List< [Manual audit - Custom parameters](get-the-details-of-the-pipeline-template.md) > | no   | reviewParams          |
| manualTrigger   | boolean                                                      | no   | manualTrigger         |
| enable          | boolean                                                      | no   | enable                |
| customCondition | string                                                       | no   | customCondition       |
| triggerUsers    | List                                                         | no   | triggerUsers          |
| reviewDesc      | string                                                       | no   | reviewDesc            |
| runCondition    | ENUM(AFTER_LAST_FINISHED, CUSTOM_VARIABLE_MATCH, CUSTOM_VARIABLE_MATCH_NOT_RUN, CUSTOM_CONDITION_MATCH, ) | no   | runCondition          |
| timeout         | integer                                                      | no   | timeout               |
| customVariables | List<[NameAndValue](get-the-details-of-the-pipeline-template.md)> | no   | customVariables       |

## TemplateVersion

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| creator        | string         | no   | creator               |
| updateTime     | integer        | no   | updateTime            |
| versionName    | string         | no   | versionName           |
| version        | integer        | no   | version               |

## Build Model - Form element attributes

| Parameter name | Parameter type                                               | must | Parameter description                                        |
| :------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- |
| defaultValue   | object                                                       | is   | Default value                                                |
| containerType  | [BuildContainerType](get-the-details-of-the-pipeline-template.md) | no   | Builder type drop-down                                       |
| glob           | string                                                       | no   | Custom warehouse wildcards                                   |
| replaceKey     | string                                                       | no   | Replace the search keyword in the search url                 |
| readOnly       | boolean                                                      | no   | Whether to read only                                         |
| label          | string                                                       | no   | Element tag                                                  |
| type           | ENUM(STRING, TEXTAREA, ENUM, DATE, LONG, BOOLEAN, SVN_TAG, GIT_REF, MULTIPLE, CODE_LIB, CONTAINER_TYPE, ARTIFACTORY, SUB_PIPELINE, CUSTOM_FILE, PASSWORD, TEMPORARY, ) | is   | Element type                                                 |
| required       | boolean                                                      | is   | Whether it is necessary                                      |
| repoHashId     | string                                                       | no   | repoHashId                                                   |
| scmType        | ENUM(CODE_SVN, CODE_GIT, CODE_GITLAB, GITHUB, CODE_TGIT, )   | no   | Code base type drop-down                                     |
| relativePath   | string                                                       | no   | relativePath                                                 |
| propertyType   | string                                                       | no   | Element module                                               |
| options        | List< [Build Model-Dropdown form element Values](get-the-details-of-the-pipeline-template.md) > | no   | Drop-down list                                               |
| searchUrl      | string                                                       | no   | Search for the url. When it is a drop-down option, the list value is obtained from the url and not from Option |
| id             | string                                                       | is   | Element ID- Identifier                                       |
| placeholder    | string                                                       | no   | Element placeholder                                          |
| properties     | object                                                       | no   | File metadata                                                |
| desc           | string                                                       | no   | description                                                  |

## BuildContainerType

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| os             | ENUM(MACOS, WINDOWS, LINUX, )                                | no   | os                    |
| buildType      | ENUM(ESXi, MACOS, DOCKER, IDC, PUBLIC_DEVCLOUD, TSTACK, THIRD_PARTY_AGENT_ID, THIRD_PARTY_AGENT_ENV, THIRD_PARTY_PCG, THIRD_PARTY_DEVCLOUD, GIT_CI, AGENT_LESS, ) | no   | buildType             |

## Build Model - Drop down box form element values

| Parameter name | Parameter type | must | Parameter description            |
| :------------- | :------------- | :--- | :------------------------------- |
| value          | string         | is   | Element value Name - for display |
| key            | string         | is   | Element value ID- identifier     |
