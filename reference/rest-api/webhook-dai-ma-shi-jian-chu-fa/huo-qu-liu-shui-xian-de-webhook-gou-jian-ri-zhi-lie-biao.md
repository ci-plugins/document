# 获取流水线的webhook构建日志列表

### 请求方法/请求路径

#### GET  /apigw-app/v3/{projectId}/{pipelineId}/webhook/buildLog

### 资源描述

#### 获取流水线的webhook构建日志列表

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| repoName | string | 否 | 仓库名 |  |
| commitId | string | 否 | commitId |  |
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
| 200 | successful operation | [数据返回包装模型SQLPage流水线webhook-触发日志明细](huo-qu-liu-shui-xian-de-webhook-gou-jian-ri-zhi-lie-biao.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为上方API地址栏请求地址]?repoName={repoName}&amp;commitId={commitId}&amp;page={page}&amp;pageSize={pageSize}&amp;app_secret={app_secret}&amp;app_code={app_code}'
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
    "records" : [ {
      "codeType" : "String",
      "repoName" : "String",
      "success" : true,
      "triggerResult" : "String",
      "createdTime" : 0,
      "logId" : 0,
      "taskName" : "String",
      "id" : 0,
      "commitId" : "String",
      "projectId" : "String",
      "taskId" : "String",
      "pipelineId" : "String"
    } ],
    "count" : 0
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型SQLPage流水线webhook-触发日志明细

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [SQLPage流水线webhook-触发日志明细](huo-qu-liu-shui-xian-de-webhook-gou-jian-ri-zhi-lie-biao.md) | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## SQLPage流水线webhook-触发日志明细

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| records | List&lt;[流水线webhook-触发日志明细](huo-qu-liu-shui-xian-de-webhook-gou-jian-ri-zhi-lie-biao.md)&gt; | 否 | records |
| count | integer | 否 | count |

## 流水线webhook-触发日志明细

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| codeType | string | 是 | 代码库类型 |
| repoName | string | 是 | 仓库名 |
| success | boolean | 是 | 是否成功触发 |
| triggerResult | string | 是 | 触发结果,如果触发成功就是buildId,触发不成功就是不成功原因 |
| createdTime | integer | 否 | createdTime |
| logId | integer | 否 | logId |
| taskName | string | 是 | 插件名 |
| id | integer | 否 | id |
| commitId | string | 是 | commitId |
| projectId | string | 是 | 项目ID |
| taskId | string | 是 | 插件ID |
| pipelineId | string | 是 | 流水线ID |

