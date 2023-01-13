# Gets a list of all kinds of pipeline templates

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/templates/allTemplates

### Resource description

#### Gets a list of all kinds of pipeline templates

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data returns the wrapper model OptionalTemplateList](get-a-list-of-all-kinds-of-pipeline-templates.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "templates" : {  "string" : "string"  },  "count" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## The data returns the wrapper model OptionalTemplateList

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [OptionalTemplateList](get-a-list-of-all-kinds-of-pipeline-templates.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## OptionalTemplateList

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| templates      | object         | no   | templates             |
| count          | integer        | no   | count                 |
| pageSize       | integer        | no   | pageSize              |
| page           | integer        | no   | page                  |
