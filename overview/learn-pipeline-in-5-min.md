# 5分钟读懂 BKCI 流水线

bk-ci 可以帮你快速实现一条持续交付流水线来编译、测试、部署你的应用，下面将通过教程和文档指南告诉你，怎么在 bk-ci 里配置和管理持续集成、持续交付（CI/CD）流水线。

下面为流水线的完整逻辑图：

![](../.gitbook/assets/image%20%283%29.png)



### Task（插件） <a id="Task&#xFF08;&#x63D2;&#x4EF6;&#xFF09;"></a>

即一个单独的任务，如拉取 GitHub 仓库代码。

### Job（作业） <a id="Job&#xFF08;&#x4F5C;&#x4E1A;&#xFF09;"></a>

可以运行在一个构建环境里，比如运行在 macOS；也可以作为不需要构建环境的普通任务调度编排。它有如下特性：

* 由多个 Tasks\(插件\)组成
* 一个 Task 失败，则该 Job 失败，其余 Task 将不会运行

![](../.gitbook/assets/image%20%2817%29.png)

### Stage（阶段） <a id="Stage&#xFF08;&#x9636;&#x6BB5;&#xFF09;"></a>

* 由多个 Job 组成
* 同个 Stage 下的 Job 并行执行，且 Job 与 Job 之间相互独立
* 当一个 Job 失败，则该 Stage 失败

![](../.gitbook/assets/image%20%2832%29.png)



### Pipeline（流水线） <a id="Pipeline&#xFF08;&#x6D41;&#x6C34;&#x7EBF;&#xFF09;"></a>

* 由多个 Stage 组成
* 同个 Pipeline 下的 Stage 串行执行，一个 Stage 失败，将不会执行后续 Stage
* 当一个 Stage 失败，则该 Pipeline 失败

### Materials and Triggers\(材料和触发\) <a id="Materials and Triggers(&#x6750;&#x6599;&#x548C;&#x89E6;&#x53D1;)"></a>

#### Materials（源材料） <a id="Materials&#xFF08;&#x6E90;&#x6750;&#x6599;&#xFF09;"></a>

流水线执行就像做饭一样，需要材料（米），有了材料，才能做出可口的饭菜。向流水线中添加了拉取代码库的相关插件后（Git、SVN），这个流水线就有了材料。

#### Trigger（触发） <a id="Trigger&#xFF08;&#x89E6;&#x53D1;&#xFF09;"></a>

即流水线构建的触发方式，目前包括：手动触发、定时触发、代码库事件触发以及远程触发。

### 其它 <a id="&#x5176;&#x5B83;"></a>

#### 产出物 <a id="&#x4EA7;&#x51FA;&#x7269;"></a>

执行一次流水线构建，会有很多产出物出现，我们按照下面的维度进行了分类：

* 构件（Artifact） 顾名思义，就是编译或打包之后产生的二进制文件，包括镜像、版本压缩包、IPA 包、APK 包等等，利用插件你可以将构件归档到指定的仓库中。
* 代码检查报告

如果你的流水线中包含了 CodeCC 代码检查任务插件，那么你的流水线就会多出这样一个代码检查报告页面，该页面数据会随着你的流水线构建执行而不断刷新。

* 测试报告
* 安装程序
* 版本日志
* 文档

> 如果想在不同 Job 之间共享产出物，需要用到【Upload】和【Download】插件。

#### WORKSPACE <a id="WORKSPACE"></a>

在构建机上工作目录，所有与构建机相关的插件执行时的相对目录，在如下这些需要路径插件中，需要的也是 WORKSPACE 下的相对路径。

#### 节点 <a id="&#x8282;&#x70B9;"></a>

也称之为构建机，为了编译、测试或部署你的代码，你需要将至少 1 台 Agent 节点导入至 bk-ci，而随着团队规模的增长，这个数字将不断扩充。根据节点类型的不同，我们的任务也分为两类：

* 直接运行在节点上

你可以在添加 Job 时直接选择导入到 bk-ci 的第三方构建机（包含 macOS、Windows、Linux），流水线会在运行到对应 Job 时将任务分配到该构建机上。

* 运行在节点的 docker 内

当你的节点操作系统是 Linux 时，Job 详情页的**构建资源类型**会多出一个选项：Linux 构建镜像。选择这个选项，流水线会在运行到该 Job 后，通过以下方式来充分利用你的节点 CPU、MEM 等动态资源：

* 在分配到该 Job 的节点上运行 docker run 命令，将对应镜像启动后
* 把 WORKSPACE 挂载至 docker 内来进行编译构建
* Job 运行结束后，销毁该容器，WORKSPACE 保留

### 接下来你可能需要 <a id="&#x63A5;&#x4E0B;&#x6765;&#x4F60;&#x53EF;&#x80FD;&#x9700;&#x8981;"></a>

了解更多基础概念有助于你快速配置适合业务场景的流水线：

* [Task](terminology/task.md)
* [Job](terminology/job.md)
* [Stage](terminology/stage.md)
* [Variables](terminology/variables.md)
* [Trigger](terminology/trigger.md)

