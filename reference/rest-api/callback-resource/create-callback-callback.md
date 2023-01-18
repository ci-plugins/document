# Create a callback

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/callbacks

### Resource description

#### Create a callback

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| url            | string         | is   | url                   |               |
| region         | string         | is   | region                |               |
| event          | string         | is   | event                 |               |
| secretToken    | string         | no   | secretToken           |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | projectId             |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](create-callback-callback.md) |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? url={url}&region={region}&event={event}&secretToken={secretToken}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
