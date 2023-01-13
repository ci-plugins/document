# Gets the node list of the specified item according to the hashId of the environment (does not verify permissions)

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/environment/projects/{projectId}/nodes/listRawByEnvHashIds

### Resource description

#### Gets the node list of the specified item according to the hashId of the environment (does not verify permissions)

### Input parameter description

#### Body parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| body           | array          | is   | Node hashIds          |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data return wrapper model MapStringList Node Information (permissions) |

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

## Data return wrapper model MapStringList Node Information (permissions)

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | object         | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
