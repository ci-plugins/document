# 流水线执行常见问题

## Q1：流水线之间如何做互斥

流水线的互斥及排队可以参考

[流水线互斥](https://docs.bkci.net/tutorials/scene/pipeline-exclusion-queue)

## Q2：有pipeline A,可单独执行，我又有pipeline B,B里面会去调用A，等待A的一个结果，这种如何做互斥呢

使用 call pipeline 调用子流水线。选择同步执行即可，触发后继续等待执行结果，有结果后再决定是否继续。



## Q3: 流水线的各个状态代表什么意思？

流水线的状态汇总如下：

![](../../../.gitbook/assets/image-20220301101202-uphlD.png)

## Q4: 蓝盾流水线进度条是如何计算的？

进度条是蓝盾前端根据流水线相关的数据做出的预估。此进度不是准确的时间，仅供参考。

![](../../../.gitbook/assets/进度条.png)

## Q5: 如何获取流水线id？

流水线url中，pipeline后的参数分别为项目id和流水线id。如：http://devops.bktencent.com/console/pipeline/iccentest/p-8f3d1b399897452e901796cf4048c9e2/history 中，iccentest 为项目id，p-xxx 即为流水线id。

## Q6: 流水线执行失败了，插件为什么没有重试按钮？

只有最新一次的构建可以重试。

## Q7: 多个job是共用一个workspace吗？

如果用的单构建机（私有构建机），多个job就会共用一个 workspace 目录。

如果是公共构建机，那么每个job在workspace下会有一个单独的目录 。

私有构建机和公共构建机，默认每个流水线都建立一个独立的 workspace 目录。



## Q8：如何获取构建产物的URL

http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/${项目名称}/${BK\_CI\_PIPELINE\_ID}/${BK\_CI\_BUILD\_ID}/{你的artifacts文件名}





## Q9:流水线的历史页面，能显示自定义内容吗？

可以在流水线里加个shell**插件**，通过设置`BK_CI_BUILD_REMARK`这全局变量的值，来实现想要的备注。流水线结束了，该字段才会显示。

并且在流水线历史页面添加备注字段。具体请参考：

[使用备注变量](https://docs.bkci.net/services/pipelines/pipeline-variables/pipeline-variables-remark)

## Q10: 选中的参数改变的时能否隐藏其他参数，比如我operator选中build，tag参数隐藏掉，就像js里option组件的change event

![](../../../.gitbook/assets/企业微信截图_1634710197325.png)

暂时还不支持

---

## Q11: 执行时，参数下拉列表里的值能通过自定义的接口获取吗？

不支持接口自定义

---



