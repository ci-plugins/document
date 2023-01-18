# Editing credentials

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}/credentials/{credentialId}

### Resource description

#### Editing credentials

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                            | must | Parameter description | Default value |
| :------------- | :-------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Credentials - Content when updated](edit-credentials.md) | is   | evidence              |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| credentialId   | string         | is   | Credential ID         |               |

#### response

| HTTP code | description          | Parameter type                                           |
| :-------- | :------------------- | :------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](edit-credentials.md) |

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

## Credentials - Content when updated

| Parameter name   | Parameter type                                               | must | Parameter description  |
| :--------------- | :----------------------------------------------------------- | :--- | :--------------------- |
| credentialType   | ENUM(PASSWORD, ACCESSTOKEN, USERNAME_PASSWORD, SECRETKEY, APPID_SECRETKEY, SSH_PRIVATEKEY, TOKEN_SSH_PRIVATEKEY, TOKEN_USERNAME_PASSWORD, COS_APPID_SECRETID_SECRETKEY_REGION, MULTI_LINE_PASSWORD, ) | is   | Credential type        |
| credentialRemark | string                                                       | no   | Credential description |
| v1               | string                                                       | is   | Credential content     |
| credentialName   | string                                                       | is   | Credential name        |
| v2               | string                                                       | is   | Credential content     |
| v3               | string                                                       | is   | Credential content     |
| v4               | string                                                       | is   | Credential content     |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
