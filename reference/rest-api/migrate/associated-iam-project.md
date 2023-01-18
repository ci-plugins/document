# Associated iam project

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/permission/move/projects/{projectCode}/relationProject

### Resource description

#### Associated iam project

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description            | Default value |
| :------------- | :------------- | :--- | :------------------------------- | :------------ |
| relationId     | string         | is   | ID of the iam tier administrator |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectCode    | string         | is   | Project Code          |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](associated-iam-project.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]? relationId={relationId}' 
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
