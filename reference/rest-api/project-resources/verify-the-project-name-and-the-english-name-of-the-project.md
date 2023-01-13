# Verify the project name and the project English name

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{validateType}/names/validate

### Resource description

#### Verify the project name and the project English name

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description                       | Default value |
| :------------- | :------------- | :--- | :------------------------------------------ | :------------ |
| name           | string         | no   | Project name or English name of the project |               |
| english_name   | string         | no   | Item ID                                     |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description                                        | Default value |
| :------------- | :------------- | :--- | :----------------------------------------------------------- | :------------ |
| validateType   | string         | is   | The check is the project name or the project name in English |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](verify-the-project-name-and-the-english-name-of-the-project.md) |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? name={name}&english_name={english_name}' 
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
