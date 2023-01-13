# Get the pipeline details for use based on the plug-in code

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/atoms/{atomCode}/pipelines

### Resource description

#### Get the pipeline details for use based on the plug-in code

### Input parameter description

#### Query parameter

| Parameter name | Parameter type | must | Parameter description    | Default value |
| :------------- | :------------- | :--- | :----------------------- | :------------ |
| page           | integer        | no   | What page                | 1             |
| pageSize       | integer        | no   | How many pieces per page | 20            |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| atomCode       | string         | is   | Plug-in code          |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | Data return packaging model page data packaging model pipeline information |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]? page={page}&pageSize={pageSize}' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "records" : [ {  "pipelineName" : "String",  "deptName" : "String",  "projectCode" : "String",  "bgName" : "String",  "projectName" : "String",  "pipelineId" : "String",  "atomVersion" : "String",  "centerName" : "String"  } ],  "count" : 0,  "totalPages" : 0,  "pageSize" : 0,  "page" : 0  },  "message" : "String",  "status" : 0 } 
```

## Data return packaging model page data packaging model pipeline information

| Parameter name | Parameter type                               | must | Parameter description |
| :------------- | :------------------------------------------- | :--- | :-------------------- |
| data           | Paging data wraps model pipeline information | no   | data                  |
| message        | string                                       | no   | Error message         |
| status         | integer                                      | is   | Status code           |

## Paging data wraps model pipeline information

| Parameter name | Parameter type               | must | Parameter description        |
| :------------- | :--------------------------- | :--- | :--------------------------- |
| records        | List< pipeline information > | is   | data                         |
| count          | integer                      | is   | Total number of record lines |
| totalPages     | integer                      | is   | How many pages in total?     |
| pageSize       | integer                      | is   | How many pieces per page     |
| page           | integer                      | is   | What page                    |

## Pipeline information

| Parameter name | Parameter type | must | Parameter description                           |
| :------------- | :------------- | :--- | :---------------------------------------------- |
| pipelineName   | string         | is   | Pipeline name                                   |
| deptName       | string         | no   | Subordinate department                          |
| projectCode    | string         | is   | Item identification                             |
| bgName         | string         | no   | Owning BG                                       |
| projectName    | string         | no   | Affiliated project                              |
| pipelineId     | string         | is   | Pipeline ID                                     |
| atomVersion    | string         | no   | The version of the plug-in used by the pipeline |
| centerName     | string         | no   | Subordinate center                              |
