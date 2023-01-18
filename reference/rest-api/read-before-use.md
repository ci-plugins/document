# Must read before use

## **Return code**

| Return code | Description |
| :--- | :--- |
| `200 OK` | Operation successful |
| `201 Created` | Created successfully|
| `400 Bad Request` | Parameter error, or parameter format error |
| `401 Unauthorized` | Authentication failed|
| `403 Forbidden` | The account does not have permission for this action or the project is set to not allow this action |
| `404 Not Found` | The resource does not exist, or the account may not have permission to the project (to prevent hackers from crashing the library to get the library list) |
| `405 Method Not Allowed` | There is no such interface |
| `409 Conflict` | Conflict with an existing object/content or an action that conflicts with a rule|
| `422 Unprocessable` | operation cannot be performed |
| `423 Locked` | Account is locked, or api request frequency exceeds limit |
| `429 Too Many Requests` | Requests are restricted |
| `500 Server Error` | Server error|

## **Authentication method**

Every API call needs authentication, please carry access\_token in query parameter, access\_token is obtained by calling /ms/auth/api/user/token/get interface, the return example is as follows.

```javascript
{
    "userId" : "testUserId",
    "expirationTime" : 1630565380912,
    "accessToken" : "PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D"
}
```

TOKEN example：

```javascript
GET https://{domain/ip}/ms/auth/api/user/token/get

If there is.
{"status": 401,"data": "","result":true,"message": "用户权限验证失败。"}
Please login to bk-ci first
```

API request demo：

```javascript
GET https://{domain/ip}/ms/openapi/api/apigw/v3/projects?access_token=PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D

1) If there is.
Verification failed : token expired error: Access token expired in: 1630919127633
Access_token has expired, please regenerate it.
2) If there is.
Request accessToken is empty.
Please check if the access_token is in the query parameter.
3) If: verification failed
verification failed : token parameter illegal error: Access token illegal
Please check whether access_token is entered correctly. 
```

