# callback Callback execution history

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/callbacks/history

### Resource description

#### callback Callback execution history

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description                    | Default value |
| :------------- | :------------- | :--- | :--------------------------------------- | :------------ |
| url            | string         | is   | Callback url                             |               |
| event          | string         | is   | Event type                               |               |
| startTime      | string         | no   | Start time (Format: yyyy-MM-dd HH:mm:ss) |               |
| endTime        | string         | no   | End Time (Format: yyyy-MM-dd HH:mm:ss)   |               |
| page           | integer        | no   | What page                                | 1             |
| pageSize       | integer        | no   | How many pieces per page                 | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Wrapper Model Page pipelined callback history of the data wrapper model project](callback-execution-history.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? url={url}&event={event}&startTime={startTime}&endTime={endTime}&page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "callBackUrl" : "String",  "responseBody" : "String",  "responseCode" : 0,  "errorMsg" : "String",  "requestHeaders" : [ {  "name" : "String",  "value" : "String"  } ],  "requestBody" : "String",  "createdTime" : 0,  "startTime" : 0,  "id" : 0,  "endTime" : 0,  "projectId" : "String",  "events" : "String",  "status" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper Model Page pipelined callback history of the data wrapper model project

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Pipeline callback history for the paging data wrapper model project](callback-execution-history.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Pipeline callback history for the paging data wrapper model project

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [pipeline callback history of the project](callback-execution-history.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Pipeline callback history of the project

| Parameter name | Parameter type                                        | must | Parameter description |
| :------------- | :---------------------------------------------------- | :--- | :-------------------- |
| callBackUrl    | string                                                | no   | callBackUrl           |
| responseBody   | string                                                | no   | responseBody          |
| responseCode   | integer                                               | no   | responseCode          |
| errorMsg       | string                                                | no   | errorMsg              |
| requestHeaders | List<[CallBackHeader](callback-execution-history.md)> | no   | requestHeaders        |
| requestBody    | string                                                | no   | requestBody           |
| createdTime    | integer                                               | no   | createdTime           |
| startTime      | integer                                               | no   | startTime             |
| id             | integer                                               | no   | id                    |
| endTime        | integer                                               | no   | endTime               |
| projectId      | string                                                | no   | projectId             |
| events         | string                                                | no   | events                |
| status         | string                                                | no   | status                |

## CallBackHeader

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| name           | string         | no   | name                  |
| value          | string         | no   | value                 |
