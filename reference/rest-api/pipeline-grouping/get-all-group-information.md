# Gets all group information

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/pipelineGroups/groups

### Resource description

#### Gets all group information

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model ListPipelineGroup](get-all-group-information.md) |

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
{  "data" : [ {  "createTime" : 0,  "name" : "String",  "updateUser" : "String",  "updateTime" : 0,  "createUser" : "String",  "id" : "String",  "projectId" : "String",  "labels" : [ {  "createTime" : 0,  "groupId" : "String",  "name" : "String",  "updateUser" : "String",  "uptimeTime" : 0,  "createUser" : "String",  "id" : "String"  } ]  } ],  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model ListPipelineGroup

| Parameter name | Parameter type                                      | must | Parameter description |
| :------------- | :-------------------------------------------------- | :--- | :-------------------- |
| data           | List<[PipelineGroup](get-all-group-information.md)> | no   | data                  |
| message        | string                                              | no   | Error message         |
| status         | integer                                             | is   | Status code           |

## PipelineGroup

| Parameter name | Parameter type                                      | must | Parameter description |
| :------------- | :-------------------------------------------------- | :--- | :-------------------- |
| createTime     | integer                                             | no   | createTime            |
| name           | string                                              | no   | name                  |
| updateUser     | string                                              | no   | updateUser            |
| updateTime     | integer                                             | no   | updateTime            |
| createUser     | string                                              | no   | createUser            |
| id             | string                                              | no   | id                    |
| projectId      | string                                              | no   | projectId             |
| labels         | List<[PipelineLabel](get-all-group-information.md)> | no   | labels                |

## PipelineLabel

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| createTime     | integer        | no   | createTime            |
| groupId        | string         | no   | groupId               |
| name           | string         | no   | name                  |
| updateUser     | string         | no   | updateUser            |
| uptimeTime     | integer        | no   | uptimeTime            |
| createUser     | string         | no   | createUser            |
| id             | string         | no   | id                    |
