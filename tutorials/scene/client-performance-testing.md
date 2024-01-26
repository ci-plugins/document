# 客户端自动化性能测试

## 关键词：自动化测试、PerfDog <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

## 业务挑战 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

PerfDog是一款移动平台的性能工具，支持Android和iOS平台。可以通过PerfDog对外开放的PerfDogService进行二次开发，定制自动化性能测试。PerfDog 数据都是由人力负责采集，所以无论是采集的效率和精准度都是较低的。同时由于转测期包的迭代速度非常快，因此人力测试的压力非常大。

## 蓝盾优势 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

在蓝盾上，通过封装调用PerfDog Service性能自动化接口，达到自动化采集数据并对不同场景阶段打标签的目的。

## 解决方案 <a href="#zhun-bei-shi-xiang" id="zhun-bei-shi-xiang"></a>

1、 PerfDog使用说明

PerfDog (性能狗)网址：https://perfdog.qq.com/

PerfDogService使用说明：https://bbs.perfdog.qq.com/article-detail.html?id=54

2、 客户端性能测试与PerfDog Service的结合

封装PerfDog Service的接口，增加时间更新线程等功能，同时添加了对PerfDog 全量数据解析的功能，以提取出想要的内容。（具体实现方式及说明，请联系PerDog官网客服）

3、 配置蓝盾流水线

结合蓝盾流水线以及wetest云真机进行自动化搭建，完成数据自动化采集。

![图1](../../.gitbook/assets/scene-Client-performance-testing-a.png)
