# 流水线执行常见问题

## Q3: 流水线的各个状态代表什么意思？

流水线的状态汇总如下：

![](../../../.gitbook/assets/image-20220301101202-uphlD.png)

## Q4: 蓝盾流水线进度条是如何计算的？

进度条是蓝盾前端根据流水线相关的数据做出的预估。此进度不是准确的时间，仅供参考。

![](../../../.gitbook/assets/进度条.png)

## Q7: 多个job是共用一个workspace吗？

如果用的单构建机（私有构建机），多个job就会共用一个 workspace 目录。

如果是公共构建机，那么每个job在workspace下会有一个单独的目录 。

私有构建机和公共构建机，默认每个流水线都建立一个独立的 workspace 目录。



## Q8：如何获取构建产物的URL

http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/${项目名称}/${BK\_CI\_PIPELINE\_ID}/${BK\_CI\_BUILD\_ID}/{你的artifacts文件名}



---

## Q11: 执行时，参数下拉列表里的值能通过自定义的接口获取吗？

不支持接口自定义

---



