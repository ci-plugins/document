# Obtain intercept record

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/quality/intercepts/list

### Resource description

#### Obtain intercept record

### Input parameter description

#### Query parameter

| Parameter name  | Parameter type | must | Parameter description | Default value |
| :-------------- | :------------- | :--- | :-------------------- | :------------ |
| pipelineId      | string         | no   | Pipeline ID           |               |
| ruleHashId      | string         | no   | Rule ID               |               |
| interceptResult | string         | no   | state                 |               |
| startTime       | integer        | no   | Start time            |               |
| endTime         | integer        | no   | Cut-off time          |               |
| page            | integer        | no   | Page number           | 1             |
| pageSize        | integer        | no   | Number of pages       | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Wrapper Model paging Data Wrapper model Quality Red Line - Intercept record](obtain-interception-records.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? pipelineId={pipelineId}&ruleHashId={ruleHashId}&interceptResult={interceptResult}&startTime={startTime}&endTime={endTime }&page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "checkTimes" : 0,  "num" : 0,  "buildId" : "String",  "remark" : "String",  "buildNo" : "String",  "hashId" : "String",  "pipelineId" : "String",  "pipelineName" : "String",  "pipelineIsDelete" : true,  "interceptList" : [ {  "indicatorId" : "String",  "indicatorName" : "String",  "indicatorType" : "String",  "pass" : true,  "actualValue" : "String",  "logPrompt" : "String",  "detail" : "String",  "operation" : "ENUM",  "value" : "String",  "controlPoint" : "String"  } ],  "interceptResult" : "ENUM",  "ruleName" : "String",  "ruleHashId" : "String",  "timestamp" : 0  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper Model paging Data Wrapper model Quality Red Line - Intercept record

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Paging data wrapper model Quality Red Line - Intercept record](obtain-interception-records.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging data wrapper model Quality Red Line - Intercept record

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [mass red line - intercept record](obtain-interception-records.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Mass red line. - Intercept log

| Parameter name   | Parameter type                                               | must | Parameter description                 |
| :--------------- | :----------------------------------------------------------- | :--- | :------------------------------------ |
| checkTimes       | integer                                                      | is   | Number of checks                      |
| num              | integer                                                      | is   | The serial number in the project      |
| buildId          | string                                                       | is   | Build ID                              |
| remark           | string                                                       | is   | description                           |
| buildNo          | string                                                       | is   | Build number                          |
| hashId           | string                                                       | is   | hashId                                |
| pipelineId       | string                                                       | is   | Pipeline ID                           |
| pipelineName     | string                                                       | is   | Pipeline name                         |
| pipelineIsDelete | boolean                                                      | is   | Whether the pipeline has been deleted |
| interceptList    | List< [Mass red line - intercept rule intercept record](obtain-interception-records.md) > | is   | Description list                      |
| interceptResult  | ENUM(PASS, FAIL, )                                           | is   | Intercept result                      |
| ruleName         | string                                                       | is   | Rule name                             |
| ruleHashId       | string                                                       | is   | Rule HashId                           |
| timestamp        | integer                                                      | is   | Timestamp (seconds)                   |

## Mass Red Line - Intercept rule intercept record

| Parameter name | Parameter type             | must | Parameter description              |
| :------------- | :------------------------- | :--- | :--------------------------------- |
| indicatorId    | string                     | is   | Indicator ID                       |
| indicatorName  | string                     | is   | Index name                         |
| indicatorType  | string                     | no   | Indicator plug-in type             |
| pass           | boolean                    | is   | Pass or not                        |
| actualValue    | string                     | is   | Actual value                       |
| logPrompt      | string                     | no   | Details about indicator log output |
| detail         | string                     | is   | Indicator details                  |
| operation      | ENUM(GT, GE, LT, LE, EQ, ) | is   | relationship                       |
| value          | string                     | is   | Threshold value                    |
| controlPoint   | string                     | is   | Control point                      |
