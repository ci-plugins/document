# 获取所有分组信息

### 请求方法/请求路径

#### GET  /apigw-app/v3/projects/{projectId}/pipelineGroups/groups

### 资源描述

#### 获取所有分组信息

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-UID | string | 是 | 用户ID | admin |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| projectId | string | 是 | 项目ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型ListPipelineGroup](huo-qu-suo-you-fen-zu-xin-xi.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-UID: {X-DEVOPS-UID}
```

### 返回样例-200

```javascript
{
  "data" : [ {
    "createTime" : 0,
    "name" : "String",
    "updateUser" : "String",
    "updateTime" : 0,
    "createUser" : "String",
    "id" : "String",
    "projectId" : "String",
    "labels" : [ {
      "createTime" : 0,
      "groupId" : "String",
      "name" : "String",
      "updateUser" : "String",
      "uptimeTime" : 0,
      "createUser" : "String",
      "id" : "String"
    } ]
  } ],
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型ListPipelineGroup

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | List&lt;[PipelineGroup](huo-qu-suo-you-fen-zu-xin-xi.md)&gt; | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## PipelineGroup

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| createTime | integer | 否 | createTime |
| name | string | 否 | name |
| updateUser | string | 否 | updateUser |
| updateTime | integer | 否 | updateTime |
| createUser | string | 否 | createUser |
| id | string | 否 | id |
| projectId | string | 否 | projectId |
| labels | List&lt;[PipelineLabel](huo-qu-suo-you-fen-zu-xin-xi.md)&gt; | 否 | labels |

## PipelineLabel

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| createTime | integer | 否 | createTime |
| groupId | string | 否 | groupId |
| name | string | 否 | name |
| updateUser | string | 否 | updateUser |
| uptimeTime | integer | 否 | uptimeTime |
| createUser | string | 否 | createUser |
| id | string | 否 | id |

