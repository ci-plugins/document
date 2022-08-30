

## 蓝盾功能使用指引

* 蓝盾产品功能介绍：[产品功能](../..//services/console.md)

* 蓝盾流水线功能使用示例：[示例](../..//tutorials/examples)

* 蓝盾流水线常见场景案例：[场景实践](../..//tutorials/scene)

---

## 故障排查流程自助：

1. 问答指引FAQ：[FAQ](../../reference/faqs)  

2. FAQ无法找到解决方案，请按如下要求提供反馈信息：

   2.1  提供蓝盾版本号（蓝盾首页可获取）

   2.2  问题现象描述及报错截图（是否必现，操作内容，配置截图等）

   2.3  提供构建日志   （获取方式如下）

   2.4  提供服务日志   （可选）

---

### 构建日志收集

构建日志存放在构建机中，构建日志存放的路径位于：

**私有构建机**：{agent 安装目录}/logs/{构建号}

**公共构建机**：/data/bkce/logs/ci/docker/{构建号}



**私有构建机中，agent安装目录怎么看**：

蓝盾---环境管理---节点---{对应使用的构建机}---安装路径

![agent安装目录](D:\document\document\.gitbook\assets\build_log_url.png)

**构建号怎么看**：

流水线 URL 中，最后一串以 b- 开头的字符串即为构建号

![构建号](D:\document\document\.gitbook\assets\build_id.png)

### 服务日志收集

进入蓝盾后台服务机器

```find /data/bkce/logs/ci/ -name \*-devops.log -o -name \*-devops-error.log |xargs tar zcvf /root/bkci-log.tar.gz```

然后发送打包好的 **/root/bkci-log.tar.gz** 日志

### 页面报错信息收集

如遇到页面报错，浏览器 F12 打开控制台后再复现一次请求操作，并且：

①、打开 network 标签，点击错误的请求并截图。

![error_request](D:\document\document\.gitbook\assets\error_request.png)



②、打开 console 标签，并截图。

![error_console](D:\document\document\.gitbook\assets\weberror_console.png)



