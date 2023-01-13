# Obtain the token of the signing interface

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/sign/ipa/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/getSignToken

### Resource description

#### Obtain the token of the signing interface

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |
| pipelineId     | string         | is   | Pipeline ID           |               |
| buildId        | string         | is   | Build ID              |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data returns the wrapper model IPA packet signature information](get-the-signature-interface-token.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "buildId" : "String",  "projectId" : "String",  "pipelineId" : "String",  "token" : "String"  },  "message" : "String",  "status" : 0 } 
```

## The data returns the wrapper model IPA packet signature information

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [IPA packet signature information](get-the-signature-interface-token.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## IPA packet signature information

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| buildId        | string         | is   | Build ID              |
| projectId      | string         | is   | Item ID               |
| pipelineId     | string         | is   | Pipeline ID           |
| token          | string         | is   | Authentication token  |
