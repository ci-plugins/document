# Job

Job，可以运行在一个构建环境里，比如运行在 macOS；也可以作为不需要构建环境的普通任务调度编排。它有如下特性：

* 由多个 Tasks\(插件\)组成；
* 一个 Task 失败，则该 Job 失败，其余 Task 将不会运行；

![](../../.gitbook/assets/image%20%2815%29.png)

### WORKSPACE <a id="WORKSPACE"></a>

每个 Job 都有自己的 WORKSPACE，WORKSPACE 就是该 Job 下所有插件的运行根目录。

> 如果一个 Job 中包含了“子流水线调用”插件，那该子流水线下的 Job 的 WORKSPACE 也会遵循上述原则，完全独立，不会跟父流水线的 WORKSPACE 冲突。

### Job 的通用选项 <a id="Job &#x7684;&#x901A;&#x7528;&#x9009;&#x9879;"></a>

#### 流程控制选项 <a id="&#x6D41;&#x7A0B;&#x63A7;&#x5236;&#x9009;&#x9879;"></a>

通过高级流程控制，可以定义 Job 的运行逻辑。

![](../../.gitbook/assets/image%20%282%29.png)

#### 互斥组 <a id="&#x4E92;&#x65A5;&#x7EC4;"></a>

互斥组是为了解决并发构建使用同一构建机时的资源冲突问题而设计的，对不同流水线的不同 Job 设置同一个互斥组。

![](../../.gitbook/assets/image%20%286%29.png)

### 接下来你可能需要 <a id="&#x63A5;&#x4E0B;&#x6765;&#x4F60;&#x53EF;&#x80FD;&#x9700;&#x8981;"></a>

* [Task](task.md)
* [Stage](stage.md)

