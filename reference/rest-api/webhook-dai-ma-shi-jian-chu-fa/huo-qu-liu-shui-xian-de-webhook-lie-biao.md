# 获取流水线的webhook列表

### 请求方法/请求路径

#### GET  /apigw-app/v3/{projectId}/{pipelineId}/webhook

### 资源描述

#### 获取流水线的webhook列表

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| page | integer | 否 | 页码 |  |
| pageSize | integer | 否 | 每页大小 |  |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |
| X-DEVOPS-UID | string | 是 | userId |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 |  |  |
| pipelineId | string | 是 |  |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型ListPipelineWebhook](huo-qu-liu-shui-xian-de-webhook-lie-biao.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?page={page}&amp;pageSize={pageSize}&amp;app_secret={app_secret}&amp;app_code={app_code}'
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
  "data" : [ {
    "repoType" : "ENUM",
    "repoName" : "String",
    "repositoryType" : "ENUM",
    "id" : 0,
    "projectName" : "String",
    "projectId" : "String",
    "repoHashId" : "String",
    "taskId" : "String",
    "pipelineId" : "String"
  } ],
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型ListPipelineWebhook

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | List&lt;[PipelineWebhook](huo-qu-liu-shui-xian-de-webhook-lie-biao.md)&gt; | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## PipelineWebhook

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| repoType | ENUM\(ID, NAME, \) | 否 | repoType |
| repoName | string | 否 | repoName |
| repositoryType | ENUM\(CODE\_SVN, CODE\_GIT, CODE\_GITLAB, GITHUB, CODE\_TGIT, \) | 否 | repositoryType |
| id | integer | 否 | id |
| projectName | string | 否 | projectName |
| projectId | string | 否 | projectId |
| repoHashId | string | 否 | repoHashId |
| taskId | string | 否 | taskId |
| pipelineId | string | 否 | pipelineId |

