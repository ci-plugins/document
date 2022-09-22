## Q1：bkiam v3 failed

![](../../.gitbook\assets\bkiam_failed.png)

此错误一般是由于机器重启后，权限中心SaaS 未启动导致的。需要手动拉起 SaaS

中控机执行 ``` /data/install/bkcli start saas-o```

其他机器重启的需要的操作，请查看 [机器重启](https://bk.tencent.com/docs/document/6.0/127/7582)



## Q2：点击插件时报错：服务正在部署中，请稍候

![](../../.gitbook\assets\touch_plugin.png)

常见于 mongodb 异常导致。

中控机执行 ``` /data/install/bkcli restart mongod```

随后检查 mongodb 状态是否正常  ``` /data/install/bkcli status mongod```
