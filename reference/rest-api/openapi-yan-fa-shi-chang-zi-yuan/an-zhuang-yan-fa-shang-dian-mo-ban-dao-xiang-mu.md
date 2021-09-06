# 安装研发商店模板到项目

### 请求方法/请求路径

#### POST  [yourIpAddress]/ms/openapi/api/apigw/v3/market/template/installFromStore

### 资源描述

#### 安装研发商店模板到项目

### 输入参数说明

#### Body参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| body | [安装模板到项目请求报文]() | 是 | 安装研发商店模板到项目请求报文体 |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型Boolean]() |

#### 请求样例

```javascript
curl -X POST '[请替换为API地址栏请求地址]'
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

## 安装模板到项目请求报文

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| projectCodeList | List | 是 | 项目标识 |
| templateCode | string | 是 | 模板代码 |

## 数据返回包装模型Boolean

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | boolean | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

