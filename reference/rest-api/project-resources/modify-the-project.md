# Modify item

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/projects/{projectId}

### Resource description

#### Modify item

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                      | must | Parameter description | Default value |
| :------------- | :-------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Project - Modify the model](modify-the-project.md) | is   | Project information   |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                             |
| :-------- | :------------------- | :--------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](modify-the-project.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
```

## Project - Modify the model

| Parameter name | Parameter type | must | Parameter description                                        |
| :------------- | :------------- | :--- | :----------------------------------------------------------- |
| centerId       | integer        | no   | Center ID                                                    |
| deptName       | string         | no   | Department name                                              |
| englishName    | string         | no   | English abbreviation                                         |
| ccAppName      | string         | no   | cc app name                                                  |
| kind           | integer        | no   | Container selection, 0 is not selected, 1 is k8s, 2 is mesos |
| projectType    | integer        | no   | Item type                                                    |
| deptId         | integer        | no   | Department ID                                                |
| description    | string         | no   | description                                                  |
| bgId           | integer        | no   | Business group ID                                            |
| secrecy        | boolean        | no   | Confidentiality or not                                       |
| bgName         | string         | no   | Business group name                                          |
| projectName    | string         | no   | Project name                                                 |
| ccAppId        | integer        | no   | cc app id                                                    |
| centerName     | string         | no   | Center name                                                  |

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
