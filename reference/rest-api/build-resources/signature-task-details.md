# Signature task details

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/sign/ipa/{resignId}/detail

### Resource description

#### Signature task details

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| resignId       | string         | is   | Signature task ID     |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data Returns the wrapper model signature status query result](signature-task-details.md) |

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
{  "data" : {  "resignId" : "String",  "message" : "String",  "status" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Data Returns the wrapper model signature status query result

| Parameter name | Parameter type                                               | must | Parameter description |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- |
| data           | [Result of signature status query](signature-task-details.md) | no   | data                  |
| message        | string                                                       | no   | Error message         |
| status         | integer                                                      | is   | Status code           |

## Result of signature status query

| Parameter name | Parameter type | must | Parameter description   |
| :------------- | :------------- | :--- | :---------------------- |
| resignId       | string         | is   | Signature ID            |
| message        | string         | is   | Description information |
| status         | string         | is   | Complete or not         |
