# Gets a list of instances of the pipeline template

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/templates/{templateId}/templateInstances

### Resource description

#### Gets a list of instances of the pipeline template

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description    | Default value |
| :------------- | :------------- | :--- | :----------------------- | :------------ |
| page           | integer        | no   | What page                | 1             |
| pageSize       | integer        | no   | How many pieces per page | 30            |
| searchKey      | string         | no   | Name Search keyword      |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| templateId     | string         | is   | Template ID           |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data is returned to the packaging model TemplateInstancePage](get-the-list-of-instances-of-the-pipeline-template.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? page={page}&pageSize={pageSize}&searchKey={searchKey}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "instances" : [ {  "pipelineName" : "String",  "hasPermission" : true,  "updateTime" : 0,  "templateId" : "String",  "versionName" : "String",  "version" : 0,  "pipelineId" : "String",  "status" : "ENUM"  } ],  "latestVersion" : {  "creator" : "String",  "updateTime" : 0,  "versionName" : "String",  "version" : 0  },  "count" : 0,  "pageSize" : 0,  "page" : 0,  "templateId" : "String",  "projectId" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Data is returned to the packaging model TemplateInstancePage

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [TemplateInstancePage](get-the-list-of-instances-of-the-pipeline-template.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## TemplateInstancePage

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| instances      | List<[TemplatePipeline](get-the-list-of-instances-of-the-pipeline-template.md)> | no   | instances             |
| latestVersion  | [TemplateVersion](get-the-list-of-instances-of-the-pipeline-template.md) | no   | latestVersion         |
| count          | integer                                                      | no   | count                 |
| pageSize       | integer                                                      | no   | pageSize              |
| page           | integer                                                      | no   | page                  |
| templateId     | string                                                       | no   | templateId            |
| projectId      | string                                                       | no   | projectId             |

## TemplatePipeline

| Parameter name | Parameter type                            | must | Parameter description |
| :------------- | :---------------------------------------- | :--- | :-------------------- |
| pipelineName   | string                                    | no   | pipelineName          |
| hasPermission  | boolean                                   | no   | hasPermission         |
| updateTime     | integer                                   | no   | updateTime            |
| templateId     | string                                    | no   | templateId            |
| versionName    | string                                    | no   | versionName           |
| version        | integer                                   | no   | version               |
| pipelineId     | string                                    | no   | pipelineId            |
| status         | ENUM(PENDING_UPDATE, UPDATING, UPDATED, ) | no   | status                |

## TemplateVersion

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| creator        | string         | no   | creator               |
| updateTime     | integer        | no   | updateTime            |
| versionName    | string         | no   | versionName           |
| version        | integer        | no   | version               |
