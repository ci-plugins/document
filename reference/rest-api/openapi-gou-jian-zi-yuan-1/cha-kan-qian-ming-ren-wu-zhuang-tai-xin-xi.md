# 查看签名任务状态信息

### 请求方法/请求路径

#### GET  \[yourIpAddress\]/ms/openapi/api/apigw/v3/sign/ipa/{resignId}/status

### 资源描述

#### 查看签名任务状态信息

### 输入参数说明

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| resignId | string | 是 | 签名任务ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型String](cha-kan-qian-ming-ren-wu-zhuang-tai-xin-xi.md) |

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
  "data" : "String",
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型String

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | string | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

