# callback Indicates the callback list

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/callbacks

### Resource description

#### callback Indicates the callback list

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description    | Default value |
| :------------- | :------------- | :--- | :----------------------- | :------------ |
| page           | integer        | no   | What page                | 1             |
| pageSize       | integer        | no   | How many pieces per page | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Wrapper Model Paging pipelined callback configuration for a data wrapper model project](callback-list.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "callBackUrl" : "String",  "secretToken" : "String",  "id" : 0,  "projectId" : "String",  "events" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper Model Paging pipelined callback configuration for a data wrapper model project

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Pipelined callback configuration for the paging data wrapper model project](callback-list.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Pipelined callback configuration for the paging data wrapper model project

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [pipeline callback configuration for the project](callback-list.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Pipelined callback configuration for the project

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| callBackUrl    | string         | no   | callBackUrl           |
| secretToken    | string         | no   | secretToken           |
| id             | integer        | no   | id                    |
| projectId      | string         | no   | projectId             |
| events         | string         | no   | events                |
