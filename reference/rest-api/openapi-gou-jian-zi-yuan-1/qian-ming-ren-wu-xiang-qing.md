# 签名任务详情

### 请求方法/请求路径

#### GET  /apigw-app/v3/sign/ipa/{resignId}/detail

### 资源描述

#### 签名任务详情

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |
| X-DEVOPS-UID | string | 是 | 用户ID | admin |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| resignId | string | 是 | 签名任务ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型签名状态查询结果]() |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
X-DEVOPS-UID: {X-DEVOPS-UID}
```

### 返回样例-200

```javascript
{
  "data" : {
    "resignId" : "String",
    "message" : "String",
    "status" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型签名状态查询结果

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [签名状态查询结果]() | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 签名状态查询结果

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| resignId | string | 是 | 签名ID |
| message | string | 是 | 描述信息 |
| status | string | 是 | 是否完成 |

