# 获取代码提交记录

### 请求方法/请求路径

#### GET  /apigw-app/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/repositoryCommit

### 资源描述

#### 获取代码提交记录

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
| buildId | string | 是 | buildID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型ListCommitResponse](huo-qu-dai-ma-ti-jiao-ji-lu.md) |

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
  "data" : [ {
    "elementId" : "String",
    "records" : [ {
      "elementId" : "String",
      "repoId" : "String",
      "committer" : "String",
      "commitTime" : 0,
      "repoName" : "String",
      "commit" : "String",
      "buildId" : "String",
      "comment" : "String",
      "type" : 0,
      "url" : "String",
      "pipelineId" : "String"
    } ],
    "name" : "String"
  } ],
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型ListCommitResponse

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | List&lt;[CommitResponse](huo-qu-dai-ma-ti-jiao-ji-lu.md)&gt; | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## CommitResponse

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| elementId | string | 否 | elementId |
| records | List&lt;[CommitData](huo-qu-dai-ma-ti-jiao-ji-lu.md)&gt; | 否 | records |
| name | string | 否 | name |

## CommitData

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| elementId | string | 否 | elementId |
| repoId | string | 否 | repoId |
| committer | string | 否 | committer |
| commitTime | integer | 否 | commitTime |
| repoName | string | 否 | repoName |
| commit | string | 否 | commit |
| buildId | string | 否 | buildId |
| comment | string | 否 | comment |
| type | integer | 否 | type |
| url | string | 否 | url |
| pipelineId | string | 否 | pipelineId |

