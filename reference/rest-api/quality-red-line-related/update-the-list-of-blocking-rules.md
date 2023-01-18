# Update the intercept rule list

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}/quality/rules/{ruleHashId}/update

### Resource description

#### Update the intercept rule list

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                              | must | Parameter description | Default value |
| :------------- | :---------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Rule update request](update-the-list-of-blocking-rules.md) | is   | Rule content          |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| ruleHashId     | string         | is   | Rule ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](update-the-list-of-blocking-rules.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Rule update request

| Parameter name       | Parameter type                                               | must | Parameter description                   |
| :------------------- | :----------------------------------------------------------- | :--- | :-------------------------------------- |
| templateRange        | List                                                         | is   | Set of pipelined template ids in effect |
| auditUserList        | List                                                         | no   | Audit notification personnel            |
| range                | List                                                         | is   | Set of pipeline ids in effect           |
| auditTimeoutMinutes  | integer                                                      | no   | Audit timeout                           |
| notifyTypeList       | List                                                         | no   | Notification type                       |
| notifyUserList       | List                                                         | no   | Notifier list                           |
| controlPointPosition | string                                                       | is   | Control point position                  |
| name                 | string                                                       | is   | Rule name                               |
| notifyGroupList      | List                                                         | no   | Notification group list                 |
| operation            | ENUM(END, AUDIT, )                                           | is   | Type of operation                       |
| indicatorIds         | List<[CreateRequestIndicator](update-the-list-of-blocking-rules.md)> | is   | Index type                              |
| controlPoint         | string                                                       | is   | Control point                           |
| gatewayId            | string                                                       | no   | The red line matches the id             |
| desc                 | string                                                       | is   | Rule description                        |

## CreateRequestIndicator

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| threshold      | string         | no   | threshold             |
| hashId         | string         | no   | hashId                |
| operation      | string         | no   | operation             |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
