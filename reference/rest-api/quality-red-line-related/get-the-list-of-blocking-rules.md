# Gets a list of intercept rules

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/quality/rules/list

### Resource description

#### Gets a list of intercept rules

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| page           | integer        | no   | Page entry            | 1             |
| pageSize       | integer        | no   | Number per page       | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Packaging Model Page Data Packaging Model Quality Red Line - Rule Brief Information v2](get-the-list-of-blocking-rules.md) |

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
{  "data" : {  "records" : [ {  "pipelineCount" : 0,  "pipelineExecuteCount" : 0,  "indicatorList" : [ {  "cnName" : "String",  "name" : "String",  "threshold" : "String",  "hashId" : "String",  "operation" : "String"  } ],  "enable" : true,  "permissions" : {  "canEnable" : true,  "canEdit" : true,  "canDelete" : true  },  "name" : "String",  "range" : "ENUM",  "rangeSummary" : [ {  "lackElements" : "string",  "name" : "String",  "id" : "String",  "type" : "String"  } ],  "interceptTimes" : 0,  "ruleHashId" : "String",  "controlPoint" : {  "cnName" : "String",  "name" : "String",  "hashId" : "String"  },  "gatewayId" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Packaging Model Page Data Packaging Model Quality Red Line - Rule Brief Information v2

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Paging Data Wrapper Model Quality Red Line - Rule Brief v2](get-the-list-of-blocking-rules.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging Data Wrapper Model Quality Red Line - Rule Brief v2

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [Quality Red Line - Rule summary v2](get-the-list-of-blocking-rules.md)> | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Quality Red Line - Rule Brief v2

| Parameter name       | Parameter type                                               | must | Parameter description                                   |
| :------------------- | :----------------------------------------------------------- | :--- | :------------------------------------------------------ |
| pipelineCount        | integer                                                      | is   | Number of pipeline                                      |
| pipelineExecuteCount | integer                                                      | is   | Number of pipeline executions in effect                 |
| indicatorList        | List<[RuleSummaryIndicator](get-the-list-of-blocking-rules.md)> | is   | Index list                                              |
| enable               | boolean                                                      | is   | Enable or not                                           |
| permissions          | [Quality Red Line - Rule authority](get-the-list-of-blocking-rules.md) | is   | Rule authority                                          |
| name                 | string                                                       | is   | Rule name                                               |
| range                | ENUM(ANY, PART_BY_TAG, PART_BY_NAME, )                       | is   | Effective scope                                         |
| rangeSummary         | List<[RuleRangeSummary](get-the-list-of-blocking-rules.md)>  | is   | Includes templates and pipelining effective scope (new) |
| interceptTimes       | integer                                                      | is   | Number of interceptions                                 |
| ruleHashId           | string                                                       | is   | Rule HashId                                             |
| controlPoint         | [RuleSummaryControlPoint](get-the-list-of-blocking-rules.md) | is   | Control point                                           |
| gatewayId            | string                                                       | is   | Red line ID                                             |

## RuleSummaryIndicator

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| cnName         | string         | no   | cnName                |
| name           | string         | no   | name                  |
| threshold      | string         | no   | threshold             |
| hashId         | string         | no   | hashId                |
| operation      | string         | no   | operation             |

## Quality Red Line - Rule authority

| Parameter name | Parameter type | must | Parameter description              |
| :------------- | :------------- | :--- | :--------------------------------- |
| canEnable      | boolean        | is   | Whether it can be disabled/enabled |
| canEdit        | boolean        | is   | Editable or not                    |
| canDelete      | boolean        | is   | Whether it can be deleted          |

## RuleRangeSummary

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| lackElements   | List           | no   | lackElements          |
| name           | string         | no   | name                  |
| id             | string         | no   | id                    |
| type           | string         | no   | type                  |

## RuleSummaryControlPoint

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| cnName         | string         | no   | cnName                |
| name           | string         | no   | name                  |
| hashId         | string         | no   | hashId                |
