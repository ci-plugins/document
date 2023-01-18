# Install the R&D store template into the project

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/market/template/installFromStore

### Resource description

#### Install the R&D store template into the project

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description                                        | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :----------------------------------------------------------- | :------------ |
| body           | [Install template to project request message](install-the-r-and-d-store-template-into-the-project.md) | is   | Install the R&D store template into the project request style |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
|                |                |      |                       |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](install-the-r-and-d-store-template-into-the-project.md) |

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
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Install template to project request message

| Parameter name  | Parameter type | must | Parameter description |
| :-------------- | :------------- | :--- | :-------------------- |
| projectCodeList | List           | is   | Item identification   |
| templateCode    | string         | is   | Template code         |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
