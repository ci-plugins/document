# New credential

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/credentials

### Resource description

#### New credential

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Credentials - Content at creation time](add-credentials.md) | is   | evidence              |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                          |
| :-------- | :------------------- | :------------------------------------------------------ |
| 200       | successful operation | [Data return wrapper model Boolean](add-credentials.md) |

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

## Credentials - Content at creation time

| Parameter name   | Parameter type                                               | must | Parameter description  |
| :--------------- | :----------------------------------------------------------- | :--- | :--------------------- |
| credentialType   | ENUM(PASSWORD, ACCESSTOKEN, USERNAME_PASSWORD, SECRETKEY, APPID_SECRETKEY, SSH_PRIVATEKEY, TOKEN_SSH_PRIVATEKEY, TOKEN_USERNAME_PASSWORD, COS_APPID_SECRETID_SECRETKEY_REGION, MULTI_LINE_PASSWORD, ) | is   | Credential type        |
| credentialRemark | string                                                       | no   | Credential description |
| credentialId     | string                                                       | is   | Credential ID          |
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
