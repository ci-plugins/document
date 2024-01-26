# 云环境异常定位

## 关键词：云环境、corefile <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

## 业务挑战 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

服务上云后，游戏进程发生core，由于pod节点漂移等原因，找到corefile并断点调试比较困难。

## 蓝盾优势 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

通过蓝盾自动拉起调试节点，并邮件输出coredump内容给后台开发，如果有断点需求，可以在集群master节点登录调试pod，进行调试定位。

## 解决方案 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

1、整体流程如下：

● node机监控是否产生corefile

思路：编写corefile文件监控脚本，利用蓝鲸“作业平台”-定时任务功能，当有corefile新增时，远程触发蓝盾流水线。

脚本核心部分样例，仅供参考

file\_list=`find /data/corefile -mmin -3 -name "core_*"`

● 远程触发蓝盾流水线后，根据node ip和镜像版本号等信息，部署调试pod

● 调试pod启动后，通过kubectl命令，获取coredump内容

● 发送邮件or机器人等方式，通知开发人员

● 开发人员自助登录调试pod，排查问题

![图1](../../.gitbook/assets/scene-Cloud-anomaly-location-a.png)

2、蓝盾流水线配置

● 解析文件名

通过解析corefile文件名，获取命名空间、文件名、镜像版本号等信息。

● 启动调试pod

根据node节点、镜像版本等参数，启动调试pod

● 获取coredump内容

通过kubectl命令，获取coredump内容

kubectl -n NAMESPACE logs POD\_NAME -c corefile-debug

![图1](../../.gitbook/assets/scene-Cloud-anomaly-location-b.png)
