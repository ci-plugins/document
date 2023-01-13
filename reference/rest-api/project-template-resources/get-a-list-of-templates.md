# Template Management - Get a list of templates

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/templates

### Resource description

#### Template Management - Get a list of templates

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description                       | Default value |
| :------------- | :------------- | :--- | :------------------------------------------ | :------------ |
| templateType   | string         | no   | Template type                               |               |
| storeFlag      | boolean        | no   | Whether it has been associated with a store |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the TemplateListModel](get-a-list-of-templates.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? templateType={templateType}&storeFlag={storeFlag}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "models" : [ {  "templateType" : "String",  "associatePipelines" : [ {  "id" : "String"  } ],  "hasPermission" : true,  "name" : "String",  "templateTypeDesc" : "String",  "templateId" : "String",  "versionName" : "String",  "version" : 0,  "hasInstance2Upgrade" : true,  "logoUrl" : "String",  "storeFlag" : true,  "associateCodes" : "string"  } ],  "hasPermission" : true,  "count" : 0,  "projectId" : "String"  },  "message" : "String",  "status" : 0 } 
```

## The data is returned to the TemplateListModel

| Parameter name | Parameter type                                  | must | Parameter description |
| :------------- | :---------------------------------------------- | :--- | :-------------------- |
| data           | [TemplateListModel](get-a-list-of-templates.md) | no   | data                  |
| message        | string                                          | no   | Error message         |
| status         | integer                                         | is   | Status code           |

## TemplateListModel

| Parameter name | Parameter type                                    | must | Parameter description |
| :------------- | :------------------------------------------------ | :--- | :-------------------- |
| models         | List<[TemplateModel](get-a-list-of-templates.md)> | no   | models                |
| hasPermission  | boolean                                           | no   | hasPermission         |
| count          | integer                                           | no   | count                 |
| projectId      | string                                            | no   | projectId             |

## TemplateModel

| Parameter name      | Parameter type                                          | must | Parameter description                                  |
| :------------------ | :------------------------------------------------------ | :--- | :----------------------------------------------------- |
| templateType        | string                                                  | is   | Template type                                          |
| associatePipelines  | List< [pipeline model-id](get-a-list-of-templates.md) > | is   | Associated pipeline                                    |
| hasPermission       | boolean                                                 | is   | Whether the template operation permission is available |
| name                | string                                                  | is   | Template name                                          |
| templateTypeDesc    | string                                                  | is   | Template type description                              |
| templateId          | string                                                  | is   | Template ID                                            |
| versionName         | string                                                  | is   | Latest version number                                  |
| version             | integer                                                 | is   | Version ID                                             |
| hasInstance2Upgrade | boolean                                                 | is   | Whether there are updatable instances                  |
| logoUrl             | string                                                  | is   | Template logo                                          |
| storeFlag           | boolean                                                 | is   | Whether it is relevant to the market                   |
| associateCodes      | List                                                    | is   | Associated code base                                   |

## Pipeline model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| id             | string         | is   | Pipeline ID           |
