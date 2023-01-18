# Adds the specified user to the specified project user group

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/createUser

### Resource description

#### Adds the specified user to the specified project user group

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [ProjectCreateUserInfo](add-the-specified-user-to-the-specified-project-user-group.md) | is   | Add information       |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](add-the-specified-user-to-the-specified-project-user-group.md) |

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
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## ProjectCreateUserInfo

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| createUserId   | string         | no   | Operating user        |
| roleId         | integer        | no   | Role Id               |
| userIds        | List           | no   | Multi-target user id  |
| roleName       | string         | no   | Role name             |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
