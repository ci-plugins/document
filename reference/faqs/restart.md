## Q1：机器需要重启，要如何关闭服务

通常来说重启前没有特殊操作，直接进行重启即可。





## Q2：重启后如何确认服务已经恢复

重启后的恢复检查操作，可以参考文档

[机器重启](https://bk.tencent.com/docs/document/6.0/127/7582)



## Q3：bkiam v3 failed

![](../../.gitbook/assets/bkiam_failed.png)

机器重启时最常见报错。蓝鲸蓝盾的各服务通常重启时都会自动拉起服务，但是 SaaS 服务并不会自动启动，需要手动启动。

中控机执行 ``` /data/install/bkcli start saas-o```

建议可以将该重启命令写入开机执行脚本中。
