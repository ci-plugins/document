# Gets the value of the variable in the build

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/variables

### Resource description

#### Gets the value of the variable in the build

### Input parameter description

#### Body parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| body           | array          | is   | Variable name list    |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data returns the wrapper model MapStringString](get-the-value-of-the-variable-in-the-build.md) |

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
{  "data" : {  "string" : "string"  },  "message" : "String",  "status" : 0 } 
```

## The data returns the wrapper model MapStringString

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | object         | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
