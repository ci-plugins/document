# 获取项目下pipelineId+自增id

### 请求方法/请求路径

#### GET  \[yourIpAddress\]/ms/openapi/api/apigw/v3/permission/move/projects/{projectCode}/pipelineIds/list

### 资源描述

#### 获取项目下pipelineId+自增id

### 输入参数说明

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| projectCode | string | 是 | 项目Code |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型ListPipelineIdInfo](huo-qu-xiang-mu-xia-pipelineid+-zi-zeng-id.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
```

### 返回样例-200

```javascript
{
  "data" : [ {
    "id" : 0,
    "pipelineId" : "String"
  } ],
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型ListPipelineIdInfo

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | List&lt;[PipelineIdInfo](huo-qu-xiang-mu-xia-pipelineid+-zi-zeng-id.md)&gt; | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## PipelineIdInfo

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| id | integer | 否 | id |
| pipelineId | string | 否 | pipelineId |

