# API Usage Examples

In this chapter, we will use the **OPNEAPI-Project Resources** to get project information, create projects, and modify projects** to demonstrate how to use the API via Curl or Python.

## **Curl example**

1、access_token should be replaced by the password you get

2, POST, PUT and other APIs that need to carry the body, the body is required. If the body is a non-essential parameter, you can pass an empty body, for example: -d '{}'

3、For the {projectId} and other parameters in the API, you need to replace them with the corresponding names.

---

**GET**

```bash
curl -X GET http://devops.bktencent.com/ms/openapi/api/apigw/v3/projects/demo?access_token=%2BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%2B7%2BTZihy1Tg5iLj5Gsj%2FdCC51MakqW0UGQ%3D%3D -H "accept: application/json" -H "Content-Type: application/json" -H "X-DEVOPS-UID: admin"
```



**POST**

```bash
curl -X POST http://devops.bktencent.com//ms/openapi/api/apigw/v3/projects?access_token=%252BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%252B7%252BTZihy1Tg5iLj5Gsj%252FdCC51MakqW0UGQ%253D%253D -H "accept: application/json" -H "Content-Type: application/json" -H "X-DEVOPS-UID: admin" -d '{"englishName":"apitest","deptName":"apitest","centerId":0,"secrecy":false,"kind":0,"projectType":0,"deptId":0,"description":"apitest","bgName":"apitest","projectName":"apitest"}'
```



**PUT**

```bash
curl -X PUT http://devops.bktencent.com//ms/openapi/api/apigw/v3/projects/apitest2?access_token=%252BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%252B7%252BTZihy1Tg5iLj5Gsj%252FdCC51MakqW0UGQ%253D%253D -H "accept: application/json" -H "Content-Type: application/json" -H "X-DEVOPS-UID: admin" -d '{"englishName":"apitest2","deptName":"apitest2","centerId":0,"secrecy":false,"kind":0,"projectType":0,"deptId":0,"description":"apitest2","bgName":"apitest2","projectName":"apitest2"}'
```





## **Python example**

1、access_token should be replaced by the password you get.

2, POST, PUT and other APIs that need to carry body, body is required. If the body is a non-essential parameter, you can pass an empty body, for example: body={}

3、For the {projectId} and other parameters in the API, you need to replace them with the corresponding names.

---

**GET获取项目信息**

```python
import requests

# CI domain
hostname = "http://devops.bktencent.com/"
# API url
api_url = "/ms/openapi/api/apigw/v3/projects/demo"
#token
token = "%2BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%2B7%2BTZihy1Tg5iLj5Gsj%2FdCC51MakqW0UGQ%3D%3D"
url = hostname + api_url
params = {'access_token': token}
headers = {"Content-Type": "application/json",
           "accept": "application/json",
           "X-DEVOPS-UID": "admin"}
r = requests.get(url, headers=headers, params=params)
print(r.text)
```



**POST创建项目**

```python
import requests

# CI domain
hostname = "http://devops.bktencent.com/"
# API url
api_url = "/ms/openapi/api/apigw/v3/projects"
# token 
token = "%2BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%2B7%2BTZihy1Tg5iLj5Gsj%2FdCC51MakqW0UGQ%3D%3D"
url = hostname + api_url
body = {
    "englishName": "apitest",
    "deptName": "apitest",
    "centerId": 0,
    "secrecy": False,
    "kind": 0,
    "projectType": 0,
    "deptId": 0,
    "description": "apitest",
    "bgName": "apitest",
    "projectName": "apitest",
    "bgId": 0,
    "centerName": "apitest"
}
params = {
    'access_token': token
}
headers = {"Content-Type": "application/json",
           "accept": "application/json",
           "X-DEVOPS-UID": "admin"}
r = requests.post(url=url, json=body, headers=headers, params=params)
print(r.text)
```



**PUT修改项目**

```python
import requests

# CI domain
hostname = "http://devops.bktencent.com/"
# API url
api_url = "/ms/openapi/api/apigw/v3/projects/apitest"
# token 
token = "%2BxeaZC44Jt0tCbF5a3ZglMOvBxROaHtKLbFBrJsZp9KC4QhcsQwX%2B7%2BTZihy1Tg5iLj5Gsj%2FdCC51MakqW0UGQ%3D%3D"
url = hostname + api_url
body = {
    "englishName": "apitest2",
    "deptName": "apitest2",
    "centerId": 0,
    "secrecy": False,
    "kind": 0,
    "projectType": 0,
    "deptId": 0,
    "description": "apitest2",
    "bgName": "apitest2",
    "projectName": "apitest2",
}
params = {
    'access_token': token
}
headers = {"Content-Type": "application/json",
           "accept": "application/json",
           "X-DEVOPS-UID": "admin"}
r = requests.put(url=url, json=body, headers=headers, params=params)
print(r.text)
```

