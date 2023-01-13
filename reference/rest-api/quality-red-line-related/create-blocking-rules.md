# Create an interception rule

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/quality/rules/create

### Resource description

#### Create an interception rule

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                    | must | Parameter description | Default value |
| :------------- | :------------------------------------------------ | :--- | :-------------------- | :------------ |
| body           | [Rule creation request](create-blocking-rules.md) | is   | Rule content          |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model String](create-blocking-rules.md) |

#### Request sample

```
curl -X POST '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : "String",  "message" : "String",  "status" : 0 } 
```

## Rule creation request

| Parameter name       | Parameter type                                           | must | Parameter description                   |
| :------------------- | :------------------------------------------------------- | :--- | :-------------------------------------- |
| templateRange        | List                                                     | is   | Set of pipelined template ids in effect |
| auditUserList        | List                                                     | no   | Audit notification personnel            |
| range                | List                                                     | is   | Set of pipeline ids in effect           |
| auditTimeoutMinutes  | integer                                                  | no   | Audit timeout                           |
| notifyTypeList       | List                                                     | no   | Notification type                       |
| notifyUserList       | List                                                     | no   | Notifier list                           |
| controlPointPosition | string                                                   | is   | Control point position                  |
| name                 | string                                                   | is   | Rule name                               |
| notifyGroupList      | List                                                     | no   | Notification group list                 |
| operation            | ENUM(END, AUDIT, )                                       | is   | Type of operation                       |
| indicatorIds         | List<[CreateRequestIndicator](create-blocking-rules.md)> | is   | Index type                              |
| controlPoint         | string                                                   | is   | Control point                           |
| gatewayId            | string                                                   | no   | The red line matches the id             |
| desc                 | string                                                   | is   | Rule description                        |

## CreateRequestIndicator

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| threshold      | string         | no   | threshold             |
| hashId         | string         | no   | hashId                |
| operation      | string         | no   | operation             |

## The data is returned to the wrapper model String

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | string         | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
