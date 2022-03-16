# 蓝鲸FAQ

#### Q: 安装云区域agent报错：CALLBACK\_URL不符合规范，请联系运维人员修改，例：http://domain.com/backend

![](../../.gitbook/assets/企业微信截图_16407490269810.png)

请参考：[https://bk.tencent.com/s-mart/community/question/2184](https://bk.tencent.com/s-mart/community/question/2184)

#### Q: 安装云区域agent报错：账号\[root]不存在

![](../../.gitbook/assets/企业微信截图_16407586012478.png)

请参考：[https://bk.tencent.com/s-mart/community/question/3151?type=answer](https://bk.tencent.com/s-mart/community/question/3151?type=answer)

#### Q: 安装云区域agent报错：用户权限不足

![](../../.gitbook/assets/企业微信截图_16407674349324.png)

安装云区域agent的用户需要拥有作业平台快速执行脚本的权限

**Q: 安装proxy时报错, connection failed**

![](../../.gitbook/assets/企业微信截图_16342054001842.png)

需要把对应端口放开

![](../../.gitbook/assets/企业微信截图_16342055675666.png)

**Q: 能调整蓝鲸登录的过期时长吗**

占位**，待补充**

**Q: 如何调整作业平台内存使用量**

到作业平台机器上，将作业平台的env文件中JAVA\_OPTS修改为适合的内存大小，env文件为：/etc/sysconfig/bk-job-\*

![](../../.gitbook/assets/tapd_20452048_1643014538_32.png)

然后重启job： `systemctl restart bk-job.target`
