# 下载日志接口

## 请求方法/请求路径

### GET  /apigw-app/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/logs/download

## 资源描述

### 下载日志接口

## 输入参数说明

### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| tag | string | 否 | 对应element ID |  |
| jobId | string | 否 | 对应jobId |  |
| executeCount | integer | 否 | 执行次数 |  |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-UID | string | 应用态必须 | 用户名 |  |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |

### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |
| pipelineId | string | 是 | 流水线ID |  |
| buildId | string | 是 | 构建ID |  |

### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| default | successful operation | parse error |

### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?tag={tag}&amp;jobId={jobId}&amp;executeCount={executeCount}&amp;app_secret={app_secret}&amp;app_code={app_code}'
```

### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-UID: {X-DEVOPS-UID}
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
```

