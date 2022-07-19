# 使用前必读

## **返回值**

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



## **开启 acces_token 认证**

API 调用需要携带access_Token。需要先修改配置文件，开启access_Token认证后才可以获取到口令。

登录CI服务器，编辑配置文件 /data/bkce/etc/ci/common.yml 的 auth 段下的 accessToken 段的内容。示例如下

```
  accessToken:
    enabled: false
    secret: ea0950b9-79e3-4193-8bf3-1f22856ca075
    expirationTime: 86400000
```



![image-20220707143212672](<../../.gitbook/assets/common.yml_demo.png>)





## **认证方式**

每个API调用都需要认证，请在query参数中携带access_Token，access_Token通过调用/ms/auth/api/user/token/get接口获取



**accessToken 获取示例**

浏览器访问  https://{域名}/ms/auth/api/user/token/get  获取

返回示例如下。

```javascript
{
    "userId" : "testUserId",
    "expirationTime" : 1630565380912,
    "accessToken" : "PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D"
}

若出现：
{"status": 401,"data": "","result":true,"message": "用户权限验证失败。"}
请先网页登录bk-ci
```



**API请求示例**

需添加 header 信息 X-DEVOPS-UID：用户名

```javascript
GET https://{域名/ip}/ms/openapi/api/apigw/v3/projects?access_token=PryTxowDezaM6u1QE1KDeZXiDH%2Bayb%2BabHZHOYLR8%2B8Md9QhAXrUrs2z3U4%2FZ3p9CvP4ObZjZJJ2VdNWQqgX3qeQ1TBK7ADhNXRVWn4q2Q0%3D -H "X-DEVOPS-UID: admin"

1)若出现：
Verification failed : token过期错误: Access token expired in: 1630919127633
因access_token已过期，请重新生成。
2)若出现：
Request accessToken is empty.
请检查是否在query参数中携带access_token
3)若出现：
verification failed : token参数非法错误: Access token illegal
请检查access_token是否输入正确 
```



