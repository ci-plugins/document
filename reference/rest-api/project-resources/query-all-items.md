# Query all items

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects

### Resource description

#### Query all items

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
|                |                |      |                       |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data returns wrapper model List item - Display model](query-all-items.md) |

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
{  "result" : true,  "code" : 0,  "data" : [ {  "deptName" : "String",  "englishName" : "String",  "projectType" : 0,  "description" : "String",  "remark" : "String",  "project_name" : "String",  "deployType" : "String",  "enabled" : true,  "createdAt" : "String",  "helmChartEnabled" : true,  "gray" : true,  "dataId" : 0,  "secrecy" : true,  "projectCode" : "String",  "project_id" : "String",  "useBk" : true,  "enableExternal" : true,  "extra" : "String",  "routerTag" : "String",  "id" : 0,  "ccAppId" : 0,  "updatedAt" : "String",  "approvalStatus" : 0,  "approver" : "String",  "pipelineLimit" : 0,  "centerId" : "String",  "ccAppName" : "String",  "creator" : "String",  "kind" : 0,  "cc_app_id" : 0,  "deptId" : "String",  "approvalTime" : "String",  "project_code" : "String",  "relationId" : "String",  "logoAddr" : "String",  "bgId" : "String",  "offlined" : true,  "hybridCcAppId" : 0,  "bgName" : "String",  "projectName" : "String",  "enableIdc" : true,  "projectId" : "String",  "cc_app_name" : "String",  "hybrid_cc_app_id" : 0,  "centerName" : "String"  } ],  "requestId" : "String",  "message" : "String" } 
```

## Data returns wrapper model List item - Display model

| Parameter name | Parameter type                                    | must | Parameter description |
| :------------- | :------------------------------------------------ | :--- | :-------------------- |
| result         | boolean                                           | no   | Request result        |
| code           | integer                                           | is   | Status code           |
| data           | List< [items-display model](query-all-items.md) > | no   | data                  |
| requestId      | string                                            | no   | Request ID            |
| message        | string                                            | no   | Error message         |

## Project - Display model

| Parameter name   | Parameter type | must | Parameter description                                        |
| :--------------- | :------------- | :--- | :----------------------------------------------------------- |
| deptName         | string         | no   | Department name                                              |
| englishName      | string         | no   | English abbreviation                                         |
| projectType      | integer        | no   | Item type                                                    |
| description      | string         | no   | description                                                  |
| remark           | string         | no   | comment                                                      |
| project_name     | string         | no   | Old project name (soon to be invalid, use projectName instead of old field names that are referenced in compatible plug-ins) |
| deployType       | string         | no   | Deployment type                                              |
| enabled          | boolean        | no   | enable                                                       |
| createdAt        | string         | no   | Creation time                                                |
| helmChartEnabled | boolean        | no   | Whether to enable chart activation                           |
| gray             | boolean        | no   | Grayscale or not                                             |
| dataId           | integer        | no   | Data ID                                                      |
| secrecy          | boolean        | no   | Confidentiality or not                                       |
| projectCode      | string         | no   | Project code                                                 |
| project_id       | string         | no   | Project ID(to be deprecated, use projectId instead of the old field being referenced in compatible plug-ins) |
| useBk            | boolean        | no   | useBK                                                        |
| enableExternal   | boolean        | no   | The builder can access the Internet                          |
| extra            | string         | no   | extra                                                        |
| routerTag        | string         | no   | Item route pointing                                          |
| id               | integer        | no   | Primary key ID                                               |
| ccAppId          | integer        | no   | cc service ID                                                |
| updatedAt        | string         | no   | Modification time                                            |
| approvalStatus   | integer        | no   | Approval status                                              |
| approver         | string         | no   | approver                                                     |
| pipelineLimit    | integer        | no   | Upper limit of pipeline quantity                             |
| centerId         | string         | no   | Center ID                                                    |
| ccAppName        | string         | no   | cc business name                                             |
| creator          | string         | no   | founder                                                      |
| kind             | integer        | no   | kind                                                         |
| cc_app_id        | integer        | no   | Old cc service ID(soon to be obsolete, the old field name referenced in the compatible plug-in, please use ccAppId instead) |
| deptId           | string         | no   | Department ID                                                |
| approvalTime     | string         | no   | Approval time                                                |
| project_code     | string         | no   | Old project code (soon to be obsolete, use projectCode instead of old field names that are referenced in compatible plug-ins) |
| relationId       | string         | no   | Associated system Id                                         |
| logoAddr         | string         | no   | logo address                                                 |
| bgId             | string         | no   | Business group ID                                            |
| offlined         | boolean        | no   | Offline or not                                               |
| hybridCcAppId    | integer        | no   | ID of the hybrid cloud CC service                            |
| bgName           | string         | no   | Business group name                                          |
| projectName      | string         | no   | Project name                                                 |
| enableIdc        | boolean        | no   | Supports the IDC builder                                     |
| projectId        | string         | no   | Item ID                                                      |
| cc_app_name      | string         | no   | Old cc business name (soon to be invalid, please use ccAppName instead of old field name referenced in compatible plug-in) |
| hybrid_cc_app_id | integer        | no   | Hybrid cloud CC business ID(to be obsolete, the old fields referenced in compatible plug-ins are named, please use hybridCcAppId instead) |
| centerName       | string         | no   | Center name                                                  |
