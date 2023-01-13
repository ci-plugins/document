# Get the user download link

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/projects/{projectId}/artifactories/userDownloadUrl

### Resource description

#### Get the user download link

### Input parameter description

#### Query parameter

| Parameter name  | Parameter type | must | Parameter description   | Default value |
| :-------------- | :------------- | :--- | :---------------------- | :------------ |
| artifactoryType | string         | is   | Version repository type |               |
| path            | string         | is   | path                    |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data is returned to the packaging model version repository - download information |

#### Request sample

```
curl -X GET '[Please replace above API address bar request address]? artifactoryType={artifactoryType}&path={path}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "url2" : "String",  "url" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Data is returned to the packaging model version repository - download information

| Parameter name | Parameter type                            | must | Parameter description |
| :------------- | :---------------------------------------- | :--- | :-------------------- |
| data           | Version Repository - Download information | no   | data                  |
| message        | string                                    | no   | Error message         |
| status         | integer                                   | is   | Status code           |

## Version Repository - Download information

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| url2           | string         | no   | Download link 2       |
| url            | string         | is   | Download link         |
