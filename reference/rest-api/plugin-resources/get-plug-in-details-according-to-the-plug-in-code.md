# Get plug-in details from the plug-in code

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/atoms/{atomCode}

### Resource description

#### Get plug-in details from the plug-in code

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| atomCode       | string         | is   | Plug-in code          |               |

#### response

| HTTP code | description          | Parameter type                                 |
| :-------- | :------------------- | :--------------------------------------------- |
| 200       | successful operation | The data returns the wrapper model AtomVersion |

#### Request sample

```
curl -X GET '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "versionContent" : "String",  "flag" : true,  "modifier" : "String",  "description" : "String",  "language" : "String",  "yamlFlag" : true,  "atomId" : "String",  "atomStatus" : "String",  "initProjectCode" : "String",  "codeSrc" : "String",  "htmlTemplateVersion" : "String",  "projectCode" : "String",  "releaseType" : "String",  "pkgName" : "String",  "jobType" : "String",  "atomType" : "String",  "classifyName" : "String",  "userCommentInfo" : {  "commentFlag" : true,  "commentId" : "String"  },  "summary" : "String",  "recommendFlag" : true,  "editFlag" : true,  "creator" : "String",  "defaultFlag" : true,  "docsLink" : "String",  "os" : "string",  "updateTime" : "String",  "privateReason" : "String",  "version" : "String",  "logoUrl" : "String",  "atomCode" : "String",  "labelList" : [ {  "createTime" : 0,  "labelType" : "String",  "updateTime" : 0,  "id" : "String",  "labelName" : "String",  "labelCode" : "String"  } ],  "createTime" : "String",  "visibilityLevel" : "String",  "frontendType" : "ENUM",  "name" : "String",  "repositoryAuthorizer" : "String",  "publisher" : "String",  "classifyCode" : "String",  "category" : "String",  "dailyStatisticList" : [ {  "dailySuccessNum" : 0,  "statisticsTime" : "String",  "dailyFailNum" : 0,  "dailyFailRate" : "parse error",  "dailyDownloads" : 0,  "totalDownloads" : 0,  "dailySuccessRate" : "parse error",  "dailyFailDetail" : {  "string" : "string"  }  } ]  },  "message" : "String",  "status" : 0 } 
```

## The data returns the wrapper model AtomVersion

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | AtomVersion    | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |

## AtomVersion

| Parameter name       | Parameter type                   | must | Parameter description                                        |
| :------------------- | :------------------------------- | :--- | :----------------------------------------------------------- |
| versionContent       | string                           | no   | Version log                                                  |
| flag                 | boolean                          | no   | Whether a label can be installed                             |
| modifier             | string                           | no   | modifier                                                     |
| description          | string                           | no   | Plug-in description                                          |
| language             | string                           | no   | Development language                                         |
| yamlFlag             | boolean                          | no   | yaml can be marked true: yes, false: no                      |
| atomId               | string                           | no   | Plug-in ID                                                   |
| atomStatus           | string                           | is   | Plug-in status                                               |
| initProjectCode      | string                           | no   | The initialization project of the plug-in                    |
| codeSrc              | string                           | no   | Code base link                                               |
| htmlTemplateVersion  | string                           | no   | Front-end rendering template version (1.0 stands for inventory plug-in rendering template version) |
| projectCode          | string                           | no   | Debug project for the plug-in                                |
| releaseType          | string                           | no   | Publication type                                             |
| pkgName              | string                           | no   | Plug-in package name                                         |
| jobType              | string                           | no   | Applicable Job type                                          |
| atomType             | string                           | no   | Plug-in type                                                 |
| classifyName         | string                           | no   | Plug-in class name                                           |
| userCommentInfo      | User review information          | no   | User review information                                      |
| summary              | string                           | no   | Plug-in introduction                                         |
| recommendFlag        | boolean                          | no   | Recommended Value true: recommended, false: not recommended  |
| editFlag             | boolean                          | no   | Editable or not                                              |
| creator              | string                           | no   | founder                                                      |
| defaultFlag          | boolean                          | no   | Whether to be the default plug-in (The default plug-in is visible to all items by default) true: default plug-in false: common plug-in |
| docsLink             | string                           | no   | Link to plug-in specification documentation                  |
| os                   | List                             | no   | Operating system                                             |
| updateTime           | string                           | no   | Modification time                                            |
| privateReason        | string                           | no   | Plug-in codebase is not open source                          |
| version              | string                           | no   | Version number                                               |
| logoUrl              | string                           | no   | logo address                                                 |
| atomCode             | string                           | no   | Plug-in identification                                       |
| labelList            | List< tag information >          | no   | Tag list                                                     |
| createTime           | string                           | no   | Creation time                                                |
| visibilityLevel      | string                           | no   | Project visibility. PRIVATE: private LOGIN_PUBLIC: Open source for login users |
| frontendType         | ENUM(HISTORY, NORMAL, SPECIAL, ) | no   | Front-end UI rendering                                       |
| name                 | string                           | no   | Plug-in name                                                 |
| repositoryAuthorizer | string                           | no   | Plug-in code base owner                                      |
| publisher            | string                           | no   | publisher                                                    |
| classifyCode         | string                           | no   | Plug-in classification code                                  |
| category             | string                           | no   | Plug-in category                                             |
| dailyStatisticList   | List< Daily Statistics >         | no   | Daily statistics list                                        |

## User review information

| Parameter name | Parameter type | must | Parameter description                |
| :------------- | :------------- | :--- | :----------------------------------- |
| commentFlag    | boolean        | is   | Commented or not true: yes false: no |
| commentId      | string         | no   | Comment ID                           |

## Label information

| Parameter name | Parameter type | must | Parameter description                                        |
| :------------- | :------------- | :--- | :----------------------------------------------------------- |
| createTime     | integer        | no   | Creation date                                                |
| labelType      | string         | is   | Category ATOM: plug-in TEMPLATE: template IMAGE: image IDE_ATOM:IDE plug-in |
| updateTime     | integer        | no   | Update date                                                  |
| id             | string         | is   | Tag ID                                                       |
| labelName      | string         | is   | Label name                                                   |
| labelCode      | string         | is   | Tag code                                                     |

## Daily statistics

| Parameter name   | Parameter type | must | Parameter description                                     |
| :--------------- | :------------- | :--- | :-------------------------------------------------------- |
| dailySuccessNum  | integer        | no   | Number of successful executions per day                   |
| statisticsTime   | string         | no   | The statistical time is in the format yyyy-MM-dd HH:mm:ss |
| dailyFailNum     | integer        | no   | Number of execution failures per day                      |
| dailyFailRate    | number         | no   | Daily execution failure rate                              |
| dailyDownloads   | integer        | no   | Daily downloads                                           |
| totalDownloads   | integer        | no   | Total downloads                                           |
| dailySuccessRate | number         | no   | Daily execution success rate                              |
| dailyFailDetail  | object         | no   | Daily execution failure details                           |
