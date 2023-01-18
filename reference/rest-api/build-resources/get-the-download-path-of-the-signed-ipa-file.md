# Obtain the download path of the signed IPA file

### Request method/request path

#### GET /ms/openapi/api/apigw/v3/sign/ipa/{resignId}/downloadUrl

### Resource description

#### Obtain the download path of the signed IPA file

### Input parameter description

#### Path parameter

| Parameter name | Parameter type | must | Parameter description | Default value |
| :------------- | :------------- | :--- | :-------------------- | :------------ |
| resignId       | string         | is   | Signature task ID     |               |

#### response

| HTTP code | description          | Parameter type                                               |
| :-------- | :------------------- | :----------------------------------------------------------- |
| 200       | successful operation | [The data is returned to the wrapper model String](get-the-download-path-of-the-signed-ipa-file.md) |

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
{  "data" : "String",  "message" : "String",  "status" : 0 } 
```

## The data is returned to the wrapper model String

| Parameter name | Parameter type | must | Parameter description |
| :------------- | :------------- | :--- | :-------------------- |
| data           | string         | no   | data                  |
| message        | string         | no   | Error message         |
| status         | integer        | is   | Status code           |
