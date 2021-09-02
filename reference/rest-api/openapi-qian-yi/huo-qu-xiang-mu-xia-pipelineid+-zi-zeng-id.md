# 获取项目下pipelineId+自增id

### 请求方法/请求路径

#### GET  /apigw-app/v3/permission/move/projects/{projectCode}/pipelineIds/list

### 资源描述

#### 获取项目下pipelineId+自增id

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-UID | string | 应用态必须 | 用户名 |  |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectCode | string | 是 | 项目Code |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型ListPipelineIdInfo](huo-qu-xiang-mu-xia-pipelineid+-zi-zeng-id.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-UID: {X-DEVOPS-UID}
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
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

