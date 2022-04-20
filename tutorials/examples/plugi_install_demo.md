# 插件安装指引

## 插件下载地址

**1、pushJobFile**

> 利用作业平台分发制品到目标服务器

https://github.com/ci-plugins/pushJobFile

编译环境：无编译环境

开发语言：java



**2、executeJob**

> 调用作业平台执行作业

https://github.com/ci-plugins/executeJob

编译环境：无编译环境

开发语言：java



**3、executeJobScript**

> 调用作业平台执行脚本

https://github.com/ci-plugins/executeJobScript

编译环境：无编译环境

开发语言：java



**4、sendEmail**

> 发送通知邮件

https://github.com/ci-plugins/sendEmail

编译环境：无编译环境

开发语言：java



**5、checkout**

> git 拉取代码

https://github.com/TencentBlueKing/ci-checkout

编译环境：编译环境（Linux+ macOS + Windows）

开发语言：java



**6、sendmsg**

> 1. 发送企业微信消息(需要配置ESB)
> 2. 发送邮件消息(需要配置ESB)
> 3. 发送企业微信群消息

https://github.com/wenchao-h/bkci-plugin-sendmsg

编译环境：（Linux + Windows + MacOS）

开发语言：Python

---

## 安装步骤

以安装 **pushJobFile** 插件为例，安装步骤基本一致。

### 一、下载安装包

按照插件下载地址，先下载好安装包。

![image-20220401160430568](./imgs/image-20220401160430568.png)

![image-20220401160511428](./imgs/image-20220401160511428.png)

---

### 二、进入工作台

路径：

蓝盾----->研发商店---->工作台

![image-20220401160738696](./imgs/image-20220401160738696.png)

---

### 三、新增插件

![image-20220401161007837](./imgs/image-20220401161007837.png)

名称：可以自定义填写。

标识：必须和要安装的插件安装包文件名一致。大小写也必须一致。

调试项目：选择调试插件的项目。

开发语言：选择插件开发的语言。

自定义前端：如果无需自定义前端，均选否即可。

---

### 四、插件配置

插件需要做的配置，GitHub 页面中均有介绍。https://github.com/TencentBlueKing/ci-pushJobFile

pushJobFile 需要配置：

1.插件配置
插件上架时，需要配置蓝鲸智云相关参数，路径：设置->私有配置

2.作业平台配置
请将蓝鲸持续集成平台后台微服务artifactory所在机器IP全部加入至作业平台的IP白名单中，在作业平台的“平台管理->IP白名单”中进行配置，生效范围选择文件分发，若artifactory扩容，需将扩容机器IP更新至白名单中。



**插件配置**

插件上架时，需要配置蓝鲸智云相关参数，路径：设置->私有配置

![image-20220401161404647](./imgs/image-20220401161404647.png)

在 蓝鲸中控机 中，按照 GitHub 中指引，获取相关变量。

```
source ${CTRL_DIR:-/data/install}/load_env.sh

echo "BK_APP_ID      $BK_CI_APP_CODE"
echo "BK_APP_SECRET  $BK_CI_APP_TOKEN"
echo "ESB_HOST       $BK_PAAS_PRIVATE_URL"
echo "JOB_HOST       $BK_JOB_PUBLIC_URL"

# 参考输出
BK_APP_ID      bk_ci
BK_APP_SECRET  略
ESB_HOST       http://paas.service.consul:80
JOB_HOST       http://job.bktencent.com:80
```

获取变量后，**新增配置** 填入各个变量

![image-20220401162406243](./imgs/image-20220401162406243.png)



**作业平台配置**

请将蓝鲸持续集成平台后台微服务artifactory所在机器IP全部加入至作业平台的IP白名单中，在作业平台的“平台管理->IP白名单”中进行配置，生效范围选择文件分发，若artifactory扩容，需将扩容机器IP更新至白名单中。



1、先在中控机中获取 artifactory 机器的 IP

cat /data/install/install.config| grep artifctory



2、在作业平台中，把IP添加至白名单

![image-20220401162613444](./imgs/image-20220401162613444.png)

![image-20220401163005167](./imgs/image-20220401163005167.png)

---

### 五、上架插件

配置完成后，返回工作台，选择上架插件

![image-20220401163151231](./imgs/image-20220401163151231.png)

按照指引填写各信息，并上传从 GitHub 获取到的插件安装包

![image-20220401163739926](./imgs/image-20220401163739926.png)

点击提交后，会进入到插件测试阶段。此处插件都是已经开发完成的，直接点击**继续**跳过测试即可。

![image-20220401163907672](./imgs/image-20220401163907672.png)

至此，插件 **pushJobFile**安装完毕，可以按照此流程继续安装其他插件。