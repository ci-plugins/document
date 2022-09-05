# 流水线使用常见问题

## Q1: 流水线的各个状态代表什么意思？

流水线的状态汇总如下：

![](D:/document/outline/document/.gitbook/assets/image-20220301101202-uphlD.png)

## Q2: 蓝盾流水线进度条是如何计算的？

进度条是蓝盾前端根据流水线相关的数据做出的预估。此进度不是准确的时间，仅供参考。

![](D:/document/outline/document/.gitbook/assets/进度条.png)

## Q3: 如何获取流水线id？

流水线url中，pipeline后的参数分别为项目id和流水线id。如：http://devops.bktencent.com/console/pipeline/iccentest/p-8f3d1b399897452e901796cf4048c9e2/history 中，iccentest 为项目id，p-xxx 即为流水线id。

## Q4: 流水线执行失败了，插件为什么没有重试按钮？

只有最新一次的构建可以重试。

## Q5: 蓝盾流水线中的视图管理、标签管理有什么用？

对流水线进行分类，当流水线数量较多时，标签、视图会有更大作用。

## Q6: 查看日志时，如何查看时间戳？

查看日志页，Show/Hide Timestamp

![](D:/document/outline/document/.gitbook/assets/image-20220301101202-QERjn.png)

## Q7: 多个job是共用一个workspace吗？

如果用的单构建机（私有构建机），多个job就会共用一个 workspace 目录。

如果是公共构建机，那么每个job在workspace下会有一个单独的目录 。

私有构建机和公共构建机，默认每个流水线都建立一个独立的 workspace 目录。

## Q8：如何获取构建产物的URL

http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/${项目名称}/${BK\_CI\_PIPELINE\_ID}/${BK\_CI\_BUILD\_ID}/{你的artifacts文件名}

## Q9：流水线之间如何做互斥

流水线的互斥及排队可以参考

[流水线互斥](https://docs.bkci.net/tutorials/scene/pipeline-exclusion-queue)

## Q10：有pipeline A,可单独执行，我又有pipeline B,B里面会去调用A，等待A的一个结果，这种如何做互斥呢

使用 call pipeline 调用子流水线。选择同步执行即可，触发后继续等待执行结果，有结果后再决定是否继续

## Q11: 如何使用流水线的视图功能

视图可以将流水线分类，允许用户根据流水线的创建人或者流水线的名称来进行分类，多个条件之间支持与/或关系，条件的键值是include的逻辑，不支持模糊匹配以及正则表达式，比如当流水线的名称对应的键值为`vinco`时，会匹配到该项目中所有流水线名称中包含`vinco`字样的流水线

![](D:/document/outline/document/.gitbook/assets/image-20220125152014075.png)

![](D:/document/outline/document/.gitbook/assets/image-20220125152350168.png)

## Q12: 定时触发的流水线，时间显示不对，触发时间也不对

![](D:/document/outline/document/.gitbook/assets/wecom-temp-26d5087b12647b6801f5d8471eeb3ee6.png)请检查蓝盾服务器的时间是否正常

## Q13:流水线的历史页面，能显示自定义内容吗？

可以在流水线里加个shell**插件**，通过设置`BK_CI_BUILD_REMARK`这全局变量的值，来实现想要的备注。流水线结束了，该字段才会显示。

并且在流水线历史页面添加备注字段。具体请参考：

[使用备注变量](https://docs.bkci.net/services/pipelines/pipeline-variables/pipeline-variables-remark)

## Q14: 选中的参数改变的时能否隐藏其他参数，比如我operator选中build，tag参数隐藏掉，就像js里option组件的change event

![](D:/document/outline/document/.gitbook/assets/企业微信截图_1634710197325.png)

暂时还不支持

## Q15: 执行时，参数下拉列表里的值能通过自定义的接口获取吗？

不支持接口自定义