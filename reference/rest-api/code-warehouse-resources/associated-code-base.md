# Associated code base

### Request method/request path

#### POST /ms/openapi/api/apigw/v3/repositories/{projectId}

### Resource description

#### Associated code base

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Code base Model - polymorphic base class](associated-code-base.md) | is   | Code base model       |               |

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId      | string         | is   | Item ID               |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data returns wrapper model code base model-ID](associated-code-base.md) |

#### Request sample

```
curl -X POST '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : {  "hashId" : "String"  },  "message" : "String",  "status" : 0 } 
```

## Code base Model - polymorphic base class

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| startPrefix    | string         | no   | startPrefix           |
| aliasName      | string         | no   | aliasName             |
| formatURL      | string         | no   | formatURL             |
| legal          | boolean        | no   | legal                 |
| credentialId   | string         | no   | credentialId          |
| userName       | string         | no   | userName              |
| projectName    | string         | no   | projectName           |
| projectId      | string         | no   | projectId             |
| url            | string         | no   | url                   |
| repoHashId     | string         | no   | repoHashId            |

## Data returns wrapper model code base model-ID

| Parameter name | Parameter type                                 | must | Parameter description |
| :------------- | :--------------------------------------------- | :--- | :-------------------- |
| data           | [Code base model -ID](associated-code-base.md) | no   | data                  |
| message        | string                                         | no   | Error message         |
| status         | integer                                        | is   | Status code           |

## Code base model -ID

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| hashId         | string         | is   | Code base hash ID     |
