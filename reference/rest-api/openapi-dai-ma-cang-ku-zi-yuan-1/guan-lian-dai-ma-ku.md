# 关联代码库

### 请求方法/请求路径

#### POST  [yourIpAddress]/ms/openapi/api/apigw/v3/repositories/{projectId}

### 资源描述

#### 关联代码库

### 输入参数说明

#### Body参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| body | [代码库模型-多态基类]() | 是 | 代码库模型 |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型代码库模型-ID]() |

#### 请求样例

```javascript
curl -X POST '[请替换为API地址栏请求地址]'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
```

### 返回样例-200

```javascript
{
  "data" : {
    "hashId" : "String"
  },
  "message" : "String",
  "status" : 0
}
```

## 代码库模型-多态基类

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| startPrefix | string | 否 | startPrefix |
| aliasName | string | 否 | aliasName |
| formatURL | string | 否 | formatURL |
| legal | boolean | 否 | legal |
| credentialId | string | 否 | credentialId |
| userName | string | 否 | userName |
| projectName | string | 否 | projectName |
| projectId | string | 否 | projectId |
| url | string | 否 | url |
| repoHashId | string | 否 | repoHashId |

## 数据返回包装模型代码库模型-ID

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [代码库模型-ID]() | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 代码库模型-ID

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| hashId | string | 是 | 代码库哈希ID |

