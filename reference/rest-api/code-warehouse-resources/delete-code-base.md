# Delete code base

### Request method/request path

#### DELETE /ms/openapi/api/apigw/v3/repositories/{projectId}/{repositoryHashId}

### Resource description

#### Delete code base

### Input parameter description

#### Path parameter

| Parameter name   | Parameter type | must | Parameter description | Default value |
| :--------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId        | string         | is   | Item ID               |               |
| repositoryHashId | string         | is   | Code base hash ID     |               |

#### response

| HTTP code | description          | Parameter type                                           |
| :-------- | :------------------- | :------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](delete-code-base.md) |

#### Request sample

```
curl -X DELETE '[Please replace API address bar request address]' 
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
