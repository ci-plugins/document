# 获取用户下载链接

### 请求方法/请求路径

#### GET  /apigw-app/v3/projects/{projectId}/artifactories/userDownloadUrl

### 资源描述

#### 获取用户下载链接

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| artifactoryType | string | 是 | 版本仓库类型 |  |
| path | string | 是 | 路径 |  |
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

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | 数据返回包装模型版本仓库-下载信息 |

#### 请求样例

```javascript
curl -X GET '[请替换为上方API地址栏请求地址]?artifactoryType={artifactoryType}&amp;path={path}&amp;app_secret={app_secret}&amp;app_code={app_code}'
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
    "url2" : "String",
    "url" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型版本仓库-下载信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | 版本仓库-下载信息 | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 版本仓库-下载信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| url2 | string | 否 | 下载链接2 |
| url | string | 是 | 下载链接 |

