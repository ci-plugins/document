# Trigger

bk-ci 支持多种方式触发流水线：

* API 触发
* 代码库事件触发
* 子流水线调用插件触发
* 定时触发
* 手动触发
* 远程触发

不同的触发方式下，系统内置的 BK\_CI\_START\_TYPE 取值也不同，你可以根据需要在流水线后续插件中使用该值：

| 触发方式 | BK\_CI\_START\_TYPE 值 |
| :--- | :--- |
| 远程触发 | REMOTE |
| 手动触发 | MANUAL |
| 定时触发 | TIME\_TRIGGER |
| 子流水线插件触发 | PIPELINE |
| 代码库 HOOK 触发 | WEB\_HOOK |
| API 触发 | SERVICE |

![](../../.gitbook/assets/image%20%2826%29.png)

