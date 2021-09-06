# 删除代码库

### 请求方法/请求路径

#### DELETE  \[yourIpAddress\]/ms/openapi/api/apigw/v3/repositories/{projectId}/{repositoryHashId}

### 资源描述

#### 删除代码库

### 输入参数说明

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |
| repositoryHashId | string | 是 | 代码库哈希ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型Boolean](shan-chu-dai-ma-ku.md) |

#### 请求样例

```javascript
curl -X DELETE '[请替换为API地址栏请求地址]'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
```

### 返回样例-200

```javascript
{
  "data" : true,
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型Boolean

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | boolean | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

