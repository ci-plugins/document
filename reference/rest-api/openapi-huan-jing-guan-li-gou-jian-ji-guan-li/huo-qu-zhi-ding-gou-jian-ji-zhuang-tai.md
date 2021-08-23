# 获取指定构建机状态

### 请求方法/请求路径

#### GET  /apigw-app/v3/projects/{projectId}/environment/thirdPartAgent/nodes/status

### 资源描述

#### 获取指定构建机状态

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| nodeHashId | string | 是 | 节点 hashId |  |
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
| projectId | string | 是 | projectId |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | 数据返回包装模型节点信息\(权限\) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?nodeHashId={nodeHashId}&amp;app_secret={app_secret}&amp;app_code={app_code}'
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
    "pipelineRefCount" : 0,
    "nodeHashId" : "String",
    "displayName" : "String",
    "ip" : "String",
    "canEdit" : true,
    "nodeStatus" : "String",
    "nodeType" : "String",
    "osName" : "String",
    "agentStatus" : true,
    "operator" : "String",
    "canUse" : true,
    "bakOperator" : "String",
    "lastBuildTime" : "String",
    "lastModifyUser" : "String",
    "createTime" : "String",
    "lastModifyTime" : "String",
    "name" : "String",
    "bizId" : 0,
    "canDelete" : true,
    "nodeId" : "String",
    "createdUser" : "String",
    "gateway" : "String",
    "agentHashId" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型节点信息\(权限\)

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | 节点信息\(权限\) | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 节点信息\(权限\)

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| pipelineRefCount | integer | 否 | 流水线Job引用数 |
| nodeHashId | string | 是 | 环境 HashId |
| displayName | string | 否 | 显示名称 |
| ip | string | 是 | IP |
| canEdit | boolean | 否 | 是否可以编辑 |
| nodeStatus | string | 是 | 节点状态 |
| nodeType | string | 是 | 节点类型 |
| osName | string | 否 | 操作系统 |
| agentStatus | boolean | 是 | agent状态 |
| operator | string | 否 | 责任人 |
| canUse | boolean | 否 | 是否可以使用 |
| bakOperator | string | 否 | 备份责任人 |
| lastBuildTime | string | 否 | 流水线Job引用数 |
| lastModifyUser | string | 否 | 最后修改人 |
| createTime | string | 否 | 创建/导入时间 |
| lastModifyTime | string | 否 | 最后修改时间 |
| name | string | 是 | 节点名称 |
| bizId | integer | 否 | 所属业务, 默认-1表示没有绑定业务 |
| canDelete | boolean | 否 | 是否可以删除 |
| nodeId | string | 是 | 节点 Id |
| createdUser | string | 是 | 创建人 |
| gateway | string | 否 | 网关地域 |
| agentHashId | string | 否 | agent hash id |

