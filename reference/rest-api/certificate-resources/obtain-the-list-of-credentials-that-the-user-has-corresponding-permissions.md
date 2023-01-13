# Gets a list of permissions for the user

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/credentials

### Resource description

#### Gets a list of permissions for the user

### Input parameter description

#### Query parameter

| Parameter name  | Parameter type | must | Parameter description                         | Default value |
| :-------------- | :------------- | :--- | :-------------------------------------------- | :------------ |
| credentialTypes | string         | no   | List of credential types, separated by commas |               |
| page            | integer        | no   | What page                                     | 1             |
| pageSize        | integer        | no   | How many pieces per page                      | 20            |
| keyword         | string         | no   | Key word                                      |               |

| X-DEVOPS-UID | string | is   | User ID | admin |
| :----------- | :----- | :--- | :------ | :---- |
|              |        |      |         |       |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Return Wrapper Model Paging Data Wrapper Model credentials - credential content and permissions](obtain-the-list-of-credentials-that-the-user-has-corresponding-permissions.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? credentialTypes={credentialTypes}&page={page}&pageSize={pageSize}&keyword={keyword}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "credentialType" : "ENUM",  "updatedTime" : 0,  "credentialRemark" : "String",  "permissions" : {  "view" : true,  "edit" : true,  "delete" : true  },  "credentialId" : "String",  "updateUser" : "String",  "v1" : "String",  "credentialName" : "String",  "v2" : "String",  "v3" : "String",  "v4" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper Model Paging Data Wrapper Model credentials - credential content and permissions

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Paging data wrapper model credentials - credential content and permissions](obtain-the-list-of-credentials-that-the-user-has-corresponding-permissions.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging data wrapper model credentials - credential content and permissions

| Parameter name | Parameter type                                               | must | Parameter description        |
| :------------- | :----------------------------------------------------------- | :--- | :--------------------------- |
| records        | List< [credential - credential contents and permissions](obtain-the-list-of-credentials-that-the-user-has-corresponding-permissions.md) > | is   | data                         |
| count          | integer                                                      | is   | Total number of record lines |
| totalPages     | integer                                                      | is   | How many pages in total?     |
| pageSize       | integer                                                      | is   | How many pieces per page     |
| page           | integer                                                      | is   | What page                    |

## Credential - credential content and authority

| Parameter name   | Parameter type                                               | must | Parameter description  |
| :--------------- | :----------------------------------------------------------- | :--- | :--------------------- |
| credentialType   | ENUM(PASSWORD, ACCESSTOKEN, USERNAME_PASSWORD, SECRETKEY, APPID_SECRETKEY, SSH_PRIVATEKEY, TOKEN_SSH_PRIVATEKEY, TOKEN_USERNAME_PASSWORD, COS_APPID_SECRETID_SECRETKEY_REGION, MULTI_LINE_PASSWORD, ) | is   | Credential type        |
| updatedTime      | integer                                                      | is   | Last update time       |
| credentialRemark | string                                                       | no   | Credential description |
| permissions      | [Credentials - Credentials permissions](obtain-the-list-of-credentials-that-the-user-has-corresponding-permissions.md) | is   | authority              |
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
