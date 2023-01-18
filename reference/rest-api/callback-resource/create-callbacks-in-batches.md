# Example Create callbacks in batches

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/callbacks/batch

### Resource description

#### Example Create callbacks in batches

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
| 200       | successful operation | [The data returns the result of the pipeline callback creation for the wrapper model project](create-callbacks-in-batches.md) |

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
{  "data" : {  "successEvents" : "string",  "failureEvents" : {  "string" : "string"  }  },  "message" : "String",  "status" : 0 } 
```

## The data returns the result of the pipeline callback creation for the wrapper model project

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Pipelined callback creation results for the project](create-callbacks-in-batches.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Pipelined callback creation results for the project

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| successEvents  | List           | no   | successEvents         |
| failureEvents  | object         | no   | failureEvents         |
