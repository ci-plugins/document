## Q1：bkiam v3 failed

![](../../.gitbook/assets/bkiam_failed.png)

机器重启时最常见报错。蓝鲸蓝盾的各服务通常重启时都会自动拉起服务，但是 SaaS 服务并不会自动启动，需要手动启动。

中控机执行 ``` /data/install/bkcli start saas-o```

建议可以将该重启命令写入开机执行脚本中。

