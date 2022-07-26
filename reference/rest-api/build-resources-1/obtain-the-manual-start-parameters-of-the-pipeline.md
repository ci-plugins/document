# 获取流水线手动启动参数

### 请求方法/请求路径

#### GET  /ms/openapi/api/apigw/v3/projects/{projectId}/pipelines/{pipelineId}/builds/manualStartupInfo

### 资源描述

#### 获取流水线手动启动参数

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| channelCode | string | 否 | 渠道号，默认为BS |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| projectId | string | 是 | 项目ID |  |
| pipelineId | string | 是 | 流水线ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型构建模型-流水线手动启动信息](obtain-the-manual-start-parameters-of-the-pipeline.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?channelCode={channelCode}' \
-H 'X-DEVOPS-UID:xxx'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-UID:xxx
```

### 返回样例-200

```javascript
{
  "data" : {
    "canManualStartup" : true,
    "canElementSkip" : true,
    "buildNo" : {
      "buildNoType" : "ENUM",
      "buildNo" : 0,
      "required" : true
    },
    "properties" : [ {
      "defaultValue" : {
        "string" : "string"
      },
      "containerType" : {
        "os" : "ENUM",
        "buildType" : "ENUM"
      },
      "glob" : "String",
      "replaceKey" : "String",
      "readOnly" : true,
      "label" : "String",
      "type" : "ENUM",
      "required" : true,
      "repoHashId" : "String",
      "scmType" : "ENUM",
      "relativePath" : "String",
      "propertyType" : "String",
      "options" : [ {
        "value" : "String",
        "key" : "String"
      } ],
      "searchUrl" : "String",
      "id" : "String",
      "placeholder" : "String",
      "properties" : {
        "string" : "string"
      },
      "desc" : "String"
    } ]
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型构建模型-流水线手动启动信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [构建模型-流水线手动启动信息](obtain-the-manual-start-parameters-of-the-pipeline.md) | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 构建模型-流水线手动启动信息

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| canManualStartup | boolean | 是 | 是否可手工启动 |
| canElementSkip | boolean | 是 | 是否可跳过插件 |
| buildNo | [BuildNo](obtain-the-manual-start-parameters-of-the-pipeline.md) | 是 | 指定的构建号 |
| properties | List&lt;[构建模型-表单元素属性](obtain-the-manual-start-parameters-of-the-pipeline.md)&gt; | 是 | 启动表单元素列表 |

## BuildNo

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| buildNoType | ENUM\(CONSISTENT, SUCCESS\_BUILD\_INCREMENT, EVERY\_BUILD\_INCREMENT, \) | 否 | buildNoType |
| buildNo | integer | 否 | buildNo |
| required | boolean | 否 | required |

## 构建模型-表单元素属性

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| defaultValue | object | 是 | 默认值 |
| containerType | [BuildContainerType](obtain-the-manual-start-parameters-of-the-pipeline.md) | 否 | 构建机类型下拉 |
| glob | string | 否 | 自定义仓库通配符 |
| replaceKey | string | 否 | 替换搜索url中的搜素关键字 |
| readOnly | boolean | 否 | 是否只读 |
| label | string | 否 | 元素标签 |
| type | ENUM\(STRING, TEXTAREA, ENUM, DATE, LONG, BOOLEAN, SVN\_TAG, GIT\_REF, MULTIPLE, CODE\_LIB, CONTAINER\_TYPE, ARTIFACTORY, SUB\_PIPELINE, CUSTOM\_FILE, PASSWORD, TEMPORARY, \) | 是 | 元素类型 |
| required | boolean | 是 | 是否必须 |
| repoHashId | string | 否 | repoHashId |
| scmType | ENUM\(CODE\_SVN, CODE\_GIT, CODE\_GITLAB, GITHUB, CODE\_TGIT, \) | 否 | 代码库类型下拉 |
| relativePath | string | 否 | relativePath |
| propertyType | string | 否 | 元素模块 |
| options | List&lt;[构建模型-下拉框表单元素值](obtain-the-manual-start-parameters-of-the-pipeline.md)&gt; | 否 | 下拉框列表 |
| searchUrl | string | 否 | 搜索url, 当是下拉框选项时，列表值从url获取不再从option获取 |
| id | string | 是 | 元素ID-标识符 |
| placeholder | string | 否 | 元素placeholder |
| properties | object | 否 | 文件元数据 |
| desc | string | 否 | 描述 |

## BuildContainerType

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| os | ENUM\(MACOS, WINDOWS, LINUX, \) | 否 | os |
| buildType | ENUM\(ESXi, MACOS, DOCKER, IDC, PUBLIC\_DEVCLOUD, TSTACK, THIRD\_PARTY\_AGENT\_ID, THIRD\_PARTY\_AGENT\_ENV, THIRD\_PARTY\_PCG, THIRD\_PARTY\_DEVCLOUD, GIT\_CI, AGENT\_LESS, \) | 否 | buildType |

## 构建模型-下拉框表单元素值

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| value | string | 是 | 元素值名称-显示用 |
| key | string | 是 | 元素值ID-标识符 |

