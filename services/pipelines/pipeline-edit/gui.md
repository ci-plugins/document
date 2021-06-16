# 流水线图形化编排

## Stage操作集合

### 为Stage开启准入

在完整的CI/CD生命周期中，我们难免会有一些期望人工介入审核的步骤，Stage准入特性可以允许你在流水线运行到某个Stage之前暂停流程，人工介入后可以继续。

#### 开启方法

在编辑流水线时，对已有的某个Stage左上角的闪电ICON点击进入Stage准入属性面板

![](../../../.gitbook/assets/image%20%2850%29.png)

![](../../../.gitbook/assets/image%20%2849%29.png)

#### 开启后的效果

* 如果某个构建任务处于Stage准入审核时，那这个构建任务将成为“STAGE\_SUCCESS”状态，可参考[流水线状态信息汇总](../pipeline-build-detail/status.md#pipeline-zhuang-tai)

