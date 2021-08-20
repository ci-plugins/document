# 清理文件托管任务

### 请求方法/请求路径

#### PUT  /apigw-app/v3/artifactory/fileTask/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/tasks/{taskId}/clear

### 资源描述

#### 清理文件托管任务

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
| X-DEVOPS-UID | string | 是 | userId |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | projectId |  |
| pipelineId | string | 是 | pipelineId |  |
| buildId | string | 是 | buildId |  |
| taskId | string | 是 | taskId |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | 数据返回包装模型Boolean |

#### 请求样例

```javascript
curl -X PUT '[请替换为上方API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
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
  "data" : true,
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型Boolean

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | boolean | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

