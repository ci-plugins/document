# Batch instantiate pipelined templates

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/templates/{templateId}/templateInstances

### Resource description

#### Batch instantiate pipelined templates

### Input parameter description

#### Query parameter

| Parameter name      | Parameter type | must | Parameter description              | Default value |
| :------------------ | :------------- | :--- | :--------------------------------- | :------------ |
| version             | integer        | is   | Template version                   |               |
| useTemplateSettings | boolean        | no   | Whether to apply template Settings |               |

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | array<[TemplateInstanceCreate](batch-instantiation-pipeline-template.md)> | is   | Create an instance    |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| templateId     | string         | is   | Template ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [TemplateOperationRet](batch-instantiation-pipeline-template.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? version={version}&useTemplateSettings={useTemplateSettings}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "failurePipelines" : "string",  "failureMessages" : {  "string" : "string"  },  "successPipelinesId" : "string",  "successPipelines" : "string"  },  "message" : "String",  "status" : 0 } 
```

## TemplateInstanceCreate

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| pipelineName   | string                                                       | no   | pipelineName          |
| param          | List< [Build Model-Form Element Attributes](batch-instantiation-pipeline-template.md) > | no   | param                 |
| buildNo        | [BuildNo](batch-instantiation-pipeline-template.md)          | no   | buildNo               |

## Build Model - Form element attributes

| Parameter name | Parameter type                                               | must | Parameter description                                        |
| :------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- |
| defaultValue   | object                                                       | is   | Default value                                                |
| containerType  | [BuildContainerType](batch-instantiation-pipeline-template.md) | no   | Builder type drop-down                                       |
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
| options        | List< [Build Model-Dropdown form element Values](batch-instantiation-pipeline-template.md) > | no   | Drop-down list                                               |
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

## BuildNo

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| buildNoType    | ENUM(CONSISTENT, SUCCESS_BUILD_INCREMENT, EVERY_BUILD_INCREMENT, ) | no   | buildNoType           |
| buildNo        | integer                                                      | no   | buildNo               |
| required       | boolean                                                      | no   | required              |

## TemplateOperationRet

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [TemplateOperationMessage](batch-instantiation-pipeline-template.md) | no   | data                  |
| message        | string                                                       | no   | message               |
| status         | integer                                                      | no   | status                |

## TemplateOperationMessage

| Parameter name     | Parameter type | must | Parameter description |
| :----------------- | :------------- | :--- | :-------------------- |
| failurePipelines   | List           | no   | failurePipelines      |
| failureMessages    | object         | no   | failureMessages       |
| successPipelinesId | List           | no   | successPipelinesId    |
| successPipelines   | List           | no   | successPipelines      |
