# **移动端版本体验使用指南**

## **版本体验接入**
### **配置蓝盾流水线**
![image-client-experience-gettingstarted.png](../../.gitbook/assets/image-client-experience-gettingstarted.png)

#### **配置ipa/apk安装包**
待上传的安装包路径：
- 从本次构建的路径下选择要上传的安装包。
- 支持ipa文件、apk文件和压缩包。

#### **配置应用信息**
- 应用名称：
    - 版本体验上所展示的应用名称。当该配置项为空时，插件会自动获取ipa/apk包内置的应用名。
- 版本号：
    - 版本体验上所展示的版本号。当该配置项为空时，插件会自动获取ipa/apk包内置的版本号。
- 应用描述：
    - 该体验版本的详细描述。可以完全由业务方自定义。常用的描述有：应用的简介；版本的变更日志等等。
- 产品负责人：
    - 支持从企业微信拉取通讯录，支持多选。

#### **配置体验范围**
- 体验结束日期：
    - 体验结束日期：超过这个日期后体验会自动过期并且不能再被下载。
    - 选择相对时间或绝对时间
        - 相对时间：流水线当前构建时间加上相对时间，单位（天），即为体验结束日期。
        - 绝对时间：所选择的日期，即为体验结束日期 。
- 体验人员：
    - 支持单个人员的选择。
    - 支持按部分选择体验人员。

#### **配置通知方式** 

- 通知方式：
    - 完成体验发布后，通过应用号发送通知。
    - 通知人员支持选择应用服务人或体验人员。


### **版本体验应用使用**
从企业微信工作台中选择「版本体验」应用。


![image-client-experience-app1.png](../../.gitbook/assets/image-client-experience-app1.png)


选择需要体验的应用，点击「下载」可快速下载应用，ipa会提示跳转safari进行下载。


![image-client-experience-app2.png](../../.gitbook/assets/image-client-experience-app2.png)
 

 点击应用标题即可进入应用详情，应用负责人可对应用进行管理：
   - 产品负责人有权限修改人员信息和体验过期时间。
   - 体验人员仅可查看和下载该应用。

达到过期时间后，体验人员将无法从版本体验首页看到该应用，产品负责人仍然可查看该应用，同时该应用会有一个“已过期”的TAG。

(如果应用有多个版本，可通过历史版本进行下载。)


![image-client-experience-app3.png](../../.gitbook/assets/image-client-experience-app3.png)

版本体验插件在勾选「通知」后，在应用上传成功后给有权限的人员发送企业微信通知消息，点击立即前往可快速访问到「版本体验」应用。

![image-client-experience-app4.png](../../.gitbook/assets/image-client-experience-app4.png)