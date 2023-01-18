# Get files based on metadata

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/artifactories

### Resource description

#### Get files based on metadata

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description                                   | Default value |
| :------------- | :------------- | :--- | :------------------------------------------------------ | :------------ |
| pipelineId     | string         | is   | Pipeline ID                                             |               |
| buildId        | string         | is   | Build ID                                                |               |
| page           | integer        | no   | What page                                               | 1             |
| pageSize       | integer        | no   | How many items per page (not passed default return all) | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data Return Wrapper model page Data wrapper model version repository - File information |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? pipelineId={pipelineId}&buildId={buildId}&page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "fullPath" : "String",  "modifiedTime" : 0,  "appVersion" : "String",  "shortUrl" : "String",  "downloadUrl" : "String",  "fullName" : "String",  "path" : "String",  "folder" : true,  "size" : 0,  "name" : "String",  "artifactoryType" : "ENUM",  "properties" : [ {  "value" : "String",  "key" : "String"  } ],  "md5" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data Return Wrapper model page Data wrapper model version repository - File information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | Paging data wrapper Model version repository - File information | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Paging data wrapper Model version repository - File information

| Parameter name | Parameter type                                | must | Parameter description        |
| :------------- | :-------------------------------------------- | :--- | :--------------------------- |
| records        | List< version repository - file information > | is   | data                         |
| count          | integer                                       | is   | Total number of record lines |
| totalPages     | integer                                       | is   | How many pages in total?     |
| pageSize       | integer                                       | is   | How many pieces per page     |
| page           | integer                                       | is   | What page                    |

## Version repository - File information

| Parameter name  | Parameter type                        | must | Parameter description |
| :-------------- | :------------------------------------ | :--- | :-------------------- |
| fullPath        | string                                | is   | Full file path        |
| modifiedTime    | integer                               | is   | Update time           |
| appVersion      | string                                | is   | app version           |
| shortUrl        | string                                | is   | Download short link   |
| downloadUrl     | string                                | no   | Download link         |
| fullName        | string                                | is   | Full name of document |
| path            | string                                | is   | File path             |
| folder          | boolean                               | is   | Yes folder            |
| size            | integer                               | is   | File size (byte)      |
| name            | string                                | is   | File name             |
| artifactoryType | ENUM(PIPELINE, CUSTOM_DIR, )          | is   | Warehouse type        |
| properties      | List< version repository - metadata > | is   | metadata              |
| md5             | string                                | no   | MD5                   |

## Version Repository - Metadata

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| value          | string         | is   | Metadata value        |
| key            | string         | is   | Metadata key          |
