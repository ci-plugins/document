# Edit the associated code base

### Request method/request path

#### PUT /ms/openapi/api/apigw/v3/repositories/{projectId}/{repositoryHashId}

### Resource description

#### Edit the associated code base

### Input parameter description

#### Body parameter

| Parameter name | Parameter type                                               | must | Parameter description | Default value |
| :------------- | :----------------------------------------------------------- | :--- | :-------------------- | :------------ |
| body           | [Code base Model - polymorphic base class](edit-the-associated-code-base.md) | is   | Code base model       |               |

#### Path parameter

| Parameter name   | Parameter type | must | Parameter description | Default value |
| :--------------- | :------------- | :--- | :-------------------- | :------------ |
| projectId        | string         | is   | Item ID               |               |
| repositoryHashId | string         | is   | Code base hash ID     |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [Data return wrapper model Boolean](edit-the-associated-code-base.md) |

#### Request sample

```
curl -X PUT '[Please replace API address bar request address]' 
```

#### HEADER example

```
accept: application/json Content-Type: application/json 
```

### Return example -200

```
{  "data" : true,  "message" : "String",  "status" : 0 } 
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

## Data return wrapper model Boolean

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | boolean        | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
