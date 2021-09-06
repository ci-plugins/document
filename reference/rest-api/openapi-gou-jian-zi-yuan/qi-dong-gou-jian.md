# 启动构建

### 请求方法/请求路径

#### POST  /apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/start

### 资源描述

#### 启动构建

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| buildNo | integer | 否 | 手动指定构建版本参数 |  |
| channelCode | string | 否 | 渠道号，默认为BS |  |

#### Body参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| body | map | 是 | 启动参数 |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |
| pipelineId | string | 是 | 流水线ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型构建模型-ID]() |

#### 请求样例

```javascript
curl -X POST '[请替换为API地址栏请求地址]?buildNo={buildNo}&amp;channelCode={channelCode}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
```

### 返回样例-200

```javascript
{
  "data" : {
    "id" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型构建模型-ID

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [构建模型-ID]() | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 构建模型-ID

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| id | string | 是 | 构建ID |

