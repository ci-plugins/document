# Stage

为了更清晰的描述 CI 流程，我们引入 Stage（阶段）的概念。

* 由多个 Jobs（作业）组成；
* 同一个 Stage 下的 Job 执行方式为并行，由于 Job 之间是相互独立的，某个 Job 失败后，其它的 Job 会被运行到完成；
* 一个 Job 失败，则该 Stage 失败。

![](<../../.gitbook/assets/image (25) (1) (2) (1).png>)

## Stage 的通用选项 <a href="#stage-de-tong-yong-xuan-xiang" id="stage-de-tong-yong-xuan-xiang"></a>

### Fastkill <a href="#fastkill" id="fastkill"></a>

开启 Fastkill 之后，当 Job 失败时立即结束当前 Stage。

### 流程控制选项 <a href="#liu-cheng-kong-zhi-xuan-xiang" id="liu-cheng-kong-zhi-xuan-xiang"></a>

通过高级流程控制，可以定义 Job 的运行逻辑。

![](<../../.gitbook/assets/image (43).png>)

## 接下来你可能需要 <a href="#jie-xia-lai-ni-ke-neng-xu-yao" id="jie-xia-lai-ni-ke-neng-xu-yao"></a>

* [Task](task.md)
* [Job](job.md)
