# Obtain credentials

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/credentials/{credentialId}

### Resource description

#### Obtain credentials

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| credentialId   | string         | is   | Credential ID         |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data returns wrapper model credentials - credential content and permissions](get-credentials.md) |

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
{  "data" : {  "credentialType" : "ENUM",  "updatedTime" : 0,  "credentialRemark" : "String",  "permissions" : {  "view" : true,  "edit" : true,  "delete" : true  },  "credentialId" : "String",  "updateUser" : "String",  "v1" : "String",  "credentialName" : "String",  "v2" : "String",  "v3" : "String",  "v4" : "String"  },  "message" : "String",  "status" : 0 } 
```

## The data returns wrapper model credentials - credential content and permissions

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Credential - credential content and authority](get-credentials.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Credential - credential content and authority

| Parameter name   | Parameter type                                               | must | Parameter description  |
| :--------------- | :----------------------------------------------------------- | :--- | :--------------------- |
| credentialType   | ENUM(PASSWORD, ACCESSTOKEN, USERNAME_PASSWORD, SECRETKEY, APPID_SECRETKEY, SSH_PRIVATEKEY, TOKEN_SSH_PRIVATEKEY, TOKEN_USERNAME_PASSWORD, COS_APPID_SECRETID_SECRETKEY_REGION, MULTI_LINE_PASSWORD, ) | is   | Credential type        |
| updatedTime      | integer                                                      | is   | Last update time       |
| credentialRemark | string                                                       | no   | Credential description |
| permissions      | [Credentials - Credentials permissions](get-credentials.md)  | is   | authority              |
| credentialId     | string                                                       | is   | Credential ID          |
| updateUser       | string                                                       | is   | Last updater           |
| v1               | string                                                       | is   | Credential content     |
| credentialName   | string                                                       | is   | Credential name        |
| v2               | string                                                       | is   | Credential content     |
| v3               | string                                                       | is   | Credential content     |
| v4               | string                                                       | is   | Credential content     |

## Credentials - Credentials permissions

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| view           | boolean        | is   | View permission       |
| edit           | boolean        | is   | Edit permission       |
| delete         | boolean        | is   | Delete permission     |
