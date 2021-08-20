# 获取签名接口token

### 请求方法/请求路径

#### GET  /apigw-app/v3/sign/ipa/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/getSignToken

### 资源描述

#### 获取签名接口token

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
| projectId | string | 是 | 项目ID |  |
| pipelineId | string | 是 | 流水线ID |  |
| buildId | string | 是 | 构建ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型IPA包签名信息]() |

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
    "buildId" : "String",
    "projectId" : "String",
    "pipelineId" : "String",
    "token" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型IPA包签名信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [IPA包签名信息]() | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## IPA包签名信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| buildId | string | 是 | 构建ID |
| projectId | string | 是 | 项目ID |
| pipelineId | string | 是 | 流水线ID |
| token | string | 是 | 鉴权token |

