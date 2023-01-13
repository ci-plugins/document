# Get plug-in statistics based on the plug-in code

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/atoms/{atomCode}/statistic

### Resource description

#### Get plug-in statistics based on the plug-in code

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| atomCode       | string         | is   | Plug-in code          |               |

#### response

| HTTP code | description          | Parameter type                              |
| :-------- | :------------------- | :------------------------------------------ |
| 200       | successful operation | The data returns packaging model statistics |

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
{  "data" : {  "score" : "parse error",  "downloads" : 0,  "successRate" : "parse error",  "recentExecuteNum" : 0,  "pipelineCnt" : 0,  "commentCnt" : 0  },  "message" : "String",  "status" : 0 } 
```

## The data returns packaging model statistics

| Parameter name | Parameter type          | must | Parameter description |
| :------------- | :---------------------- | :--- | :-------------------- |
| data           | Statistical information | no   | data                  |
| message        | string                  | no   | Error message         |
| status         | integer                 | is   | Status code           |

## Statistical information

| Parameter name   | Parameter type | must | Parameter description |
| :--------------- | :------------- | :--- | :-------------------- |
| score            | number         | no   | Star rating           |
| downloads        | integer        | no   | download              |
| successRate      | number         | no   | Success rate          |
| recentExecuteNum | integer        | no   | Last execution        |
| pipelineCnt      | integer        | no   | Number of pipeline    |
| commentCnt       | integer        | no   | Comment volume        |
