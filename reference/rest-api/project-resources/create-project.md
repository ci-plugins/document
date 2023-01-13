# Create a project

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/projects

### Resource description

#### Create a project

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                           | must | Parameter description | Default value |
| :------------- | :--------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Project - New model](create-project.md) | is   | Project information   |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
|                |                |      |                       |               |

#### response

| HTTP code | description          | Parameter type                                         |
| :-------- | :------------------- | :----------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](create-project.md) |

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

## Project - New model

| Parameter name | Parameter type | must | Parameter description        |
| :------------- | :------------- | :--- | :--------------------------- |
| englishName    | string         | no   | English abbreviation         |
| deptName       | string         | no   | Name of secondary department |
| centerId       | integer        | no   | Tertiary department ID       |
| secrecy        | boolean        | no   | Confidentiality or not       |
| kind           | integer        | no   | kind                         |
| projectType    | integer        | no   | Item type                    |
| deptId         | integer        | no   | Secondary department ID      |
| description    | string         | no   | description                  |
| bgName         | string         | no   | Name of primary department   |
| projectName    | string         | no   | Project name                 |
| bgId           | integer        | no   | Primary department ID        |
| centerName     | string         | no   | Three-level department name  |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
