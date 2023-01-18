# Gets pipeline manual startup parameters

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/manualStartupInfo

### Resource description

#### Gets pipeline manual startup parameters

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

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return packaging model build model - pipeline manual start information](obtain-the-manual-start-parameters-of-the-pipeline.md) |

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
{  "data" : {  "canManualStartup" : true,  "canElementSkip" : true,  "buildNo" : {  "buildNoType" : "ENUM",  "buildNo" : 0,  "required" : true  },  "properties" : [ {  "defaultValue" : {  "string" : "string"  },  "containerType" : {  "os" : "ENUM",  "buildType" : "ENUM"  },  "glob" : "String",  "replaceKey" : "String",  "readOnly" : true,  "label" : "String",  "type" : "ENUM",  "required" : true,  "repoHashId" : "String",  "scmType" : "ENUM",  "relativePath" : "String",  "propertyType" : "String",  "options" : [ {  "value" : "String",  "key" : "String"  } ],  "searchUrl" : "String",  "id" : "String",  "placeholder" : "String",  "properties" : {  "string" : "string"  },  "desc" : "String"  } ]  },  "message" : "String",  "status" : 0 } 
```

## Data return packaging model build model - pipeline manual start information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Build model - Pipeline manual startup information](obtain-the-manual-start-parameters-of-the-pipeline.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Build model - Pipeline manual startup information

| Parameter name   | Parameter type                                               | must | Parameter description              |
| :--------------- | :----------------------------------------------------------- | :--- | :--------------------------------- |
| canManualStartup | boolean                                                      | is   | Whether it can be manually started |
| canElementSkip   | boolean                                                      | is   | Whether plug-ins can be skipped    |
| buildNo          | [BuildNo](obtain-the-manual-start-parameters-of-the-pipeline.md) | is   | The specified build number         |
| properties       | List< [Build Model-Form Element Attributes](obtain-the-manual-start-parameters-of-the-pipeline.md) > | is   | Launch the list of form elements   |

## BuildNo

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| buildNoType    | ENUM(CONSISTENT, SUCCESS_BUILD_INCREMENT, EVERY_BUILD_INCREMENT, ) | no   | buildNoType           |
| buildNo        | integer                                                      | no   | buildNo               |
| required       | boolean                                                      | no   | required              |

## Build Model - Form element attributes

| Parameter name | Parameter type                                               | must | Parameter description                                        |
| :------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- |
| defaultValue   | object                                                       | is   | Default value                                                |
| containerType  | [BuildContainerType](obtain-the-manual-start-parameters-of-the-pipeline.md) | no   | Builder type drop-down                                       |
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
| options        | List< [Build Model-Dropdown form element Values](obtain-the-manual-start-parameters-of-the-pipeline.md) > | no   | Drop-down list                                               |
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
