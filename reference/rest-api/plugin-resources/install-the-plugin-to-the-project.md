# Install the plug-in into the project

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/atoms/{atomCode}/install

### Resource description

#### Install the plug-in into the project

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| channelCode    | string         | no   | Channel type          |               |

#### Body parameter

| Parameter name | Parameter type                             | must | Parameter description                            | Default value |
| :------------- | :----------------------------------------- | :--- | :----------------------------------------------- | :------------ |
| body           | Install plug-in to project request message | is   | Install the plug-in to the project request style |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
|                |                |      |                       |               |

#### response

| HTTP code | description          | Parameter type                    |
| :-------- | :------------------- | :-------------------------------- |
| 200       | successful operation | Data return wrapper model Boolean |

#### Request sample

```
curl -X POST '[please replace API address bar request address]? channelCode={channelCode}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Install plug-in to project request message

| Parameter name | Parameter type | must | Parameter description  |
| :------------- | :------------- | :--- | :--------------------- |
| atomCode       | string         | is   | Plug-in identification |
| projectCode    | List           | is   | Item identification    |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
