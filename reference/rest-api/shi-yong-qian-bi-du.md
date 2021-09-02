# 使用前必读

#### **返回值**

| 返回值 | 涵义 |
| :--- | :--- |
| `200 OK` | 操作成功 |
| `201 Created` | 创建成功 |
| `400 Bad Request` | 参数错误，或是参数格式错误 |
| `401 Unauthorized` | 认证失败 |
| `403 Forbidden` | 帐号并没有该操作的权限或者项目设置不允许该操作 |
| `404 Not Found` | 资源不存在，也可能是帐号没有该项目的权限（为防止黑客撞库获取库列表） |
| `405 Method Not Allowed` | 没有该接口 |
| `409 Conflict` | 与已存在的对象/内容冲突或者操作行为与规则相冲突 |
| `422 Unprocessable` | 操作不能进行 |
| `423 Locked` | 帐号被锁定，或api请求频率超限 |
| `429 Too Many Requests` | 请求被限流 |
| `500 Server Error` | 服务器出错 |



#### **认证方式**

每个API调用都需要认证，请在query参数中携带accessToken，accessToken通过调用/ms/auth/api/user/token/get接口获取，返回示例如下。

```javascript
{
    "userId" : "testUserId",
    "expirationTime" : 1630565380912,
    "accessToken" : "PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D"
}
```

TOKEN请求示例：

```text
GET https://{域名/ip}/ms/auth/api/user/token/get
```

API请求示例：

```text
GET https://{域名/ip}/api/v3/projects?accessToken=PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D
```



